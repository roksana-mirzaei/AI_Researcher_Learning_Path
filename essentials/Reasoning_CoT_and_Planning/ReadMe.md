# Reasoning, Chain-of-Thought & Planning

This folder contains papers on advancing model reasoning capabilities, planning strategies, and structured problem-solving approaches that enable AI systems to tackle complex multi-step tasks.

For each paper below, I added detailed explanations and working implementations in the corresponding subfolders.

How to make models think, not just pattern-match. This category covers the leap from associative completion to structured multi-step reasoning, one of the defining frontiers of 2024-2026.

## Papers

- [Chain-of-Thought Prompting Elicits Reasoning in Large Language Models](https://arxiv.org/abs/2201.11903)
- *Wei et al. (2022)* — NeurIPS
- *Why it matters:* Showed that simply asking a model to think step by step dramatically improves reasoning, opening a new research programme.

- [Tree of Thoughts: Deliberate Problem Solving with Large Language Models](https://arxiv.org/abs/2305.10601)
- *Yao et al. (2023)* — NeurIPS
- *Why it matters:* Extended chain-of-thought to tree-structured exploration with backtracking, making models more deliberate problem solvers.

- [Self-Consistency Improves Chain of Thought Reasoning in Language Models](https://arxiv.org/abs/2203.11171)
- *Wang et al. (2023)* — ICLR
- *Why it matters:* Samples multiple reasoning paths and takes the majority answer, which reduces reasoning errors.

- [Let's Verify Step by Step (Process Reward Models)](https://arxiv.org/abs/2305.20050)
- *Lightman et al. (2023)* — arXiv / OpenAI
- *Why it matters:* Rewards each reasoning step, not just the final answer, making process supervision central to reasoning models.

- [STaR: Bootstrapping Reasoning With Reasoning](https://arxiv.org/abs/2203.14465)
- *Zelikman et al. (2022)* — NeurIPS
- *Why it matters:* Models can improve their own reasoning by training on their correct chains of thought, creating a self-improvement loop.

- [Quiet-STaR: Language Models Can Teach Themselves to Think Before Speaking](https://arxiv.org/abs/2403.09629)
- *Zelikman et al. (2024)* — arXiv
- *Why it matters:* Internalises reasoning into the model's forward pass rather than requiring explicit chain-of-thought prompts.

- [Reasoning with Language Model is Planning with World Model](https://aclanthology.org/2023.emnlp-main.507/)
- *Hao et al. (2023)* — EMNLP
- *Why it matters:* Frames LLM reasoning as planning with a learned world model, connecting language modelling to classical AI planning.

- [OpenAI o1 / o3 System Card & Technical Approach](https://openai.com/index/openai-o1-system-card/)
- *OpenAI (2024-2025)* — OpenAI
- *Why it matters:* Documents how extended inference-time compute can produce breakthrough reasoning on mathematics, science, and coding benchmarks.

---

## Extra Learning Material

- **[LLM Agents Learning](https://llmagents-learning.org/f24)** — Focus on building and understanding large language model-based agents, their architectures, and interactions.
- **[Agentic AI Learning](https://agenticai-learning.org/sp25)** — Comprehensive course on agentic AI systems, planning, and autonomous decision-making.