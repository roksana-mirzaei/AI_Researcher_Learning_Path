# Agents, Tool Use and Autonomous Systems

This folder covers papers and systems about agents that reason, call tools, act in environments, and coordinate longer-horizon plans. The main theme is how language models move from static prediction to interactive decision-making.

For each paper below, I added short notes on why it matters and, where relevant, linked the implementation or project folder.

---

## Core Agent Papers and Systems

1. **[ReAct: Synergizing Reasoning and Acting in Language Models](https://arxiv.org/abs/2210.03629)**
	- Yao et al. (2023) - ICLR
	- Why it matters: The canonical framework for interleaving reasoning traces with tool actions. Nearly every modern agent system builds on this pattern.
	- Status: Completed

2. **[Toolformer: Language Models Can Teach Themselves to Use Tools](https://arxiv.org/abs/2302.04761)**
	- Schick et al. (2023) - NeurIPS
	- Why it matters: Showed how models can learn when and how to call tools, including calculators, search, APIs, and external functions.

3. **[Voyager: An Open-Ended Embodied Agent with Large Language Models](https://arxiv.org/abs/2305.16291)**
	- Wang et al. (2023) - arXiv
	- Why it matters: A landmark embodied agent that learns continuously through code generation, memory, and self-improvement in an open-ended environment.

4. **[Generative Agents: Interactive Simulacra of Human Behavior](https://arxiv.org/abs/2304.03442)**
	- Park et al. (2023) - UIST
	- Why it matters: Demonstrated believable multi-agent social behavior, memory, and emergent routines inside a simulated world.

5. **AutoGPT / BabyAGI and the Autonomous Agent Movement**
	- Open-source projects (2023)
	- Why it matters: Defined the first wave of autonomous agent prototypes, showing both the promise and the failure modes of looping LLM agents.

6. **[SWE-bench: Can Language Models Resolve Real-World GitHub Issues?](https://arxiv.org/abs/2310.06770)**
	- Jimenez et al. (2024) - arXiv
	- Why it matters: Became a key benchmark for coding agents and tool-using systems that must edit code, run tests, and fix real bugs.

7. **[Gorilla: Large Language Models Connected with Massive APIs](https://arxiv.org/abs/2305.15334)**
	- Patil et al. (2023) - arXiv
	- Why it matters: Focused on reliable API selection and tool invocation, pushing agents toward grounded, structured interactions with external systems.

8. **[The Landscape of Emerging AI Agent Architectures for Reasoning, Planning, and Tool Use](https://arxiv.org/search/?query=The+Landscape+of+Emerging+AI+Agent+Architectures+for+Reasoning%2C+Planning%2C+and+Tool+Use&searchtype=all)**
	- Survey paper
	- Why it matters: A useful map of the design space for agent architecture, including planning loops, memory, tool use, and coordination.

---

## Study Focus

- Reasoning and acting loops
- Tool selection and API calling
- Memory, planning, and reflection
- Embodied and open-ended environments
- Benchmarks for real-world agent performance
TBC