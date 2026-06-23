# What Has Changed Since the Original Transformer (2017)
taken from stanford course lecture 2 - you can find the course in ReadMe.md here. 

## Big Picture

The original Transformer introduced in 2017 is still the backbone of modern language models, but the way the key component is implemented has evolved a lot. 

## Positional Encoding: From Absolute Inputs to Relative Attention

One of the biggest shifts is in how models represent position. In the first Transformer, position information was added to token embeddings at the input level, either with learned absolute position vectors or fixed sinusoidal vectors. Learned absolute embeddings worked, but they had obvious limitations: they were tied to the maximum length seen during training and could overfit to dataset-specific position patterns. Sinusoidal embeddings solved part of this by giving a deterministic encoding for any index and by making similarity between positions depend on relative distance through trigonometric structure. That was already a strong idea, but modern models pushed it further by moving positional effects closer to where attention decisions are actually made.

In the sinusoidal method from the original Transformer, the position vector for token position $m$ is defined dimension-wise with alternating sine and cosine terms:

$$
PE(m, 2i) = \sin\left(\frac{m}{10000^{2i/d_{model}}}\right), \qquad
PE(m, 2i+1) = \cos\left(\frac{m}{10000^{2i/d_{model}}}\right)
$$

This gives each pair of dimensions a different frequency. Lower-index dimensions oscillate faster, while higher-index dimensions oscillate more slowly. Intuitively, that creates a multi-scale positional code: some coordinates are sensitive to short-range shifts and others to longer-range shifts.

The important geometric point discussed in class is why this captures relative distance. If you compare position vectors at $m$ and $n$, trigonometric identities like

$$
\cos(a-b) = \cos a \cos b + \sin a \sin b
$$

appear directly inside the dot product between their sinusoidal coordinates. As a result, parts of $PE(m) \cdot PE(n)$ become functions of $(m-n)$, not just absolute indices. This is why the representation naturally reflects relative displacement.

Reminder Cos(0) = 1

So when we say "closer positions are more similar," the intuition is that for small $|m-n|$, many cosine terms remain high, while for larger separations the aggregate similarity tends to drop (with periodic oscillation). It is not strictly monotonic everywhere because sine/cosine are periodic, but the construction still gives a strong inductive bias that nearby tokens should look more related than far-away tokens.

## RoPE, ALiBi, and Relative Bias in Practice

Instead of only adding position at input, newer approaches inject relative position information directly into attention logits or into the Query and Key geometry. T5-style relative position bias learns bucketed distance biases. ALiBi uses a deterministic linear penalty based on distance. RoPE, which is now extremely common, rotates Query and Key vectors by position-dependent angles so that their dot product naturally reflects relative displacement. In practice, this gives a much cleaner way to encode order in the exact part of the model where token similarity is computed. So the conceptual move is from absolute additive position signals to relative, attention-native position mechanisms.

## Normalization: Post-LN to Pre-LN, LayerNorm to RMSNorm

The second major evolution is normalization. The intuition discussed in class is that activations inside deep networks can have extreme values in different layers or dimensions. When that happens, optimization becomes harder because downstream layers see unstable scales, which makes weight learning less consistent. Normalization helps keep activations in a controlled range so training is more stable and convergence is faster.

In the original Transformer, the pattern was Post-LN: first do the sublayer computation, then add the residual, then normalize (the classic "Add & Norm" block). Modern LLMs mostly prefer Pre-LN: normalize first, pass through the sublayer, then add the residual. This small reordering has a big optimization effect in deep stacks and is one reason modern training is more stable.

For a hidden vector $x \in \mathbb{R}^d$, LayerNorm computes

$$
\mu = \frac{1}{d}\sum_{i=1}^{d} x_i,
\qquad
\sigma^2 = \frac{1}{d}\sum_{i=1}^{d}(x_i-\mu)^2
$$

then normalizes and applies learned affine parameters:

$$
\mathrm{LN}(x)_i = \gamma_i \cdot \frac{x_i-\mu}{\sqrt{\sigma^2+\epsilon}} + \beta_i
$$

So LayerNorm learns both $\gamma$ (scale) and $\beta$ (shift).

RMSNorm simplifies this by removing mean-centering and using only root-mean-square scaling:

$$
\mathrm{RMS}(x)=\sqrt{\frac{1}{d}\sum_{i=1}^{d}x_i^2 + \epsilon},
\qquad
\mathrm{RMSNorm}(x)_i = \gamma_i \cdot \frac{x_i}{\mathrm{RMS}(x)}
$$

In the common formulation, RMSNorm keeps the learned scale $\gamma$ and drops the learned bias term $\beta$. That reduction is part of why it is computationally lighter while often giving similar training behavior in large models.

It is also useful to contrast LayerNorm with BatchNorm. LayerNorm normalizes each token representation across its feature dimensions, so it does not depend on batch statistics and behaves consistently between training and inference. BatchNorm normalizes each feature using statistics across the batch dimension, which can be very effective in CNNs but is less convenient in autoregressive Transformer settings where sequence lengths and batch behavior can vary. This is why Transformer-based LLMs overwhelmingly use LayerNorm/RMSNorm rather than BatchNorm.

## Attention Efficiency and KV-Cache Pressure

Beyond position and normalization, attention itself was engineered for efficiency. Full attention has $O(n^2)$ complexity in sequence length, so many systems now use local or sliding-window attention in parts of the network, or combine local and global patterns across layers. Another important change is in head parameterization for decoding efficiency. Standard multi-head attention gives each head separate Q, K, and V projections. MQA shares K and V across heads, while GQA shares K and V across groups of heads. These changes are mostly motivated by KV-cache memory and inference throughput, and GQA has become a common compromise.

## Model Family Shift Since 2017

At the model-family level, the field has also specialized. The original encoder-decoder shape remains valuable, especially in text-to-text settings like T5, and encoder-only models like BERT are still strong for classification and representation tasks. But for large-scale generative systems, decoder-only models became the dominant design because they align well with next-token prediction and scale effectively.


## Paper Links

- Attention Is All You Need (Transformer, 2017): https://arxiv.org/abs/1706.03762
- Exploring the Limits of Transfer Learning with a Unified Text-to-Text Transformer (T5, 2019): https://arxiv.org/abs/1910.10683
- Train Short, Test Long: Attention with Linear Biases Enables Input Length Extrapolation (ALiBi, 2021): https://arxiv.org/abs/2108.12409
- RoFormer: Enhanced Transformer with Rotary Position Embedding (RoPE, 2021): https://arxiv.org/abs/2104.09864
- On Layer Normalization in the Transformer Architecture (Pre-LN vs Post-LN, 2020): https://arxiv.org/abs/2002.04745
- Root Mean Square Layer Normalization (RMSNorm, 2019): https://arxiv.org/abs/1910.07467
