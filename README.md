<div align="center">

# 🤖 Awesome Agentic Embodied Systems

[![Awesome](https://awesome.re/badge.svg)](https://awesome.re)
[![License: BSD-3-Clause](https://img.shields.io/badge/License-BSD--3--Clause-blue.svg)](LICENSE)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](CONTRIBUTING.md)

**A curated research map of the models, runtimes, and learning loops behind goal-directed embodied agents.**

_Last literature sweep: 2026-08-30_

</div>

---

## News and Updates

- **2026-08 — Initial release.** Published the initial system-oriented research map.
- **Ongoing — Contributions welcome.** Missing papers, corrected links, and better placements are welcome through focused issues or pull requests; see [CONTRIBUTING.md](CONTRIBUTING.md).

## Overview

- [🤖 Awesome Agentic Embodied Systems](#-awesome-agentic-embodied-systems)
  - [News and Updates](#news-and-updates)
  - [Overview](#overview)
  - [Motivation: Why Agentic Embodied Systems, Why Now?](#motivation-why-agentic-embodied-systems-why-now)
  - [Scope and System Map](#scope-and-system-map)
  - [Tutorials, Surveys, and Starter Resources](#tutorials-surveys-and-starter-resources)
  - [Scaling Laws and Scaling Evidence](#scaling-laws-and-scaling-evidence)
    - [Language and Vision-Language Models](#language-and-vision-language-models)
    - [Embodied AI Scaling Evidence](#embodied-ai-scaling-evidence)
  - [Foundation Models, Policies, and Data](#foundation-models-policies-and-data)
    - [Generalist Embodied Models and Policies](#generalist-embodied-models-and-policies)
    - [Promptable and In-Context Robot Policies](#promptable-and-in-context-robot-policies)
    - [Data and Open Infrastructure](#data-and-open-infrastructure)
  - [Agentic Embodied System Stack](#agentic-embodied-system-stack)
    - [Architectures and Harnesses](#architectures-and-harnesses)
    - [State, Context, and Memory](#state-context-and-memory)
      - [Embodied Systems and Robotics Foundations](#embodied-systems-and-robotics-foundations)
      - [Adjacent Memory Architectures](#adjacent-memory-architectures)
    - [Planning and Orchestration](#planning-and-orchestration)
    - [Tools, Programs, and Action Grounding](#tools-programs-and-action-grounding)
      - [Embodied Systems and Robotics Foundations](#embodied-systems-and-robotics-foundations-1)
      - [Adjacent Agent Interfaces](#adjacent-agent-interfaces)
    - [Monitoring, Verification, and Recovery](#monitoring-verification-and-recovery)
      - [Embodied Systems and Robotics Foundations](#embodied-systems-and-robotics-foundations-2)
      - [Adjacent Verification and Feedback](#adjacent-verification-and-feedback)
    - [Skill Learning and Lifelong Adaptation](#skill-learning-and-lifelong-adaptation)
    - [Autonomous System and Policy Improvement](#autonomous-system-and-policy-improvement)
      - [Embodied Data, Policy, and Harness Loops](#embodied-data-policy-and-harness-loops)
      - [Adjacent Autonomous-Agent Precedents](#adjacent-autonomous-agent-precedents)
    - [Multi-Agent, Multi-Robot, and Fleet Coordination](#multi-agent-multi-robot-and-fleet-coordination)
      - [Embodied and Multi-Robot Systems](#embodied-and-multi-robot-systems)
      - [Adjacent Multi-Agent References](#adjacent-multi-agent-references)
  - [Environments and Evaluation](#environments-and-evaluation)
    - [Platforms and Task Suites](#platforms-and-task-suites)
    - [Evaluation Infrastructure and Real-World Arenas](#evaluation-infrastructure-and-real-world-arenas)
    - [Long-Horizon, Language, Memory, and Collaboration](#long-horizon-language-memory-and-collaboration)
    - [Robustness and System Evaluation](#robustness-and-system-evaluation)
      - [Embodied System Evaluation](#embodied-system-evaluation)
      - [Adjacent Digital-Agent Evaluation](#adjacent-digital-agent-evaluation)
  - [Challenges and Open Questions](#challenges-and-open-questions)
  - [Related Repositories and Resources](#related-repositories-and-resources)
  - [Contributing](#contributing)
  - [Acknowledgements](#acknowledgements)

## Motivation: Why Agentic Embodied Systems, Why Now?

A useful way to read recent language and vision-language AI is:

```text
scaling -> foundation models -> agents / harnesses
```

Empirical [scaling laws](https://arxiv.org/abs/2001.08361) linked model performance to data, parameters, and compute. Broad pretraining produced adaptable [foundation models](https://arxiv.org/abs/2108.07258). As multimodal reasoning, code generation, and tool use improved, research expanded toward reliable multi-step goal completion. [ReAct](https://arxiv.org/abs/2210.03629) interleaved reasoning with action and observation, and [SWE-agent](https://arxiv.org/abs/2405.15793) showed that agent interfaces materially shape behavior. A **harness** supplies runtime interfaces, persistent state, and outcome-driven control around a model. All three stages continue to co-evolve.

Embodied AI can draw on semantic and multimodal priors that are costly to learn from robot trajectories alone. [RT-2](https://arxiv.org/abs/2307.15818) transferred Internet-scale vision-language training to robotic control, [Open X-Embodiment](https://arxiv.org/abs/2310.08864) found positive transfer across embodiments, and [π₀.₅](https://arxiv.org/abs/2504.16054) combined heterogeneous robot, semantic, and web data for manipulation in unseen homes. Together, these works provide evidence for reusable cross-task transfer and control within the studied settings.

Physical interaction makes state uncertain, action constrained, and recovery costly. System interfaces and outcome verification therefore become central to long-horizon performance: [SayCan](https://arxiv.org/abs/2204.01691) grounds plans in executable affordances, and [LIBERO-PRO](https://arxiv.org/abs/2510.03827) measures degradation under task and environment perturbations.

Reusable models and skills now make harness design a visible research target. [Thea](https://arxiv.org/abs/2608.11246), [ENPIRE](https://arxiv.org/abs/2606.19980), and [ASPIRE](https://arxiv.org/abs/2607.00272) study closed-loop state management, recovery, and improvement in embodied systems. The central question is how model and runtime capabilities should scale together in grounded interaction.

## Scope and System Map

This repository maps agentic embodied research across enabling models, system design, and evaluation. It prioritizes verified primary links, concise synthesis, and one primary section per work.

Papers are the default evidence unit. Technically substantive non-paper sources are included when they materially shape the field; source types and company reports are labeled explicitly.

> **Agentic embodied systems** organize embodied models and policies through a runtime that supports goal-directed interaction, feedback, and improvement.

The scope covers physical and simulated environments, within and across episodes.

The collection moves from scaling evidence and reusable models through the agentic system stack to evaluation. Historical robotics and adjacent software-agent precedents appear within the corresponding module. Entries follow earliest public release, use one primary home, and cross-reference other relationships.

## Tutorials, Surveys, and Starter Resources

- **Embodied AI Survey**: "A Survey of Embodied AI: From Simulators to Research Tasks". [![arXiv](https://img.shields.io/badge/arXiv-2103.04918-b31b1b.svg)](https://arxiv.org/abs/2103.04918)
- **Large Language Models for Robotics**: "Large Language Models for Robotics: A Survey". [![arXiv](https://img.shields.io/badge/arXiv-2311.07226-b31b1b.svg)](https://arxiv.org/abs/2311.07226)
- **Foundation Models in Robotics**: "Foundation Models in Robotics: Applications, Challenges, and the Future". [![arXiv](https://img.shields.io/badge/arXiv-2312.07843-b31b1b.svg)](https://arxiv.org/abs/2312.07843) [![Code](https://img.shields.io/badge/Resources-GitHub-green)](https://github.com/robotics-survey/Awesome-Robotics-Foundation-Models)
- **LLMs for Robotics: Opportunities and Challenges**: "Large Language Models for Robotics: Opportunities, Challenges, and Perspectives". [![arXiv](https://img.shields.io/badge/arXiv-2401.04334-b31b1b.svg)](https://arxiv.org/abs/2401.04334)
- **Robotics with Foundation Models**: "A Survey on Robotics with Foundation Models: toward Embodied AI". [![arXiv](https://img.shields.io/badge/arXiv-2402.02385-b31b1b.svg)](https://arxiv.org/abs/2402.02385)
- **VLA Survey**: "A Survey on Vision-Language-Action Models for Embodied AI". [![arXiv](https://img.shields.io/badge/arXiv-2405.14093-b31b1b.svg)](https://arxiv.org/abs/2405.14093)
- **Building Effective Agents**: "Building effective agents". [![Website](https://img.shields.io/badge/Website-Anthropic-blue)](https://www.anthropic.com/engineering/building-effective-agents)
- **Harness Engineering with Codex**: "Harness engineering: leveraging Codex in an agent-first world". [![Website](https://img.shields.io/badge/Website-OpenAI-blue)](https://openai.com/index/harness-engineering/)
- **Harness Engineering for Physical AI**: "Harness Engineering for Physical AI: Robot Middleware Is the Harness Layer". [![arXiv](https://img.shields.io/badge/arXiv-2606.09416-b31b1b.svg)](https://arxiv.org/abs/2606.09416)
- **Scaling Laws, Carefully**: "Scaling Laws, Carefully". [![Website](https://img.shields.io/badge/Website-Lil%27Log-blue)](https://lilianweng.github.io/posts/2026-06-24-scaling-laws/)
- **Embodied Collective Intelligence**: "When Multi-Robot Systems Meet Agentic AI: Towards Embodied Collective Intelligence". [![arXiv](https://img.shields.io/badge/arXiv-2606.27929-b31b1b.svg)](https://arxiv.org/abs/2606.27929)
- **Harness Engineering for Self-Improvement**: "Harness Engineering for Self-Improvement". [![Website](https://img.shields.io/badge/Website-Lil%27Log-blue)](https://lilianweng.github.io/posts/2026-07-04-harness/)

## Scaling Laws and Scaling Evidence

These works connect scaling research in language, vision-language, and embodied AI.

### Language and Vision-Language Models

- **Kaplan Scaling Laws**: "Scaling Laws for Neural Language Models". [![arXiv](https://img.shields.io/badge/arXiv-2001.08361-b31b1b.svg)](https://arxiv.org/abs/2001.08361)
- **Chinchilla**: "Training Compute-Optimal Large Language Models". [![arXiv](https://img.shields.io/badge/arXiv-2203.15556-b31b1b.svg)](https://arxiv.org/abs/2203.15556)
- **OpenCLIP Scaling**: "Reproducible scaling laws for contrastive language-image learning". [![arXiv](https://img.shields.io/badge/arXiv-2212.07143-b31b1b.svg)](https://arxiv.org/abs/2212.07143) [![Code](https://img.shields.io/badge/Code-GitHub-green)](https://github.com/LAION-AI/scaling-laws-openclip)
- **Zero-Shot Data Limit**: "No \"Zero-Shot\" Without Exponential Data: Pretraining Concept Frequency Determines Multimodal Model Performance". [![arXiv](https://img.shields.io/badge/arXiv-2404.04125-b31b1b.svg)](https://arxiv.org/abs/2404.04125)

### Embodied AI Scaling Evidence

Embodied scaling evidence remains less mature than language-model scaling laws. Proprietary company reports are labeled to reflect their limited reproducibility.

- **Manipulation Data Scaling**: "Data Scaling Laws in Imitation Learning for Robotic Manipulation". [![arXiv](https://img.shields.io/badge/arXiv-2410.18647-b31b1b.svg)](https://arxiv.org/abs/2410.18647) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://data-scaling-laws.github.io/)
- **Agents and World Models**: "Scaling Laws for Pre-training Agents and World Models". [![arXiv](https://img.shields.io/badge/arXiv-2411.04434-b31b1b.svg)](https://arxiv.org/abs/2411.04434)
- **GEN-0**: "GEN-0 / Embodied Foundation Models That Scale with Physical Interaction". [![Website](https://img.shields.io/badge/Report-Generalist_AI-blue)](https://generalistai.com/blog/gen-0)
- **EgoScale**: "EgoScale: Scaling Dexterous Manipulation with Diverse Egocentric Human Data". [![arXiv](https://img.shields.io/badge/arXiv-2602.16710-b31b1b.svg)](https://arxiv.org/abs/2602.16710) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://research.nvidia.com/labs/gear/egoscale/)
- **Precision Scaling**: "The Curse of Precision: A Data Scaling Law for High-Precision Robotic Manipulation". [![arXiv](https://img.shields.io/badge/arXiv-2607.23108-b31b1b.svg)](https://arxiv.org/abs/2607.23108)
- **Dyna-2**: "Dyna-2: A 1-Million-Hour Scaling Law for World-Action Models". [![Website](https://img.shields.io/badge/Report-DYNA-blue)](https://www.dyna.co/dyna-2)

## Foundation Models, Policies, and Data

Foundation models, generalist policies, and shared datasets supply reusable capabilities for agentic runtimes.

### Generalist Embodied Models and Policies

This section selects models and policies that materially advance reusable embodied capability or its integration into agentic systems. Checkpoint updates are grouped by model family.

- **CLIPort**: "CLIPort: What and Where Pathways for Robotic Manipulation". [![arXiv](https://img.shields.io/badge/arXiv-2109.12098-b31b1b.svg)](https://arxiv.org/abs/2109.12098) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://cliport.github.io/)
- **BC-Z**: "BC-Z: Zero-Shot Task Generalization with Robotic Imitation Learning". [![arXiv](https://img.shields.io/badge/arXiv-2202.02005-b31b1b.svg)](https://arxiv.org/abs/2202.02005)
- **Gato**: "A Generalist Agent". [![arXiv](https://img.shields.io/badge/arXiv-2205.06175-b31b1b.svg)](https://arxiv.org/abs/2205.06175)
- **VIMA**: "VIMA: General Robot Manipulation with Multimodal Prompts". [![arXiv](https://img.shields.io/badge/arXiv-2210.03094-b31b1b.svg)](https://arxiv.org/abs/2210.03094) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://vimalabs.github.io/)
- **RT-1**: "RT-1: Robotics Transformer for Real-World Control at Scale". [![arXiv](https://img.shields.io/badge/arXiv-2212.06817-b31b1b.svg)](https://arxiv.org/abs/2212.06817)
- **PaLM-E**: "PaLM-E: An Embodied Multimodal Language Model". [![arXiv](https://img.shields.io/badge/arXiv-2303.03378-b31b1b.svg)](https://arxiv.org/abs/2303.03378)
- **RT-2**: "RT-2: Vision-Language-Action Models Transfer Web Knowledge to Robotic Control". [![arXiv](https://img.shields.io/badge/arXiv-2307.15818-b31b1b.svg)](https://arxiv.org/abs/2307.15818)
- **Open X-Embodiment / RT-X**: "Open X-Embodiment: Robotic Learning Datasets and RT-X Models". [![arXiv](https://img.shields.io/badge/arXiv-2310.08864-b31b1b.svg)](https://arxiv.org/abs/2310.08864) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://robotics-transformer-x.github.io/)
- **RT-H**: "RT-H: Action Hierarchies Using Language". [![arXiv](https://img.shields.io/badge/arXiv-2403.01823-b31b1b.svg)](https://arxiv.org/abs/2403.01823) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://rt-hierarchy.github.io/)
- **Octo**: "Octo: An Open-Source Generalist Robot Policy". [![arXiv](https://img.shields.io/badge/arXiv-2405.12213-b31b1b.svg)](https://arxiv.org/abs/2405.12213) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://octo-models.github.io/)
- **OpenVLA**: "OpenVLA: An Open-Source Vision-Language-Action Model". [![arXiv](https://img.shields.io/badge/arXiv-2406.09246-b31b1b.svg)](https://arxiv.org/abs/2406.09246) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://openvla.github.io/)
- **RDT-1B**: "RDT-1B: a Diffusion Foundation Model for Bimanual Manipulation". [![arXiv](https://img.shields.io/badge/arXiv-2410.07864-b31b1b.svg)](https://arxiv.org/abs/2410.07864)
- **π₀**: "$π_0$: A Vision-Language-Action Flow Model for General Robot Control". [![arXiv](https://img.shields.io/badge/arXiv-2410.24164-b31b1b.svg)](https://arxiv.org/abs/2410.24164) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://www.pi.website/blog/pi0)
- **Magma**: "Magma: A Foundation Model for Multimodal AI Agents". [![arXiv](https://img.shields.io/badge/arXiv-2502.13130-b31b1b.svg)](https://arxiv.org/abs/2502.13130) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://microsoft.github.io/Magma/) [![Code](https://img.shields.io/badge/Code-GitHub-green)](https://github.com/microsoft/Magma)
- **Helix family**: "Helix: A Vision-Language-Action Model for Generalist Humanoid Control". [![Helix](https://img.shields.io/badge/Report-Helix-blue)](https://www.figure.ai/news/helix) [![Helix 02](https://img.shields.io/badge/Report-Helix_02-blue)](https://www.figure.ai/news/helix-02)
- **GR00T N family**: "GR00T N1: An Open Foundation Model for Generalist Humanoid Robots". [![arXiv](https://img.shields.io/badge/arXiv-2503.14734-b31b1b.svg)](https://arxiv.org/abs/2503.14734) [![N1.6](https://img.shields.io/badge/Project-N1.6-blue)](https://research.nvidia.com/labs/gear/gr00t-n1_6/) [![N1.7](https://img.shields.io/badge/Model-N1.7-yellow)](https://huggingface.co/nvidia/GR00T-N1.7-3B) [![Code](https://img.shields.io/badge/Code-GitHub-green)](https://github.com/NVIDIA/Isaac-GR00T)
- **Gemini Robotics**: "Gemini Robotics: Bringing AI into the Physical World". [![arXiv](https://img.shields.io/badge/arXiv-2503.20020-b31b1b.svg)](https://arxiv.org/abs/2503.20020) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://deepmind.google/blog/gemini-robotics-brings-ai-into-the-physical-world/)
- **π₀.₅**: "$π_{0.5}$: a Vision-Language-Action Model with Open-World Generalization". [![arXiv](https://img.shields.io/badge/arXiv-2504.16054-b31b1b.svg)](https://arxiv.org/abs/2504.16054)
- **SmolVLA**: "SmolVLA: A Vision-Language-Action Model for Affordable and Efficient Robotics". [![arXiv](https://img.shields.io/badge/arXiv-2506.01844-b31b1b.svg)](https://arxiv.org/abs/2506.01844)
- **TRI LBM 1.0**: "A Careful Examination of Large Behavior Models for Multitask Dexterous Manipulation". [![arXiv](https://img.shields.io/badge/arXiv-2507.05331-b31b1b.svg)](https://arxiv.org/abs/2507.05331) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://toyotaresearchinstitute.github.io/lbm1/)
- **GR-3**: "GR-3 Technical Report". [![arXiv](https://img.shields.io/badge/arXiv-2507.15493-b31b1b.svg)](https://arxiv.org/abs/2507.15493) [![Website](https://img.shields.io/badge/Report-ByteDance_Seed-blue)](https://seed.bytedance.com/en/public_papers/gr-3-technical-report)
- **Gemini Robotics 1.5**: "Gemini Robotics 1.5: Pushing the Frontier of Generalist Robots with Advanced Embodied Reasoning, Thinking, and Motion Transfer". [![arXiv](https://img.shields.io/badge/arXiv-2510.03342-b31b1b.svg)](https://arxiv.org/abs/2510.03342)
- **X-VLA**: "X-VLA: Soft-Prompted Transformer as Scalable Cross-Embodiment Vision-Language-Action Model". [![arXiv](https://img.shields.io/badge/arXiv-2510.10274-b31b1b.svg)](https://arxiv.org/abs/2510.10274) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://thu-air-dream.github.io/X-VLA/) [![Code](https://img.shields.io/badge/Code-GitHub-green)](https://github.com/2toinf/X-VLA)
- **LingBot-VLA**: "A Pragmatic VLA Foundation Model". [![arXiv](https://img.shields.io/badge/arXiv-2601.18692-b31b1b.svg)](https://arxiv.org/abs/2601.18692)
- **DreamZero**: "World Action Models are Zero-shot Policies". [![arXiv](https://img.shields.io/badge/arXiv-2602.15922-b31b1b.svg)](https://arxiv.org/abs/2602.15922) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://dreamzero0.github.io/) [![Code](https://img.shields.io/badge/Code-GitHub-green)](https://github.com/dreamzero0/dreamzero)
- **GEN-1**: "GEN-1: Scaling Embodied Foundation Models to Mastery". [![Website](https://img.shields.io/badge/Report-Generalist_AI-blue)](https://generalistai.com/blog/gen-1)
- **π₀.₇**: "$π_{0.7}$: a Steerable Generalist Robotic Foundation Model with Emergent Capabilities". [![arXiv](https://img.shields.io/badge/arXiv-2604.15483-b31b1b.svg)](https://arxiv.org/abs/2604.15483) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://www.pi.website/blog/pi07)
- **MolmoAct 2**: "MolmoAct2: Action Reasoning Models for Real-world Deployment". [![arXiv](https://img.shields.io/badge/arXiv-2605.02881-b31b1b.svg)](https://arxiv.org/abs/2605.02881) [![Website](https://img.shields.io/badge/Website-AI2-blue)](https://allenai.org/blog/molmoact2) [![Code](https://img.shields.io/badge/Code-GitHub-green)](https://github.com/allenai/molmoact2)
- **Embodied-R1.5**: "Embodied-R1.5: Evolving Physical Intelligence via Embodied Foundation Models". [![arXiv](https://img.shields.io/badge/arXiv-2606.11324-b31b1b.svg)](https://arxiv.org/abs/2606.11324) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://embodied-r.github.io/) [![Code](https://img.shields.io/badge/Code-GitHub-green)](https://github.com/pickxiguapi/Embodied-R1.5)
- **Vesta**: "Vesta: A Generalist Embodied Reasoning Model". [![arXiv](https://img.shields.io/badge/arXiv-2606.20905-b31b1b.svg)](https://arxiv.org/abs/2606.20905) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://research.nvidia.com/labs/gear/vesta/)
- **LingBot-VLA 2.0**: "From Foundation to Application: Improving VLA Models in Practice". [![arXiv](https://img.shields.io/badge/arXiv-2607.06403-b31b1b.svg)](https://arxiv.org/abs/2607.06403) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://technology.robbyant.com/lingbot-vla-v2) [![Code](https://img.shields.io/badge/Code-GitHub-green)](https://github.com/Robbyant/lingbot-vla-v2)
- **Xiaomi-Robotics-1**: "Xiaomi-Robotics-1: Scaling Vision-Language-Action Models with over 100K Hours of Real-World Trajectories". [![arXiv](https://img.shields.io/badge/arXiv-2607.15330-b31b1b.svg)](https://arxiv.org/abs/2607.15330) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://robotics.xiaomi.com/xiaomi-robotics-1.html) [![Code](https://img.shields.io/badge/Code-GitHub-green)](https://github.com/XiaomiRobotics/Xiaomi-Robotics-1)
- **Gemini Robotics 2**: "Gemini Robotics 2 brings whole body intelligence to robots". [![Website](https://img.shields.io/badge/Website-Google_DeepMind-blue)](https://deepmind.google/blog/gemini-robotics-2-brings-whole-body-intelligence-to-robots/)

### Promptable and In-Context Robot Policies

Policies that adapt at inference time through demonstrations, interaction history, or persistent context.

- **ICRT**: "In-Context Imitation Learning via Next-Token Prediction". [![arXiv](https://img.shields.io/badge/arXiv-2408.15980-b31b1b.svg)](https://arxiv.org/abs/2408.15980) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://icrt.dev/)
- **Instant Policy**: "Instant Policy: In-Context Imitation Learning via Graph Diffusion". [![arXiv](https://img.shields.io/badge/arXiv-2411.12633-b31b1b.svg)](https://arxiv.org/abs/2411.12633) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://www.robot-learning.uk/instant-policy)
- **LocoFormer**: "LocoFormer: Generalist Locomotion via Long-context Adaptation". [![arXiv](https://img.shields.io/badge/arXiv-2509.23745-b31b1b.svg)](https://arxiv.org/abs/2509.23745) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://generalist-locomotion.github.io/)
- **BPP**: "Behavior Prompting Policy: Demonstrations as Prompts for Manipulation". [![arXiv](https://img.shields.io/badge/arXiv-2606.30457-b31b1b.svg)](https://arxiv.org/abs/2606.30457) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://behavior-prompting.github.io/)
- **RoboTTT**: "RoboTTT: Context Scaling for Robot Policies". [![arXiv](https://img.shields.io/badge/arXiv-2607.15275-b31b1b.svg)](https://arxiv.org/abs/2607.15275) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://research.nvidia.com/labs/gear/robottt/)
- **Skild S1**: "Introducing S1: In-Context Learning for Robotics". [![Website](https://img.shields.io/badge/Article%2FDemo-Skild_AI-blue)](https://skild.ai/blogs/s1)
- **GEN-1.5**: "GEN-1.5: Embodied Foundation Models are One-Shot Learners". [![Website](https://img.shields.io/badge/Demo-Generalist_AI-blue)](https://generalistai.com/blog/gen-1.5)

### Data and Open Infrastructure

- **RoboNet**: "RoboNet: Large-Scale Multi-Robot Learning". [![arXiv](https://img.shields.io/badge/arXiv-1910.11215-b31b1b.svg)](https://arxiv.org/abs/1910.11215) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://www.robonet.wiki/)
- **BridgeData V2**: "BridgeData V2: A Dataset for Robot Learning at Scale". [![arXiv](https://img.shields.io/badge/arXiv-2308.12952-b31b1b.svg)](https://arxiv.org/abs/2308.12952) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://rail-berkeley.github.io/bridgedata/)
- **DROID**: "DROID: A Large-Scale In-The-Wild Robot Manipulation Dataset". [![arXiv](https://img.shields.io/badge/arXiv-2403.12945-b31b1b.svg)](https://arxiv.org/abs/2403.12945) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://droid-dataset.github.io/)
- **LeRobot**: "LeRobot". [![Website](https://img.shields.io/badge/Website-Hugging_Face-blue)](https://huggingface.co/lerobot) [![Code](https://img.shields.io/badge/Code-GitHub-green)](https://github.com/huggingface/lerobot)
- **OpenVLA-OFT**: "Fine-Tuning Vision-Language-Action Models: Optimizing Speed and Success". [![arXiv](https://img.shields.io/badge/arXiv-2502.19645-b31b1b.svg)](https://arxiv.org/abs/2502.19645) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://openvla-oft.github.io/)
- **AgiBot World / GO-1**: "AgiBot World Colosseo: A Large-scale Manipulation Platform for Scalable and Intelligent Embodied Systems". [![arXiv](https://img.shields.io/badge/arXiv-2503.06669-b31b1b.svg)](https://arxiv.org/abs/2503.06669) [![Website](https://img.shields.io/badge/Website-OpenGO1-blue)](https://opendrivelab.com/OpenGO1/) [![Code](https://img.shields.io/badge/Code-GitHub-green)](https://github.com/OpenDriveLab/AgiBot-World)
- **DreamGen**: "DreamGen: Unlocking Generalization in Robot Learning through Video World Models". [![arXiv](https://img.shields.io/badge/arXiv-2505.12705-b31b1b.svg)](https://arxiv.org/abs/2505.12705) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://research.nvidia.com/labs/gear/dreamgen/) [![Code](https://img.shields.io/badge/Code-GitHub-green)](https://github.com/nvidia/GR00T-dreams)

## Agentic Embodied System Stack

The primary classification axis groups each work by its main system responsibility, with embodied systems foregrounded and relevant precedents placed alongside them.

### Architectures and Harnesses

Architectures, middleware, and runtimes that span multiple stages of the interaction loop.

- **Subsumption Architecture**: "A Robust Layered Control System for a Mobile Robot". [![Paper](https://img.shields.io/badge/Paper-DOI-b31b1b.svg)](https://doi.org/10.1109/JRA.1986.1087032)
- **ATLANTIS**: "Integrating Planning and Reacting in a Heterogeneous Asynchronous Architecture for Controlling Real-World Mobile Robots". [![Paper](https://img.shields.io/badge/Paper-AAAI-b31b1b.svg)](https://cdn.aaai.org/AAAI/1992/AAAI92-125.pdf)
- **3T**: "Experiences with an Architecture for Intelligent, Reactive Agents". [![Paper](https://img.shields.io/badge/Paper-DOI-b31b1b.svg)](https://doi.org/10.1080/095281397147103)
- **Remote Agent**: "Remote Agent: To Boldly Go Where No AI System Has Gone Before". [![Paper](https://img.shields.io/badge/Paper-DOI-b31b1b.svg)](https://doi.org/10.1016/S0004-3702%2898%2900068-X)
- **CRAM**: "CRAM—A Cognitive Robot Abstract Machine for Everyday Manipulation in Human Environments". [![Paper](https://img.shields.io/badge/Paper-DOI-b31b1b.svg)](https://doi.org/10.1109/IROS.2010.5650146) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://www.cram-system.org/)
- **OK-Robot**: "OK-Robot: What Really Matters in Integrating Open-Knowledge Models for Robotics". [![arXiv](https://img.shields.io/badge/arXiv-2401.12202-b31b1b.svg)](https://arxiv.org/abs/2401.12202) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://ok-robot.github.io/)
- **ROS-LLM**: "ROS-LLM: A ROS framework for embodied AI with task feedback and structured reasoning". [![arXiv](https://img.shields.io/badge/arXiv-2406.19741-b31b1b.svg)](https://arxiv.org/abs/2406.19741) [![Code](https://img.shields.io/badge/Code-GitHub-green)](https://github.com/huawei-noah/HEBO/tree/master/ROSLLM)
- **Being-0**: "Being-0: A Humanoid Robotic Agent with Vision-Language Models and Modular Skills". [![arXiv](https://img.shields.io/badge/arXiv-2503.12533-b31b1b.svg)](https://arxiv.org/abs/2503.12533) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://beingbeyond.github.io/Being-0/)
- **RoboNeuron**: "RoboNeuron: A Middle-Layer Infrastructure for Agent-Driven Orchestration in Embodied AI". [![arXiv](https://img.shields.io/badge/arXiv-2512.10394-b31b1b.svg)](https://arxiv.org/abs/2512.10394) [![Code](https://img.shields.io/badge/Code-GitHub-green)](https://github.com/guanweifan/RoboNeuron)
- **VoLo / RoboVoLo**: "VoLo: A Physical Orchestrator for Open-Vocabulary Long-Horizon Manipulation". [![arXiv](https://img.shields.io/badge/arXiv-2606.07723-b31b1b.svg)](https://arxiv.org/abs/2606.07723) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://chicychen.github.io/VoLo/) [![Code](https://img.shields.io/badge/Code-GitHub-green)](https://github.com/NVlabs/VoLoAgent)
- **Harness VLA**: "Harness VLA: Steering Frozen VLAs into Reliable Manipulation Primitives via Memory-Guided Agents". [![arXiv](https://img.shields.io/badge/arXiv-2607.08448-b31b1b.svg)](https://arxiv.org/abs/2607.08448)
- **OpenETA**: "ETA: A New Agentic Paradigm for Embodied Tasks". [![arXiv](https://img.shields.io/badge/arXiv-2608.03924-b31b1b.svg)](https://arxiv.org/abs/2608.03924) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://openmoss.ai/OpenETA/) [![Code](https://img.shields.io/badge/Code-GitHub-green)](https://github.com/OpenMOSS/OpenETA)
- **Thea**: "Towards the Harness of Embodied Agents". [![arXiv](https://img.shields.io/badge/arXiv-2608.11246-b31b1b.svg)](https://arxiv.org/abs/2608.11246) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://eit-hai.github.io/thea/) [![Code](https://img.shields.io/badge/Code-GitHub-green)](https://github.com/EIT-HAI/Thea)

### State, Context, and Memory

Methods for constructing world state and retaining knowledge across steps or episodes.

#### Embodied Systems and Robotics Foundations

- **KnowRob**: "KnowRob—Knowledge Processing for Autonomous Personal Robots". [![Website](https://img.shields.io/badge/Website-Link-blue)](https://www.knowrob.org/)
- **RoboEarth**: "RoboEarth—A World Wide Web for Robots". [![Website](https://img.shields.io/badge/Website-Link-blue)](https://roboearth.ethz.ch/publications/index.html)
- **RoboBrain**: "RoboBrain: Large-Scale Knowledge Engine for Robots". [![arXiv](https://img.shields.io/badge/arXiv-1412.0691-b31b1b.svg)](https://arxiv.org/abs/1412.0691)
- **Statler**: "Statler: State-Maintaining Language Models for Embodied Reasoning". [![arXiv](https://img.shields.io/badge/arXiv-2306.17840-b31b1b.svg)](https://arxiv.org/abs/2306.17840)
- **HELPER**: "Open-Ended Instructable Embodied Agents with Memory-Augmented Large Language Models". [![arXiv](https://img.shields.io/badge/arXiv-2310.15127-b31b1b.svg)](https://arxiv.org/abs/2310.15127) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://helper-agent-llm.github.io/)
- **HELPER-X**: "HELPER-X: A Unified Instructable Embodied Agent to Tackle Four Interactive Vision-Language Domains with Memory-Augmented Language Models". [![arXiv](https://img.shields.io/badge/arXiv-2404.19065-b31b1b.svg)](https://arxiv.org/abs/2404.19065)
- **KARMA**: "KARMA: Augmenting Embodied AI Agents with Long-and-short Term Memory Systems". [![arXiv](https://img.shields.io/badge/arXiv-2409.14908-b31b1b.svg)](https://arxiv.org/abs/2409.14908)
- **ViReSkill**: "ViReSkill: Vision-Grounded Replanning with Skill Memory for LLM-Based Planning in Lifelong Robot Learning". [![arXiv](https://img.shields.io/badge/arXiv-2509.24219-b31b1b.svg)](https://arxiv.org/abs/2509.24219)
- **MEM**: "MEM: Multi-Scale Embodied Memory for Vision Language Action Models". [![arXiv](https://img.shields.io/badge/arXiv-2603.03596-b31b1b.svg)](https://arxiv.org/abs/2603.03596) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://www.pi.website/research/memory)

#### Adjacent Memory Architectures

- **Reflexion**: "Reflexion: Language Agents with Verbal Reinforcement Learning". [![OpenReview](https://img.shields.io/badge/OpenReview-NeurIPS--2023-8E44AD.svg)](https://openreview.net/forum?id=vAElhFcKW6)
- **Generative Agents**: "Generative Agents: Interactive Simulacra of Human Behavior". [![arXiv](https://img.shields.io/badge/arXiv-2304.03442-b31b1b.svg)](https://arxiv.org/abs/2304.03442)
- **ExpeL**: "ExpeL: LLM Agents Are Experiential Learners". [![arXiv](https://img.shields.io/badge/arXiv-2308.10144-b31b1b.svg)](https://arxiv.org/abs/2308.10144) [![Paper](https://img.shields.io/badge/Paper-AAAI--2024-b31b1b.svg)](https://ojs.aaai.org/index.php/AAAI/article/view/29936)
- **MemGPT**: "MemGPT: Towards LLMs as Operating Systems". [![arXiv](https://img.shields.io/badge/arXiv-2310.08560-b31b1b.svg)](https://arxiv.org/abs/2310.08560)

### Planning and Orchestration

Goal decomposition and high-level coordination of plans, actions, and skills.

- **STRIPS**: "STRIPS: A New Approach to the Application of Theorem Proving to Problem Solving". [![Paper](https://img.shields.io/badge/Paper-DOI-b31b1b.svg)](https://doi.org/10.1016/0004-3702%2871%2990010-5)
- **Generalized Robot Plans**: "Learning and Executing Generalized Robot Plans". [![Paper](https://img.shields.io/badge/Paper-DOI-b31b1b.svg)](https://doi.org/10.1016/0004-3702%2872%2990051-3)
- **PRS**: "Reactive Reasoning and Planning". [![Paper](https://img.shields.io/badge/Paper-AAAI-b31b1b.svg)](https://aaai.org/papers/00677-AAAI87-121-reactive-reasoning-and-planning/)
- **PDDL**: "PDDL—The Planning Domain Definition Language". [![Paper](https://img.shields.io/badge/Paper-AIPS--1998-b31b1b.svg)](https://www.cs.cmu.edu/~mmv/planning/readings/98aips-PDDL.pdf)
- **HTAMP**: "Hierarchical Task and Motion Planning in the Now". [![Paper](https://img.shields.io/badge/Paper-ICRA-b31b1b.svg)](https://people.csail.mit.edu/tlp/pdf/2011/hpnICRA11Final.pdf)
- **ROSPlan**: "ROSPlan: Planning in the Robot Operating System". [![Paper](https://img.shields.io/badge/Paper-ICAPS-b31b1b.svg)](https://ojs.aaai.org/index.php/ICAPS/article/view/13699) [![Code](https://img.shields.io/badge/Code-GitHub-green)](https://github.com/KCL-Planning/ROSPlan)
- **Logic-Geometric Programming**: "Logic-Geometric Programming: An Optimization-Based Approach to Combined Task and Motion Planning". [![Paper](https://img.shields.io/badge/Paper-IJCAI-b31b1b.svg)](https://www.ijcai.org/Proceedings/15/Papers/274.pdf)
- **PDDLStream**: "PDDLStream: Integrating Symbolic Planners and Blackbox Samplers via Optimistic Adaptive Planning". [![arXiv](https://img.shields.io/badge/arXiv-1802.08705-b31b1b.svg)](https://arxiv.org/abs/1802.08705)
- **Zero-Shot Planner**: "Language Models as Zero-Shot Planners: Extracting Actionable Knowledge for Embodied Agents". [![arXiv](https://img.shields.io/badge/arXiv-2201.07207-b31b1b.svg)](https://arxiv.org/abs/2201.07207)
- **SayCan**: "Do As I Can, Not As I Say: Grounding Language in Robotic Affordances". [![arXiv](https://img.shields.io/badge/arXiv-2204.01691-b31b1b.svg)](https://arxiv.org/abs/2204.01691) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://say-can.github.io/)
- **ProgPrompt**: "ProgPrompt: Generating Situated Robot Task Plans using Large Language Models". [![arXiv](https://img.shields.io/badge/arXiv-2209.11302-b31b1b.svg)](https://arxiv.org/abs/2209.11302)
- **LLM-Planner**: "LLM-Planner: Few-Shot Grounded Planning for Embodied Agents with Large Language Models". [![arXiv](https://img.shields.io/badge/arXiv-2212.04088-b31b1b.svg)](https://arxiv.org/abs/2212.04088)
- **ASC**: "ASC: Adaptive Skill Coordination for Robotic Mobile Manipulation". [![arXiv](https://img.shields.io/badge/arXiv-2304.00410-b31b1b.svg)](https://arxiv.org/abs/2304.00410)
- **LLM+P**: "LLM+P: Empowering Large Language Models with Optimal Planning Proficiency". [![arXiv](https://img.shields.io/badge/arXiv-2304.11477-b31b1b.svg)](https://arxiv.org/abs/2304.11477) [![Code](https://img.shields.io/badge/Code-GitHub-green)](https://github.com/Cranial-XIX/llm-pddl)
- **SayPlan**: "SayPlan: Grounding Large Language Models using 3D Scene Graphs for Scalable Robot Task Planning". [![arXiv](https://img.shields.io/badge/arXiv-2307.06135-b31b1b.svg)](https://arxiv.org/abs/2307.06135) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://sayplan.github.io/)
- **Reflective Planning**: "Reflective Planning: Vision-Language Models for Multi-Stage Long-Horizon Robotic Manipulation". [![arXiv](https://img.shields.io/badge/arXiv-2502.16707-b31b1b.svg)](https://arxiv.org/abs/2502.16707) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://reflect-vlm.github.io/)
- **Hi Robot**: "Hi Robot: Open-Ended Instruction Following with Hierarchical Vision-Language-Action Models". [![arXiv](https://img.shields.io/badge/arXiv-2502.19417-b31b1b.svg)](https://arxiv.org/abs/2502.19417) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://www.pi.website/research/hirobot)
- **VLA-Reasoner**: "VLA-Reasoner: Empowering Vision-Language-Action Models with Reasoning via Online Monte Carlo Tree Search". [![arXiv](https://img.shields.io/badge/arXiv-2509.22643-b31b1b.svg)](https://arxiv.org/abs/2509.22643)
- **Goal2Skill**: "Goal2Skill: Long-Horizon Manipulation with Adaptive Planning and Reflection". [![arXiv](https://img.shields.io/badge/arXiv-2604.13942-b31b1b.svg)](https://arxiv.org/abs/2604.13942)
- **τ₀-VLA**: "$τ_0$-VLA: a Hierarchical Robot Foundation Model with World-Model-Guided Test-Time Computation". [![arXiv](https://img.shields.io/badge/arXiv-2608.16885-b31b1b.svg)](https://arxiv.org/abs/2608.16885)

### Tools, Programs, and Action Grounding

Representations and interfaces that turn selected capabilities into executable actions.

#### Embodied Systems and Robotics Foundations

- **RAPs**: "An Investigation into Reactive Planning in Complex Domains". [![Paper](https://img.shields.io/badge/Paper-AAAI-b31b1b.svg)](https://cdn.aaai.org/AAAI/1987/AAAI87-036.pdf)
- **Teleo-Reactive Programs**: "Teleo-Reactive Programs for Agent Control". [![arXiv](https://img.shields.io/badge/arXiv-cs%2F9401101-b31b1b.svg)](https://arxiv.org/abs/cs/9401101)
- **Options**: "Between MDPs and Semi-MDPs: A Framework for Temporal Abstraction in Reinforcement Learning". [![Paper](https://img.shields.io/badge/Paper-DOI-b31b1b.svg)](https://doi.org/10.1016/S0004-3702%2899%2900052-1)
- **Walk the Talk / MARCO**: "Walk the Talk: Connecting Language, Knowledge, and Action in Route Instructions". [![Paper](https://img.shields.io/badge/Paper-AAAI-b31b1b.svg)](https://cdn.aaai.org/AAAI/2006/AAAI06-232.pdf)
- **G³**: "Understanding Natural Language Commands for Robotic Navigation and Mobile Manipulation". [![Paper](https://img.shields.io/badge/Paper-AAAI-b31b1b.svg)](https://ojs.aaai.org/index.php/AAAI/article/view/7979)
- **Navigation from Observation**: "Learning to Interpret Natural Language Navigation Instructions from Observations". [![Paper](https://img.shields.io/badge/Paper-AAAI-b31b1b.svg)](https://ojs.aaai.org/index.php/AAAI/article/view/7974)
- **Grounded Semantic Parsing**: "Weakly Supervised Learning of Semantic Parsers for Mapping Instructions to Actions". [![Paper](https://img.shields.io/badge/Paper-TACL-b31b1b.svg)](https://aclanthology.org/Q13-1005/)
- **Behavior Trees**: "Behavior Trees in Robotics and AI: An Introduction". [![arXiv](https://img.shields.io/badge/arXiv-1709.00084-b31b1b.svg)](https://arxiv.org/abs/1709.00084)
- **Code as Policies**: "Code as Policies: Language Model Programs for Embodied Control". [![arXiv](https://img.shields.io/badge/arXiv-2209.07753-b31b1b.svg)](https://arxiv.org/abs/2209.07753) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://code-as-policies.github.io/)
- **ChatGPT for Robotics**: "ChatGPT for Robotics: Design Principles and Model Abilities". [![Paper](https://img.shields.io/badge/Paper-MSR--TR--2023--8-b31b1b.svg)](https://www.microsoft.com/en-us/research/publication/chatgpt-for-robotics-design-principles-and-model-abilities/) [![Code](https://img.shields.io/badge/Code-GitHub-green)](https://github.com/microsoft/PromptCraft-Robotics)
- **VoxPoser**: "VoxPoser: Composable 3D Value Maps for Robotic Manipulation with Language Models". [![arXiv](https://img.shields.io/badge/arXiv-2307.05973-b31b1b.svg)](https://arxiv.org/abs/2307.05973) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://voxposer.github.io/)
- **ReKep**: "ReKep: Spatio-Temporal Reasoning of Relational Keypoint Constraints for Robotic Manipulation". [![arXiv](https://img.shields.io/badge/arXiv-2409.01652-b31b1b.svg)](https://arxiv.org/abs/2409.01652) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://rekep-robot.github.io/)
- **VLAs-as-Tools**: "Towards Long-horizon Embodied Agents with Tool-Aligned Vision-Language-Action Models". [![arXiv](https://img.shields.io/badge/arXiv-2605.13119-b31b1b.svg)](https://arxiv.org/abs/2605.13119)
- **Project Fetch: Phase Two**: "Project Fetch: Phase two". [![Website](https://img.shields.io/badge/Experiment-Anthropic-blue)](https://www.anthropic.com/news/project-fetch-phase-two)

#### Adjacent Agent Interfaces

- **MRKL Systems**: "MRKL Systems: A modular, neuro-symbolic architecture that combines large language models, external knowledge sources and discrete reasoning". [![arXiv](https://img.shields.io/badge/arXiv-2205.00445-b31b1b.svg)](https://arxiv.org/abs/2205.00445)
- **Toolformer**: "Toolformer: Language Models Can Teach Themselves to Use Tools". [![arXiv](https://img.shields.io/badge/arXiv-2302.04761-b31b1b.svg)](https://arxiv.org/abs/2302.04761)
- **MM-REACT**: "MM-REACT: Prompting ChatGPT for Multimodal Reasoning and Action". [![arXiv](https://img.shields.io/badge/arXiv-2303.11381-b31b1b.svg)](https://arxiv.org/abs/2303.11381)
- **HuggingGPT**: "HuggingGPT: Solving AI Tasks with ChatGPT and its Friends in Hugging Face". [![Paper](https://img.shields.io/badge/Paper-NeurIPS--2023-b31b1b.svg)](https://papers.nips.cc/paper_files/paper/2023/hash/77c33e6a367922d003ff102ffb92b658-Abstract-Conference.html)
- **CodeAct**: "Executable Code Actions Elicit Better LLM Agents". [![Paper](https://img.shields.io/badge/Paper-ICML--2024-b31b1b.svg)](https://proceedings.mlr.press/v235/wang24h.html)
- **SWE-agent**: "SWE-agent: Agent-Computer Interfaces Enable Automated Software Engineering". [![arXiv](https://img.shields.io/badge/arXiv-2405.15793-b31b1b.svg)](https://arxiv.org/abs/2405.15793)
- **Model Context Protocol**: "Model Context Protocol". [![Website](https://img.shields.io/badge/Website-MCP-blue)](https://modelcontextprotocol.io/)

### Monitoring, Verification, and Recovery

Mechanisms for tracking progress, verifying outcomes, and choosing recovery or termination.

#### Embodied Systems and Robotics Foundations

- **IPEM**: "Integrating Planning, Execution and Monitoring". [![Paper](https://img.shields.io/badge/Paper-AAAI-b31b1b.svg)](https://cdn.aaai.org/AAAI/1988/AAAI88-015.pdf)
- **Inner Monologue**: "Inner Monologue: Embodied Reasoning through Planning with Language Models". [![arXiv](https://img.shields.io/badge/arXiv-2207.05608-b31b1b.svg)](https://arxiv.org/abs/2207.05608) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://innermonologue.github.io/)
- **REFLECT**: "REFLECT: Summarizing Robot Experiences for Failure Explanation and Correction". [![arXiv](https://img.shields.io/badge/arXiv-2306.15724-b31b1b.svg)](https://arxiv.org/abs/2306.15724)
- **DoReMi**: "DoReMi: Grounding Language Model by Detecting and Recovering from Plan-Execution Misalignment". [![arXiv](https://img.shields.io/badge/arXiv-2307.00329-b31b1b.svg)](https://arxiv.org/abs/2307.00329) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://sites.google.com/view/doremi-paper/)
- **BrainBody-LLM**: "Grounding LLMs For Robot Task Planning Using Closed-loop State Feedback". [![arXiv](https://img.shields.io/badge/arXiv-2402.08546-b31b1b.svg)](https://arxiv.org/abs/2402.08546)
- **VASO**: "VASO: Formally Verifiable Self-Evolving Skills for Physical AI Agents". [![arXiv](https://img.shields.io/badge/arXiv-2606.05395-b31b1b.svg)](https://arxiv.org/abs/2606.05395)

#### Adjacent Verification and Feedback

- **Training Verifiers**: "Training Verifiers to Solve Math Word Problems". [![arXiv](https://img.shields.io/badge/arXiv-2110.14168-b31b1b.svg)](https://arxiv.org/abs/2110.14168)
- **ReAct**: "ReAct: Synergizing Reasoning and Acting in Language Models". [![OpenReview](https://img.shields.io/badge/OpenReview-ICLR--2023-8E44AD.svg)](https://openreview.net/forum?id=WE_vluYUL-X)
- **Let's Verify Step by Step**: "Let's Verify Step by Step". [![arXiv](https://img.shields.io/badge/arXiv-2305.20050-b31b1b.svg)](https://arxiv.org/abs/2305.20050)
- **LLM Critics**: "LLM Critics Help Catch LLM Bugs". [![Paper](https://img.shields.io/badge/Paper-Technical_Report-b31b1b.svg)](https://cdn.openai.com/llm-critics-help-catch-llm-bugs-paper.pdf)

### Skill Learning and Lifelong Adaptation

Methods for acquiring and reusing skills across tasks, environments, and embodiments.

- **Lifelong Robot Learning**: "Lifelong Robot Learning". [![Paper](https://img.shields.io/badge/Paper-DOI-b31b1b.svg)](https://doi.org/10.1016/0921-8890%2895%2900004-Y)
- **Portable Options**: "Building Portable Options: Skill Transfer in Reinforcement Learning". [![Paper](https://img.shields.io/badge/Paper-IJCAI-b31b1b.svg)](https://www.ijcai.org/Proceedings/07/Papers/144.pdf)
- **Robot Learning from Demonstration Survey**: "A Survey of Robot Learning from Demonstration". [![Paper](https://img.shields.io/badge/Paper-DOI-b31b1b.svg)](https://doi.org/10.1016/j.robot.2008.10.024)
- **Neural Task Programming**: "Neural Task Programming: Learning to Generalize Across Hierarchical Tasks". [![arXiv](https://img.shields.io/badge/arXiv-1710.01813-b31b1b.svg)](https://arxiv.org/abs/1710.01813)
- **Voyager**: "Voyager: An Open-Ended Embodied Agent with Large Language Models". [![arXiv](https://img.shields.io/badge/arXiv-2305.16291-b31b1b.svg)](https://arxiv.org/abs/2305.16291) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://voyager.minedojo.org/)
- **RoboCat**: "RoboCat: A Self-Improving Generalist Agent for Robotic Manipulation". [![arXiv](https://img.shields.io/badge/arXiv-2306.11706-b31b1b.svg)](https://arxiv.org/abs/2306.11706)
- **LRLL**: "Lifelong Robot Library Learning: Bootstrapping Composable and Generalizable Skills for Embodied Control with Language Models". [![arXiv](https://img.shields.io/badge/arXiv-2406.18746-b31b1b.svg)](https://arxiv.org/abs/2406.18746) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://gtziafas.github.io/LRLL_project/)
- **ASPIRE**: "ASPIRE: Agentic /Skills Discovery for Robotics". [![arXiv](https://img.shields.io/badge/arXiv-2607.00272-b31b1b.svg)](https://arxiv.org/abs/2607.00272) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://research.nvidia.com/labs/gear/aspire/) [![Code](https://img.shields.io/badge/Code-GitHub-green)](https://github.com/NVlabs/ASPIRE)
- **APPL**: "Agent Priors-guided Policy Learning". [![arXiv](https://img.shields.io/badge/arXiv-2609.35690-b31b1b.svg)](https://arxiv.org/abs/2609.35690) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://agentics-robotics.github.io/APPL/) [![Code](https://img.shields.io/badge/Code-GitHub-green)](https://github.com/Agentics-robotics/Agent-Priors-guided-Policy-Learning)

### Autonomous System and Policy Improvement

Feedback-driven loops that improve policies and their supporting data, tools, or runtimes.

#### Embodied Data, Policy, and Harness Loops

- **GenSim**: "GenSim: Generating Robotic Simulation Tasks via Large Language Models". [![arXiv](https://img.shields.io/badge/arXiv-2310.01361-b31b1b.svg)](https://arxiv.org/abs/2310.01361)
- **Eureka**: "Eureka: Human-Level Reward Design via Coding Large Language Models". [![arXiv](https://img.shields.io/badge/arXiv-2310.12931-b31b1b.svg)](https://arxiv.org/abs/2310.12931) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://eureka-research.github.io/)
- **RoboGen**: "RoboGen: Towards Unleashing Infinite Data for Automated Robot Learning via Generative Simulation". [![arXiv](https://img.shields.io/badge/arXiv-2311.01455-b31b1b.svg)](https://arxiv.org/abs/2311.01455)
- **AutoRT**: "AutoRT: Embodied Foundation Models for Large Scale Orchestration of Robotic Agents". [![arXiv](https://img.shields.io/badge/arXiv-2401.12963-b31b1b.svg)](https://arxiv.org/abs/2401.12963)
- **DrEureka**: "DrEureka: Language Model Guided Sim-To-Real Transfer". [![arXiv](https://img.shields.io/badge/arXiv-2406.01967-b31b1b.svg)](https://arxiv.org/abs/2406.01967) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://eureka-research.github.io/dr-eureka/)
- **π*₀.₆ / RECAP**: "$π^{*}_{0.6}$: a VLA That Learns From Experience". [![arXiv](https://img.shields.io/badge/arXiv-2511.14759-b31b1b.svg)](https://arxiv.org/abs/2511.14759) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://www.pi.website/blog/pistar06)
- **RoboClaw**: "RoboClaw: An Agentic Framework for Scalable Long-Horizon Robotic Tasks". [![arXiv](https://img.shields.io/badge/arXiv-2603.11558-b31b1b.svg)](https://arxiv.org/abs/2603.11558)
- **HARBOR**: "HARBOR: A Harness Framework for Agentic Robot Reinforcement Learning". [![arXiv](https://img.shields.io/badge/arXiv-2606.08610-b31b1b.svg)](https://arxiv.org/abs/2606.08610)
- **RHO**: "RHO: Your Coding Agent is Secretly a Roboticist". [![arXiv](https://img.shields.io/badge/arXiv-2606.16458-b31b1b.svg)](https://arxiv.org/abs/2606.16458) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://rho-robotics.github.io/) [![Code](https://img.shields.io/badge/Code-GitHub-green)](https://github.com/KE7/HELIX)
- **RATs**: "Playful Agentic Robot Learning". [![arXiv](https://img.shields.io/badge/arXiv-2606.19419-b31b1b.svg)](https://arxiv.org/abs/2606.19419) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://playful-rats.github.io/) [![Code](https://img.shields.io/badge/Code-GitHub-green)](https://github.com/Playful-RATs/RATs)
- **ENPIRE**: "ENPIRE: Agentic Robot Policy Self-Improvement in the Real World". [![arXiv](https://img.shields.io/badge/arXiv-2606.19980-b31b1b.svg)](https://arxiv.org/abs/2606.19980) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://research.nvidia.com/labs/gear/enpire/)
- **GaP**: "GaP: A Graph-as-Policy Multi-Agent Self-Learning Harness For Variational Automation Tasks". [![arXiv](https://img.shields.io/badge/arXiv-2607.05369-b31b1b.svg)](https://arxiv.org/abs/2607.05369) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://graph-robots.github.io/gap/) [![Code](https://img.shields.io/badge/Code-GitHub-green)](https://github.com/graph-robots/graph-as-policy)
- **SHAPER**: "Self-Evolving Embodied Agents via Skill-Harness Evolution". [![arXiv](https://img.shields.io/badge/arXiv-2608.11350-b31b1b.svg)](https://arxiv.org/abs/2608.11350)
- **Zetta ζ**: "Zetta $ζ$: An Efficient Closed-Loop Embodied Harness for Self-Evolving Physical Intelligence". [![arXiv](https://img.shields.io/badge/arXiv-2608.16590-b31b1b.svg)](https://arxiv.org/abs/2608.16590) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://air-embodied-brain.github.io/zetta/)
- **Agentic Push-T**: "Revisiting the “Push-T” Robot Manipulation Task with Agentic Robotics". [![arXiv](https://img.shields.io/badge/arXiv-2608.18227-b31b1b.svg)](https://arxiv.org/abs/2608.18227)

#### Adjacent Autonomous-Agent Precedents

- **Self-Refine**: "Self-Refine: Iterative Refinement with Self-Feedback". [![Paper](https://img.shields.io/badge/Paper-NeurIPS--2023-b31b1b.svg)](https://papers.nips.cc/paper_files/paper/2023/hash/91edff07232fb1b55a505a9e9f6c0ff3-Abstract-Conference.html)
- **Coscientist**: "Autonomous Chemical Research with Large Language Models". [![Paper](https://img.shields.io/badge/Paper-Nature-b31b1b.svg)](https://www.nature.com/articles/s41586-023-06792-0)
- **ChemCrow**: "ChemCrow: Augmenting large-language models with chemistry tools". [![arXiv](https://img.shields.io/badge/arXiv-2304.05376-b31b1b.svg)](https://arxiv.org/abs/2304.05376) [![Paper](https://img.shields.io/badge/Paper-Nature_Machine_Intelligence-b31b1b.svg)](https://www.nature.com/articles/s42256-024-00832-8)
- **DSPy**: "DSPy: Compiling Declarative Language Model Calls into Self-Improving Pipelines". [![arXiv](https://img.shields.io/badge/arXiv-2310.03714-b31b1b.svg)](https://arxiv.org/abs/2310.03714)
- **A-Lab**: "An autonomous laboratory for the accelerated synthesis of inorganic materials". [![Paper](https://img.shields.io/badge/Paper-Nature-b31b1b.svg)](https://www.nature.com/articles/s41586-023-06734-w)

### Multi-Agent, Multi-Robot, and Fleet Coordination

#### Embodied and Multi-Robot Systems

- **ALLIANCE**: "ALLIANCE: An Architecture for Fault Tolerant Multirobot Cooperation". [![Paper](https://img.shields.io/badge/Paper-IEEE-b31b1b.svg)](https://ieeexplore.ieee.org/document/681242)
- **CoELA**: "Building Cooperative Embodied Agents Modularly with Large Language Models". [![arXiv](https://img.shields.io/badge/arXiv-2307.02485-b31b1b.svg)](https://arxiv.org/abs/2307.02485) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://umass-embodied-agi.github.io/CoELA/) [![Code](https://img.shields.io/badge/Code-GitHub-green)](https://github.com/UMass-Embodied-AGI/CoELA)
- **RoCo**: "RoCo: Dialectic Multi-Robot Collaboration with Large Language Models". [![arXiv](https://img.shields.io/badge/arXiv-2307.04738-b31b1b.svg)](https://arxiv.org/abs/2307.04738) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://project-roco.github.io/) [![Code](https://img.shields.io/badge/Code-GitHub-green)](https://github.com/MandiZhao/robot-collab)
- **SMART-LLM**: "SMART-LLM: Smart Multi-Agent Robot Task Planning using Large Language Models". [![arXiv](https://img.shields.io/badge/arXiv-2309.10062-b31b1b.svg)](https://arxiv.org/abs/2309.10062) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://sites.google.com/view/smart-llm/)
- **COHERENT**: "COHERENT: Collaboration of Heterogeneous Multi-Robot System with Large Language Models". [![arXiv](https://img.shields.io/badge/arXiv-2409.15146-b31b1b.svg)](https://arxiv.org/abs/2409.15146) [![Code](https://img.shields.io/badge/Code-GitHub-green)](https://github.com/MrKeee/COHERENT)
- **EMOS**: "EMOS: Embodiment-aware Heterogeneous Multi-robot Operating System with LLM Agents". [![arXiv](https://img.shields.io/badge/arXiv-2410.22662-b31b1b.svg)](https://arxiv.org/abs/2410.22662)
- **HMCF**: "HMCF: A Human-in-the-loop Multi-Robot Collaboration Framework Based on Large Language Models". [![arXiv](https://img.shields.io/badge/arXiv-2505.00820-b31b1b.svg)](https://arxiv.org/abs/2505.00820)
- **RAI**: "RAI: Flexible Agent Framework for Embodied AI". [![arXiv](https://img.shields.io/badge/arXiv-2505.07532-b31b1b.svg)](https://arxiv.org/abs/2505.07532)
- **Embodied World-Model Alignment**: "Embodied Multi-Agent Coordination by Aligning World Models Through Dialogue". [![arXiv](https://img.shields.io/badge/arXiv-2605.12920-b31b1b.svg)](https://arxiv.org/abs/2605.12920)
- **LLawCo**: "LLawCo: Learning Laws of Cooperation for Modeling Embodied Multi-Agent Behavior". [![arXiv](https://img.shields.io/badge/arXiv-2606.28182-b31b1b.svg)](https://arxiv.org/abs/2606.28182)

#### Adjacent Multi-Agent References

- **CAMEL**: "CAMEL: Communicative Agents for &quot;Mind&quot; Exploration of Large Scale Language Model Society". [![arXiv](https://img.shields.io/badge/arXiv-2303.17760-b31b1b.svg)](https://arxiv.org/abs/2303.17760)
- **ChatDev**: "ChatDev: Communicative Agents for Software Development". [![arXiv](https://img.shields.io/badge/arXiv-2307.07924-b31b1b.svg)](https://arxiv.org/abs/2307.07924) [![Paper](https://img.shields.io/badge/Paper-ACL--2024-b31b1b.svg)](https://aclanthology.org/2024.acl-long.810/)
- **MetaGPT**: "MetaGPT: Meta Programming for A Multi-Agent Collaborative Framework". [![OpenReview](https://img.shields.io/badge/OpenReview-ICLR--2024-8E44AD.svg)](https://openreview.net/forum?id=VtmBAGCN7o)
- **AutoGen**: "AutoGen: Enabling Next-Gen LLM Applications via Multi-Agent Conversation". [![arXiv](https://img.shields.io/badge/arXiv-2308.08155-b31b1b.svg)](https://arxiv.org/abs/2308.08155)
- **Agent2Agent Protocol**: "Agent2Agent Protocol". [![Website](https://img.shields.io/badge/Website-A2A-blue)](https://a2a-protocol.org/)

## Environments and Evaluation

Resources are grouped by the system properties they expose.

### Platforms and Task Suites

- **AI2-THOR**: "AI2-THOR: An Interactive 3D Environment for Visual AI". [![arXiv](https://img.shields.io/badge/arXiv-1712.05474-b31b1b.svg)](https://arxiv.org/abs/1712.05474) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://ai2thor.allenai.org/)
- **VirtualHome**: "VirtualHome: Simulating Household Activities via Programs". [![arXiv](https://img.shields.io/badge/arXiv-1806.07011-b31b1b.svg)](https://arxiv.org/abs/1806.07011)
- **Habitat**: "Habitat: A Platform for Embodied AI Research". [![arXiv](https://img.shields.io/badge/arXiv-1904.01201-b31b1b.svg)](https://arxiv.org/abs/1904.01201) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://aihabitat.org/)
- **RLBench**: "RLBench: The Robot Learning Benchmark & Learning Environment". [![arXiv](https://img.shields.io/badge/arXiv-1909.12271-b31b1b.svg)](https://arxiv.org/abs/1909.12271)
- **ManiSkill**: "ManiSkill: Generalizable Manipulation Skill Benchmark with Large-Scale Demonstrations". [![arXiv](https://img.shields.io/badge/arXiv-2107.14483-b31b1b.svg)](https://arxiv.org/abs/2107.14483)
- **BEHAVIOR**: "BEHAVIOR: Benchmark for Everyday Household Activities in Virtual, Interactive, and Ecological Environments". [![arXiv](https://img.shields.io/badge/arXiv-2108.03332-b31b1b.svg)](https://arxiv.org/abs/2108.03332) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://behavior.stanford.edu/)
- **Habitat 3.0**: "Habitat 3.0: A Co-Habitat for Humans, Avatars and Robots". [![arXiv](https://img.shields.io/badge/arXiv-2310.13724-b31b1b.svg)](https://arxiv.org/abs/2310.13724)
- **BEHAVIOR-1K / OmniGibson**: "BEHAVIOR-1K: A Human-Centered, Embodied AI Benchmark with 1,000 Everyday Activities and Realistic Simulation". [![arXiv](https://img.shields.io/badge/arXiv-2403.09227-b31b1b.svg)](https://arxiv.org/abs/2403.09227) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://behavior.stanford.edu/)
- **RoboCasa**: "RoboCasa: Large-Scale Simulation of Everyday Tasks for Generalist Robots". [![arXiv](https://img.shields.io/badge/arXiv-2406.02523-b31b1b.svg)](https://arxiv.org/abs/2406.02523) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://robocasa.ai/)
- **RoboVerse / MetaSim**: "RoboVerse: Towards a Unified Platform, Dataset and Benchmark for Scalable and Generalizable Robot Learning". [![arXiv](https://img.shields.io/badge/arXiv-2504.18904-b31b1b.svg)](https://arxiv.org/abs/2504.18904) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://roboverseorg.github.io/) [![Code](https://img.shields.io/badge/Code-GitHub-green)](https://github.com/RoboVerseOrg/RoboVerse)
- **RoboTwin 2.0**: "RoboTwin 2.0: A Scalable Data Generator and Benchmark with Strong Domain Randomization for Robust Bimanual Robotic Manipulation". [![arXiv](https://img.shields.io/badge/arXiv-2506.18088-b31b1b.svg)](https://arxiv.org/abs/2506.18088) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://robotwin-platform.github.io/) [![Plus](https://img.shields.io/badge/Project-2.0--Plus-blue)](https://robot-robustness.github.io/RoboTwin2.0-Plus/) [![Code](https://img.shields.io/badge/Code-GitHub-green)](https://github.com/RoboTwin-Platform/RoboTwin)
- **MolmoSpaces**: "MolmoSpaces: A Large-Scale Open Ecosystem for Robot Navigation and Manipulation". [![arXiv](https://img.shields.io/badge/arXiv-2602.11337-b31b1b.svg)](https://arxiv.org/abs/2602.11337) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://molmospaces.allen.ai/) [![Code](https://img.shields.io/badge/Code-GitHub-green)](https://github.com/allenai/molmospaces)
- **RoboCasa365**: "RoboCasa365: A Large-Scale Simulation Framework for Training and Benchmarking Generalist Robots". [![arXiv](https://img.shields.io/badge/arXiv-2603.04356-b31b1b.svg)](https://arxiv.org/abs/2603.04356)

### Evaluation Infrastructure and Real-World Arenas

Infrastructure for evaluating complete policies and agent systems across tasks, embodiments, and physical sites.

- **SIMPLER**: "Evaluating Real-World Robot Manipulation Policies in Simulation". [![arXiv](https://img.shields.io/badge/arXiv-2405.05941-b31b1b.svg)](https://arxiv.org/abs/2405.05941) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://simpler-env.github.io/) [![Code](https://img.shields.io/badge/Code-GitHub-green)](https://github.com/simpler-env/SimplerEnv)
- **RoboArena**: "RoboArena: Distributed Real-World Evaluation of Generalist Robot Policies". [![arXiv](https://img.shields.io/badge/arXiv-2506.18123-b31b1b.svg)](https://arxiv.org/abs/2506.18123) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://robo-arena.github.io/) [![Code](https://img.shields.io/badge/Code-GitHub-green)](https://github.com/robo-arena/roboarena)
- **RoboChallenge / Table30**: "RoboChallenge: Large-scale Real-robot Evaluation of Embodied Policies". [![arXiv](https://img.shields.io/badge/arXiv-2510.17950-b31b1b.svg)](https://arxiv.org/abs/2510.17950) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://robochallenge.ai/)
- **Isaac Lab-Arena**: "NVIDIA Isaac Lab-Arena". [![Website](https://img.shields.io/badge/Website-NVIDIA-blue)](https://developer.nvidia.com/isaac/lab-arena) [![Code](https://img.shields.io/badge/Code-GitHub-green)](https://github.com/isaac-sim/IsaacLab-Arena)
- **vla-eval**: "vla-eval: A Unified Evaluation Harness for Vision-Language-Action Models". [![arXiv](https://img.shields.io/badge/arXiv-2603.13966-b31b1b.svg)](https://arxiv.org/abs/2603.13966) [![Leaderboard](https://img.shields.io/badge/Leaderboard-Link-blue)](https://allenai.github.io/vla-evaluation-harness/leaderboard/) [![Code](https://img.shields.io/badge/Code-GitHub-green)](https://github.com/allenai/vla-evaluation-harness)
- **CaP-X**: "CaP-X: A Framework for Benchmarking and Improving Coding Agents for Robot Manipulation". [![arXiv](https://img.shields.io/badge/arXiv-2603.22435-b31b1b.svg)](https://arxiv.org/abs/2603.22435) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://capgym.github.io/) [![Code](https://img.shields.io/badge/Code-GitHub-green)](https://github.com/capgym/cap-x)
- **ManipArena**: "ManipArena: Comprehensive Real-world Evaluation of Reasoning-Oriented Generalist Robot Manipulation". [![arXiv](https://img.shields.io/badge/arXiv-2603.28545-b31b1b.svg)](https://arxiv.org/abs/2603.28545) [![Code](https://img.shields.io/badge/Code-GitHub-green)](https://github.com/maniparena/maniparena-repo)
- **SimFoundry**: "SimFoundry: Modular and Automated Scene Generation for Policy Learning and Evaluation". [![arXiv](https://img.shields.io/badge/arXiv-2606.28276-b31b1b.svg)](https://arxiv.org/abs/2606.28276) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://research.nvidia.com/labs/gear/simfoundry/) [![Code](https://img.shields.io/badge/Code-GitHub-green)](https://github.com/NVlabs/SimFoundry)
- **RoboDojo**: "RoboDojo: A Unified Sim-and-Real Benchmark for Comprehensive Evaluation of Generalist Robot Manipulation Policies". [![arXiv](https://img.shields.io/badge/arXiv-2607.04434-b31b1b.svg)](https://arxiv.org/abs/2607.04434) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://robodojo-benchmark.com/) [![Code](https://img.shields.io/badge/Code-GitHub-green)](https://github.com/RoboDojo-Benchmark/RoboDojo)
- **Embody / Claude Plays Robotics**: "How Claude performs on robotics tasks". [![Website](https://img.shields.io/badge/Report-Anthropic-blue)](https://www.anthropic.com/research/claude-plays-robotics)

### Long-Horizon, Language, Memory, and Collaboration

[VoLo](https://arxiv.org/abs/2606.07723) is listed under Architectures and Harnesses for its primary system contribution.

- **ALFRED**: "ALFRED: A Benchmark for Interpreting Grounded Instructions for Everyday Tasks". [![arXiv](https://img.shields.io/badge/arXiv-1912.01734-b31b1b.svg)](https://arxiv.org/abs/1912.01734)
- **ALFWorld**: "ALFWorld: Aligning Text and Embodied Environments for Interactive Learning". [![arXiv](https://img.shields.io/badge/arXiv-2010.03768-b31b1b.svg)](https://arxiv.org/abs/2010.03768)
- **TEACh**: "TEACh: Task-driven Embodied Agents that Chat". [![arXiv](https://img.shields.io/badge/arXiv-2110.00534-b31b1b.svg)](https://arxiv.org/abs/2110.00534)
- **CALVIN**: "CALVIN: A Benchmark for Language-Conditioned Policy Learning for Long-Horizon Robot Manipulation Tasks". [![arXiv](https://img.shields.io/badge/arXiv-2112.03227-b31b1b.svg)](https://arxiv.org/abs/2112.03227)
- **MineDojo**: "MineDojo: Building Open-Ended Embodied Agents with Internet-Scale Knowledge". [![arXiv](https://img.shields.io/badge/arXiv-2206.08853-b31b1b.svg)](https://arxiv.org/abs/2206.08853) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://minedojo.org/)
- **LIBERO**: "LIBERO: Benchmarking Knowledge Transfer for Lifelong Robot Learning". [![arXiv](https://img.shields.io/badge/arXiv-2306.03310-b31b1b.svg)](https://arxiv.org/abs/2306.03310) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://libero-project.github.io/)
- **PARTNR**: "PARTNR: A Benchmark for Planning and Reasoning in Embodied Multi-agent Tasks". [![arXiv](https://img.shields.io/badge/arXiv-2411.00081-b31b1b.svg)](https://arxiv.org/abs/2411.00081)
- **VLABench**: "VLABench: A Large-Scale Benchmark for Language-Conditioned Robotics Manipulation with Long-Horizon Reasoning Tasks". [![arXiv](https://img.shields.io/badge/arXiv-2412.18194-b31b1b.svg)](https://arxiv.org/abs/2412.18194)
- **MIKASA-Robo**: "Memory, Benchmark & Robots: A Benchmark for Solving Complex Tasks with Reinforcement Learning". [![arXiv](https://img.shields.io/badge/arXiv-2502.10550-b31b1b.svg)](https://arxiv.org/abs/2502.10550) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://mikasarobo.github.io/) [![Code](https://img.shields.io/badge/Code-GitHub-green)](https://github.com/CognitiveAISystems/MIKASA-Robo)
- **RoboCerebra**: "RoboCerebra: A Large-scale Benchmark for Long-horizon Robotic Manipulation Evaluation". [![arXiv](https://img.shields.io/badge/arXiv-2506.06677-b31b1b.svg)](https://arxiv.org/abs/2506.06677) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://robocerebra.github.io/)
- **LongBench**: "LongBench: Evaluating Robotic Manipulation Policies on Real-World Long-Horizon Tasks". [![arXiv](https://img.shields.io/badge/arXiv-2604.16788-b31b1b.svg)](https://arxiv.org/abs/2604.16788)
- **RoboMemArena**: "RoboMemArena: A Comprehensive and Challenging Robotic Memory Benchmark". [![arXiv](https://img.shields.io/badge/arXiv-2605.10921-b31b1b.svg)](https://arxiv.org/abs/2605.10921) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://robomemarena.github.io/) [![Code](https://img.shields.io/badge/Code-GitHub-green)](https://github.com/OpenHelix-Team/RoboMemArena)
- **ESI-Bench**: "ESI-Bench: Towards Embodied Spatial Intelligence that Closes the Perception-Action Loop". [![arXiv](https://img.shields.io/badge/arXiv-2605.18746-b31b1b.svg)](https://arxiv.org/abs/2605.18746)
- **RoboGraph / Task-State Horizons**: "Compiling and Benchmarking Task-State Horizons for Embodied Agents". [![arXiv](https://img.shields.io/badge/arXiv-2608.08036-b31b1b.svg)](https://arxiv.org/abs/2608.08036)

### Robustness and System Evaluation

Evaluations of system behavior under distribution shift, interface changes, and cross-site variation.

#### Embodied System Evaluation

- **Embodied Agent Interface**: "Embodied Agent Interface: Benchmarking LLMs for Embodied Decision Making". [![arXiv](https://img.shields.io/badge/arXiv-2410.07166-b31b1b.svg)](https://arxiv.org/abs/2410.07166)
- **EmbodiedBench**: "EmbodiedBench: Comprehensive Benchmarking Multi-modal Large Language Models for Vision-Driven Embodied Agents". [![arXiv](https://img.shields.io/badge/arXiv-2502.09560-b31b1b.svg)](https://arxiv.org/abs/2502.09560) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://embodiedbench.github.io/)
- **LIBERO-PRO**: "LIBERO-PRO: Towards Robust and Fair Evaluation of Vision-Language-Action Models Beyond Memorization". [![arXiv](https://img.shields.io/badge/arXiv-2510.03827-b31b1b.svg)](https://arxiv.org/abs/2510.03827) [![Code](https://img.shields.io/badge/Code-GitHub-green)](https://github.com/Zxy-MLlab/LIBERO-PRO)
- **LIBERO-Plus**: "LIBERO-Plus: In-depth Robustness Analysis of Vision-Language-Action Models". [![arXiv](https://img.shields.io/badge/arXiv-2510.13626-b31b1b.svg)](https://arxiv.org/abs/2510.13626) [![Code](https://img.shields.io/badge/Code-GitHub-green)](https://github.com/sylvestf/LIBERO-plus)
- **RobotArena ∞**: "RobotArena $∞$: Scalable Robot Benchmarking via Real-to-Sim Translation". [![arXiv](https://img.shields.io/badge/arXiv-2510.23571-b31b1b.svg)](https://arxiv.org/abs/2510.23571) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://robotarenainf.github.io/) [![Code](https://img.shields.io/badge/Code-GitHub-green)](https://github.com/offjangir/RobotArena)
- **VLA-Arena**: "VLA-Arena: An Open-Source Framework for Benchmarking Vision-Language-Action Models". [![arXiv](https://img.shields.io/badge/arXiv-2512.22539-b31b1b.svg)](https://arxiv.org/abs/2512.22539) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://vla-arena.github.io/) [![Code](https://img.shields.io/badge/Code-GitHub-green)](https://github.com/PKU-Alignment/VLA-Arena)
- **SafeVLA-Bench**: "SafeVLA-Bench: A Benchmark for the Success-Safety Gap in Vision-Language-Action Models". [![arXiv](https://img.shields.io/badge/arXiv-2606.00773-b31b1b.svg)](https://arxiv.org/abs/2606.00773) [![Website](https://img.shields.io/badge/Website-Link-blue)](https://safevla.org/)
- **ASIMOV-Agentic**: "Asimov Agentic Safety Evaluation". [![Dataset](https://img.shields.io/badge/Dataset-Hugging_Face-yellow)](https://huggingface.co/datasets/google/asimov_agentic)

#### Adjacent Digital-Agent Evaluation

- **WebArena**: "WebArena: A Realistic Web Environment for Building Autonomous Agents". [![OpenReview](https://img.shields.io/badge/OpenReview-ICLR--2024-8E44AD.svg)](https://openreview.net/forum?id=oKn9c6ytLx)
- **AgentBench**: "AgentBench: Evaluating LLMs as Agents". [![OpenReview](https://img.shields.io/badge/OpenReview-ICLR--2024-8E44AD.svg)](https://openreview.net/forum?id=zAdUB0aCTQ)
- **OSWorld**: "OSWorld: Benchmarking Multimodal Agents for Open-Ended Tasks in Real Computer Environments". [![OpenReview](https://img.shields.io/badge/OpenReview-NeurIPS--2024-8E44AD.svg)](https://openreview.net/forum?id=tN61DTr4Ed)

## Challenges and Open Questions

Embodied agents require reliable state, execution, verification, and recovery under uncertain physical interaction. The table summarizes the main harness-level challenges.

| Challenge | Why it matters for an embodied harness | Useful research direction |
| --- | --- | --- |
| State and partial observation | Physical state is partial, noisy, and viewpoint-dependent. | Persistent scene/world models, active perception, uncertainty-aware context |
| Action interfaces | Natural-language plans omit safety and dynamic feasibility. | Typed tools, skill contracts, preconditions/effects, capability discovery |
| Verification and termination | Controller completion provides weak evidence of physical goal success. | Independent success detectors, progress monitors, diagnostic exit states |
| Timing and latency | Reasoning and communication add latency as the world changes. | Hierarchical rates, asynchronous execution, latency-aware planning, safe interruption |
| Reset and repeatability | Physical resets are costly, imperfect, and sometimes impossible. | Auto-reset, reset verification, counterbalancing, simulation and digital twins |
| Safety and permissions | Actions can injure people, damage hardware, or create irreversible states. | Permission boundaries, runtime shields, human escalation, rollback-aware planning |
| Memory and context | Raw multimodal history quickly exceeds context and obscures causal evidence. | Event abstraction, trace indexing, multimodal episodic/semantic memory |
| Regression-safe learning | Policy and skill updates can regress established behaviors. | Held-out regression suites, versioned skills, gated promotion, reproducible artifacts |
| Embodiment variation | Tools and policies expose different kinematics, sensors, timing, and failure modes. | Semantic capability descriptions, adapters, cross-embodiment skill transfer |
| Evaluation | Final success alone hides retries, unsafe actions, resets, human labor, and resource use. | Process metrics, perturbation suites, audit trails, real-world distributed evaluation |
| Fleet orchestration | More robots and agents add contention, communication cost, and inconsistent state. | Resource-aware scheduling, shared evidence, branch comparison, fault tolerance |
| Foundation-model limits | Model scale leaves grounding, control, and verification as separate system requirements. | Joint model–harness scaling studies and failure-aware system design |

## Related Repositories and Resources

- **Awesome World Models**: "Awesome World Models". [![Code](https://img.shields.io/badge/Code-GitHub-green)](https://github.com/knightnemo/Awesome-World-Models)
- **Awesome Robotics Foundation Models**: "Awesome Robotics Foundation Models". [![Code](https://img.shields.io/badge/Code-GitHub-green)](https://github.com/robotics-survey/Awesome-Robotics-Foundation-Models)
- **Awesome LLM Robotics**: "Awesome LLM Robotics". [![Code](https://img.shields.io/badge/Code-GitHub-green)](https://github.com/GT-RIPL/Awesome-LLM-Robotics)
- **Embodied AI Paper List**: "Embodied AI Paper List". [![Code](https://img.shields.io/badge/Code-GitHub-green)](https://github.com/HCPLab-SYSU/Embodied_AI_Paper_List)
- **NVIDIA GEAR**: "Generalist Embodied Agent Research". [![Website](https://img.shields.io/badge/Website-Link-blue)](https://research.nvidia.com/labs/gear/)

## Contributing

Contributions are welcome. Please read [CONTRIBUTING.md](CONTRIBUTING.md) before opening a pull request. A good addition verifies the official title and links, checks aliases and duplicates, chooses one primary section, and preserves chronological order.

## Acknowledgements

This project takes presentation inspiration from [Awesome World Models](https://github.com/knightnemo/Awesome-World-Models) and builds on the open work of the robotics, embodied AI, machine learning, computer vision, language, agents, and systems communities.

This project was developed with extensive use of GPT-5.6 Sol Ultra and Codex for literature discovery, verification, organization, and editing.

If this list helps your research, consider starring the eventual public repository and contributing missing or corrected work.
