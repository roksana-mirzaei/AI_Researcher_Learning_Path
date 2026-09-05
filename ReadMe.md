# AI Researcher Learning Path

![Implemented Papers](https://img.shields.io/badge/Implemented_Papers-6-blue)
![Notebooks](https://img.shields.io/badge/Notebooks-6-success)
![Last Updated](https://img.shields.io/badge/Last_Updated-2026--07--03-orange)
![License](https://img.shields.io/badge/License-MIT-lightgrey)

This repository is my personal learning journey to become a stronger AI researcher.

I use it to study important AI papers, build the core ideas from scratch, and keep notes on what I learn along the way.

## Table of Contents

- [How to Run](#how-to-run)
- [Learning Tracks](#learning-tracks)
- [Paper Progress and Metadata](#paper-progress-and-metadata)
- [Repository Layout](#repository-layout)
- [Contributing](#contributing)
- [License](#license)

## How to Run

Requires Python 3.12 (see `.python-version`).

```bash
python3 -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
jupyter notebook
```

This installs the dependencies needed across all notebooks in the repo. If you
only want to run a single paper's notebook, use the `requirements.txt` inside
that paper's own folder instead (e.g.
`essentials/Foundational_Architecture_and_Representation_Learning/Transformer/requirements.txt`).

Datasets used by the CV notebooks (e.g. CIFAR-10) are downloaded by the
notebooks themselves on first run and are not committed to the repo.

## Learning Tracks

The repository is organized into progressive tracks and domain themes:

- **Essentials:** Core concepts required to reason about modern AI systems.
- **Foundation:** Fundamental methods for decision-making and learning dynamics.
- **High:** Advanced topics for production-scale and frontier research.
- **Recommended:** Adjacent domains that broaden research perspective.

## Paper Progress and Metadata

| Paper | Year | Venue | Type | Difficulty | Status | Notes | Implementation Link |
| --- | --- | --- | --- | --- | --- | --- | --- |
| Attention Is All You Need | 2017 | NeurIPS | NLP | Intermediate | Done | Transformer from-scratch implementation notebook available. | [Transformer notebook](essentials/Foundational_Architecture_and_Representation_Learning/Transformer/transformers_from_scratch.ipynb) |
| BERT: Pre-training of Deep Bidirectional Transformers for Language Understanding | 2019 | NAACL | NLP | Intermediate | Done | BERT implementation notebook available. | [BERT notebook](essentials/Foundational_Architecture_and_Representation_Learning/BERT/bert_from_scratch.ipynb) |
| Language Models are Unsupervised Multitask Learners (GPT-2) | 2019 | OpenAI Technical Report | NLP | Intermediate | Done | GPT-2 experiment notebook available. | [GPT-2 notebook](essentials/Foundational_Architecture_and_Representation_Learning/GPT-2/gpt-2-experiment.ipynb) |
| Deep Residual Learning for Image Recognition (ResNet) | 2016 | CVPR | CV | Intermediate | Done | ResNet from-scratch notebook available. | [ResNet notebook](essentials/Foundational_Architecture_and_Representation_Learning/ResNet/ResNet_from_scratch.ipynb) |
| Mixture of Experts Meets Instruction Tuning | 2023 | arXiv | Systems | Advanced | Done | MoE implementation notebook available. | [MoE notebook](essentials/Foundational_Architecture_and_Representation_Learning/MoE/implement_MoE_from_scratch.ipynb) |
| An Image is Worth 16x16 Words: Transformers for Image Recognition at Scale (ViT) | 2021 | ICLR | CV | Intermediate | Done | Vision Transformer from-scratch implementation notebook available. | [ViT notebook](essentials/Foundational_Architecture_and_Representation_Learning/ViT/Vision_Transfomer_from_scratch.ipynb) |
| [Concrete Problems in AI Safety](https://arxiv.org/abs/1606.06565) | 2016 | arXiv | Safety | Intermediate | To Read | Foundational taxonomy of real-world safety problems (reward hacking, distributional shift, safe exploration). | -- |
| [Deep Reinforcement Learning from Human Preferences](https://arxiv.org/abs/1706.03741) | 2017 | NeurIPS | Alignment | Intermediate | To Read | Introduced learning reward models from human preference data. | -- |
| [Direct Preference Optimization (DPO)](https://arxiv.org/abs/2305.18290) | 2023 | NeurIPS | Alignment | Intermediate | To Read | Simplifies RLHF by optimizing policy directly from preferences without a separate reward model. | -- |
| [Denoising Diffusion Probabilistic Models (DDPM)](https://arxiv.org/abs/2006.11239) | 2020 | NeurIPS | Generative | Intermediate | To Read | Foundational diffusion paper for iterative denoising from Gaussian noise. | -- |
| [High-Resolution Image Synthesis with Latent Diffusion Models](https://arxiv.org/abs/2112.10752) | 2022 | CVPR | Generative | Intermediate | To Read | Introduced latent diffusion for practical high-resolution generation. | -- |
| [Scalable Diffusion Models with Transformers (DiT)](https://arxiv.org/abs/2212.09748) | 2023 | ICCV | Generative | Advanced | To Read | Replaced U-Nets with transformers and improved diffusion scaling behavior. | -- |
| [Flow Matching for Generative Modeling](https://arxiv.org/abs/2210.02747) | 2023 | ICLR | Generative | Advanced | To Read | Flow-based alternative to diffusion with simpler training and faster sampling. | -- |
| Graph RAG & Knowledge Graph Integration | 2024 | Various | Retrieval | Intermediate | To Read | Extends RAG to structured knowledge graphs for multi-hop relational reasoning. | -- |
| [Proximal Policy Optimization (PPO)](https://arxiv.org/abs/1707.06347) | 2017 | arXiv | RL | Intermediate | To Read | Stable and practical policy optimization method used widely in RLHF pipelines. | -- |
| [LoRA: Low-Rank Adaptation of Large Language Models](https://arxiv.org/abs/2106.09685) | 2022 | ICLR | LLM Systems | Intermediate | To Read | Efficient parameter-efficient fine-tuning via low-rank adapters in frozen weights. | -- |


## Repository Layout

```text
AI_Researcher_Learning_Path/
├── ReadMe.md
├── essentials/
│   ├── ReadMe.md
│   └── Foundational_Architecture_and_Representation_Learning/
│       ├── ReadMe.md
│       ├── Transformer/
│       └── ...
├── foundation/
│   ├── ReadMe.md
│   └── Reinforcement_Learning_and_Decision_Making/
├── high/
│   └── ReadMe.md
└── recommended/
    └── ReadMe.md
```

## Contributing

This is primarily a personal learning repo, developed with a mentor. See
[CONTRIBUTING.md](CONTRIBUTING.md) for setup instructions and conventions, and
[CODE_OF_CONDUCT.md](CODE_OF_CONDUCT.md) for community guidelines.

## License

This project is licensed under the [MIT License](LICENSE).
