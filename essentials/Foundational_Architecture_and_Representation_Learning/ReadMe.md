# Foundational Architecture & Representation Learning

This folder contains all works focused on the structural blueprints of modern AI. These papers define the architectures and training paradigms that underpin virtually everything else on this list. Understanding them is non-negotiable.

For each paper below, I added detailed explanations and working implementations in the corresponding subfolders.

---

## Core Transformer Architecture

1. **[Attention Is All You Need](https://arxiv.org/abs/1706.03762)**
   - Vaswani et al. (2017) — NeurIPS
   - Why it matters: The paper that launched the transformer era. Every modern LLM, vision model, and multimodal system traces its lineage here.

2. **[BERT: Pre-training of Deep Bidirectional Transformers for Language Understanding](https://arxiv.org/abs/1810.04805)**
   - Devlin et al. (2019) — NAACL
   - Why it matters: Established the pre-train-then-fine-tune paradigm and bidirectional context modelling that shaped an entire generation of NLP.

3. **[An Image is Worth 16x16 Words: Transformers for Image Recognition at Scale (ViT)](https://arxiv.org/abs/2010.11929)**
   - Dosovitskiy et al. (2021) — ICLR
   - Why it matters: Proved transformers could replace CNNs for vision, unifying the architecture across modalities.

4. **[Language Models are Unsupervised Multitask Learners (GPT-2)](https://arxiv.org/abs/1902.10673)**
   - Radford et al. (2019) — OpenAI
   - Why it matters: Demonstrated that scale plus next-token prediction yields emergent generalist capabilities without task-specific training.

---

## Architectural Foundations & Improvements

5. **[Deep Residual Learning for Image Recognition (ResNet)](https://arxiv.org/abs/1512.03385)**
   - He et al. (2016) — CVPR
   - Why it matters: Solved the degradation problem with skip connections; still the conceptual backbone of deep network training.

6. **[Scaling Laws for Neural Language Models](https://arxiv.org/abs/2001.08361)**
   - Kaplan et al. (2020) — arXiv
   - Why it matters: Quantified how loss scales predictably with compute, data, and parameters—the intellectual foundation of the scaling hypothesis.

7. **[FlashAttention: Fast and Memory-Efficient Exact Attention with IO-Awareness](https://arxiv.org/abs/2205.14135)**
   - Dao et al. (2022) — NeurIPS
   - Why it matters: Made long-context transformers practical by rethinking attention as an IO problem rather than a compute problem.

---

## Alternative Architectures & Optimization

8. **[Mamba: Linear-Time Sequence Modeling with Selective State Spaces](https://arxiv.org/abs/2312.08956)**
   - Gu & Dao (2023) — arXiv
   - Why it matters: The leading alternative to attention: linear-time sequence modelling that challenges the transformer's monopoly on long-context tasks.

9. **[Mixture of Experts Meets Instruction Tuning (MoE)](https://arxiv.org/abs/2305.14819)**
   - Shen et al. (2023) — arXiv
   - Why it matters: Sparse expert routing allows models to scale parameters without proportional compute cost—the architecture behind many frontier models.
 
