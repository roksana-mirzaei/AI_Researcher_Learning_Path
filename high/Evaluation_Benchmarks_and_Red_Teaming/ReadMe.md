# Evaluation, Benchmarks & Red-Teaming

This folder covers the papers and benchmarks I use to measure model capability, expose weaknesses, and study evaluation methodology. The main focus is on how we test systems rigorously in a fast-moving field.

For each item below, I included a short note on why it matters and, where useful, a status marker.

---

## Core Evaluation Papers and Benchmarks

1. **[Holistic Evaluation of Language Models (HELM)](https://www.crfm.stanford.edu/helm/)**
	- Liang et al. (2022) - TMLR
	- Why it matters: Established comprehensive, multi-dimensional evaluation covering accuracy, fairness, robustness, efficiency, and calibration.

2. **[MMLU: Measuring Massive Multitask Language Understanding](https://crfm.stanford.edu/helm/mmlu/latest/)**
	- Hendrycks et al. (2021) - ICLR
	- Why it matters: A 57-subject knowledge benchmark that became the standard measure of LLM capability, and is now both essential and showing its age.

3. **[Chatbot Arena & the Elo Rating System for LLMs](https://lmsys.org/blog/2023-05-03-arena/)**
	- Zheng et al. (2023) - arXiv / LMSYS
	- Why it matters: Human preference-based evaluation through blind pairwise comparison, and one of the most trusted public rankings of LLM quality.
	- Status: Completed

4. **[Red Teaming Language Models to Reduce Harms](https://arxiv.org/abs/2209.07858)**
	- Ganguli et al. (2022) - arXiv / Anthropic
	- Why it matters: Systematic adversarial evaluation to find failure modes before deployment, which is essential methodology for responsible AI.

5. **[Evaluating Large Language Models Trained on Code (HumanEval)](https://arxiv.org/abs/2107.03374)**
	- Chen et al. (2021) - arXiv / OpenAI
	- Why it matters: The foundational code generation benchmark, measuring functional correctness of synthesised programs.

6. **[GPQA: A Graduate-Level Google-Proof Question-Answering Benchmark](https://arxiv.org/abs/2311.12022)**
	- Rein et al. (2023) - arXiv
	- Why it matters: PhD-level questions that even expert humans struggle with without domain knowledge, making it a strong ceiling benchmark for LLM reasoning.

---

## Study Focus

- Benchmark design and contamination risks
- Human preference evaluation and ranking systems
- Safety, robustness, and adversarial testing
- Code generation and functional correctness
- Reasoning benchmarks and capability ceilings
TBC