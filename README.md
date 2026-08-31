<div align="center">

# Awesome Action-Conditioned World Models

<p>
  <a href="https://awesome.re"><img src="https://awesome.re/badge.svg" alt="Awesome"></a>
  <a href="https://github.com/HaobroLi/Awesome-ACWM/stargazers"><img src="https://img.shields.io/github/stars/HaobroLi/Awesome-ACWM?style=flat-square" alt="GitHub stars"></a>
  <a href="https://github.com/HaobroLi/Awesome-ACWM/issues"><img src="https://img.shields.io/github/issues/HaobroLi/Awesome-ACWM?style=flat-square" alt="GitHub issues"></a>
  <a href="https://github.com/HaobroLi/Awesome-ACWM/commits/main"><img src="https://img.shields.io/github/last-commit/HaobroLi/Awesome-ACWM?style=flat-square" alt="Last commit"></a>
</p>

<p><strong>Action-conditioned video generation, game worlds, embodied simulation, and latent imagination.</strong></p>

<p>
  A curated, community-driven reading list of visual world models that respond to actions,<br>
  roll out controllable futures, and support planning, policy learning, and evaluation.
</p>
<p>
  <a href="#contents">Explore the list</a> ·
  <a href="https://github.com/HaobroLi/Awesome-ACWM/issues">Report an issue</a>
</p>

</div>

---

## About this list

This repository tracks **action-conditioned visual world models (ACWMs)** across three connected use cases:

<table>
  <tr>
    <td width="33%" align="center"><strong>🎮 Game World Models</strong><br>Controllable game-like environments and long-horizon interactive rollouts.</td>
    <td width="33%" align="center"><strong>🤖 Embodied Simulation</strong><br>World models for robot policy planning, imitation, reinforcement learning, and evaluation.</td>
    <td width="33%" align="center"><strong>🧠 Latent Control</strong><br>Pixel, token, feature, and latent dynamics used for visual control.</td>
  </tr>
</table>

The list includes models that generate future pixels/video as well as models that roll the world forward in a learned visual latent space. Last metadata check: **2026-08-14**.

## Contents

- [About this list](#about-this-list)
- [Scope](#scope)
- [Tag legend](#tag-legend)
- [Surveys and perspectives](#surveys-and-perspectives)
- [Game world models](#game-world-models)
- [Embodied simulation](#embodied-simulation)
- [Latent visual world models and control](#latent-visual-world-models-and-control)
- [Benchmarks](#benchmarks)
- [Datasets](#datasets)
- [Related lists](#related-lists)

## Scope

We use **action-conditioned world model (ACWM)** for a model that learns controlled visual dynamics:

<p align="center">
  <strong>future visual states · rewards · termination</strong><br>
  <code>= f(observation history, actions, context)</code>
</p>

Here, future states may be pixels, video tokens, object/3D states, or learned visual features; actions may be observed controls or learned latent actions; and context may include language, goals, scene information, or embodiment details.

Included work should satisfy these criteria:

1. Visual observations are modeled in pixel space, a renderable 3D/4D representation, discrete visual tokens, or a learned visual latent space.
2. Actions or controls affect the transition model. Keyboard/mouse inputs, robot commands, trajectories, action chunks, camera controls, and learned latent actions all qualify.
3. The learned transition is used for interactive rollout, simulation, planning, policy learning, evaluation, or control.

The sections are navigation aids rather than mutually exclusive theoretical categories. In particular, embodied papers are kept in one flat list and may carry several use tags.

## Tag legend

### Representation

- `Video` — future RGB/RGB-D or multi-view observations.
- `Token` — discrete visual tokens or autoregressive observation tokens.
- `Latent` — recurrent or transformer latent states learned from visual observations.
- `Feature` — dynamics in a pretrained visual feature space.
- `3D/4D` — occupancy, point, Gaussian, flow, or other renderable spatial states.
- `Unified` — visual dynamics and action generation/decoding learned in one jointly trained model.

### Downstream use

- `Game` — game-playing or game-like interactive environments.
- `Interactive` — controllable, multi-step visual rollouts.
- `Eval` — policy evaluation, ranking, verification, or failure detection.
- `IL` — imitation learning, behavior cloning, DAgger, or demonstration replay.
- `RL` — reinforcement learning or reinforcement fine-tuning inside the model.
- `Plan` — MPC, tree search, visual foresight, or goal-conditioned planning.
- `Policy` — joint world/action learning or direct policy improvement.
- `Data` — synthetic trajectories, observations, or demonstrations.

## Surveys and perspectives

- “From World Models to World Action Models: A Concise Tutorial for Robotics,” **`arXiv 2026.07`**. [[Paper](https://arxiv.org/abs/2607.00836)]
- “Towards Interactive Video World Modeling: Frontiers, Challenges, Benchmarks, and Future Trends,” **`arXiv 2026.06`**. [[Paper](https://arxiv.org/abs/2606.01164)]
- “World Model for Robot Learning: A Comprehensive Survey,” **`arXiv 2026.05`**. [[Paper](https://arxiv.org/abs/2605.00080)] [[Project](https://ntumars.github.io/wm-robot-survey/)] [[List](https://github.com/NTUMARS/Awesome-World-Model-for-Robotics-Policy)]
- “Video Generation Models as World Models: Efficient Paradigms, Architectures and Algorithms,” **`arXiv 2026.03`**. [[Paper](https://arxiv.org/abs/2603.28489)]
- “A Survey: Learning Embodied Intelligence from Physical Simulators and World Models,” **`arXiv 2025.07`**. [[Paper](https://arxiv.org/abs/2507.00917)] [[List](https://github.com/NJU3DV-LoongGroup/Embodied-World-Models-Survey)]

## Game World Models

**🎮 Game-like interactive environments.** The learned model itself is a controllable game or game-like visual environment. Entries use the same table format as the embodied section and are ordered by first public release, newest first.

| Date | Work | Rep. | Uses | Links |
| --- | --- | --- | --- | --- |
| 2026.07 | **ABot-World-0** — Infinite Interactive World Rollout on a Single Desktop GPU | `Video` | `Game` `Interactive` | [Paper](https://arxiv.org/abs/2607.19191) |
| 2026.07 | **AlayaWorld** — Interactive Long-Horizon World Modeling | `Video` | `Game` `Interactive` | [Paper](https://arxiv.org/abs/2607.18367) |
| 2026.07 | **LingBot-World 2.0 (Infinity)** — Infinite Worlds with Versatile Interactions | `Video` | `Game` `Interactive` | [Paper](https://arxiv.org/abs/2607.07534) · [Project](https://technology.robbyant.com/lingbot-world-v2) · [Code](https://github.com/Robbyant/lingbot-world-v2) |
| 2026.06 | **ActWorld** — From Explorable to Interactive World Model via Action-Aware Memory | `Video` | `Game` `Interactive` | [Paper](https://arxiv.org/abs/2606.17730) |
| 2026.06 | **DreamX-World 1.0** — A General-Purpose Interactive World Model | `Video` | `Game` `Interactive` | [Paper](https://arxiv.org/abs/2606.16993) |
| 2026.05 | **minWM** — A Full-Stack Open-Source Framework for Real-Time Interactive Video World Models | `Video` | `Game` `Interactive` | [Paper](https://arxiv.org/abs/2605.30263) · [Code](https://github.com/shengshu-ai/minWM) |
| 2026.05 | **WorldCraft** — From Camera Navigation to Object Manipulation in Interactive Video World Models | `Video` | `Game` `Interactive` | [Paper](https://arxiv.org/abs/2605.25077) · [Project](https://nevsdev.github.io/WorldCraft/) |
| 2026.04 | **Matrix-Game 3.0** — Real-Time and Streaming Interactive World Model with Long-Horizon Memory | `Video` | `Game` `Interactive` | [Paper](https://arxiv.org/abs/2604.08995) · [Project](https://matrix-game-v3.github.io/) |
| 2026.02 | **LIVE** — Long-horizon Interactive Video World Modeling | `Video` | `Game` `Interactive` | [Paper](https://arxiv.org/abs/2602.03747) · [Project](https://junchao-cs.github.io/LIVE-demo/) |
| 2026.01 | **LingBot-World** — Advancing Open-source World Models | `Video` | `Game` `Interactive` | [Paper](https://arxiv.org/abs/2601.20540) · [Project](https://technology.robbyant.com/lingbot-world) · [Code](https://github.com/Robbyant/lingbot-world) |
| 2025.12 | **Yume-1.5** — A Text-Controlled Interactive World Generation Model | `Video` | `Game` `Interactive` | [Paper](https://arxiv.org/abs/2512.22096) · [Project](https://stdstu12.github.io/YUME-Project/) · [Code](https://github.com/stdstu12/YUME) |
| 2025.12 | **WorldPlay** — Towards Long-Term Geometric Consistency for Real-Time Interactive World Modeling | `Video` | `Game` `Interactive` | [Paper](https://arxiv.org/abs/2512.14614) |
| 2025.12 | **Astra** — General Interactive World Model with Autoregressive Denoising | `Video` | `Game` `Interactive` | [Paper](https://arxiv.org/abs/2512.08931) · [Project](https://eternalevan.github.io/Astra-project/) · [Code](https://github.com/EternalEvan/Astra) |
| 2025.12 | **RELIC** — Interactive Video World Model with Long-Horizon Memory | `Video` | `Game` `Interactive` | [Paper](https://arxiv.org/abs/2512.04040) · [Project](https://relic-worldmodel.github.io/) |
| 2025.11 | **Hunyuan-GameCraft-2** — Instruction-following Interactive Game World Model | `Video` | `Game` `Interactive` | [Paper](https://arxiv.org/abs/2511.23429) · [Project](https://hunyuan-gamecraft-2.github.io/) |
| 2025.08 | **Matrix-Game 2.0** — An Open-Source Real-Time and Streaming Interactive World Model | `Video` | `Game` `Interactive` | [Paper](https://arxiv.org/abs/2508.13009) · [Project](https://matrix-game-v2.github.io/) |
| 2025.08 | **Genie 3** — A New Frontier for World Models | `Video` | `Game` `Interactive` | [Blog](https://deepmind.google/discover/blog/genie-3-a-new-frontier-for-world-models/) |
| 2025.07 | **Yume** — An Interactive World Generation Model | `Video` | `Game` `Interactive` | [Paper](https://arxiv.org/abs/2507.17744) · [Project](https://stdstu12.github.io/YUME-Project/) · [Code](https://github.com/stdstu12/YUME) |
| 2025.06 | **Matrix-Game** — Interactive World Foundation Model | `Video` | `Game` `Interactive` | [Paper](https://arxiv.org/abs/2506.18701) · [Code](https://github.com/SkyworkAI/Matrix-Game) |
| 2025.06 | **Hunyuan-GameCraft** — High-dynamic Interactive Game Video Generation with Hybrid History Condition | `Video` | `Game` `Interactive` | [Paper](https://arxiv.org/abs/2506.17201) · [Project](https://hunyuan-gamecraft.github.io/) |
| 2025.05 | **VRAG** — Learning World Models for Interactive Video Generation | `Video` | `Game` `Interactive` | [Paper](https://arxiv.org/abs/2505.21996) |
| 2025.05 | **Vid2World** — Crafting Video Diffusion Models to Interactive World Models | `Video` | `Game` `Interactive` | [Paper](https://arxiv.org/abs/2505.14357) · [Project](https://knightnemo.github.io/vid2world/) |
| 2025.04 | **MineWorld** — A Real-Time and Open-Source Interactive World Model on Minecraft | `Token` | `Game` `Interactive` | [Paper](https://arxiv.org/abs/2504.08388) · [Project](https://aka.ms/mineworld) · [Code](https://github.com/microsoft/mineworld) |
| 2024.12 | **Genie 2** — A Large-Scale Foundation World Model | `Video` | `Game` `Interactive` | [Blog](https://deepmind.google/discover/blog/genie-2-a-large-scale-foundation-world-model/) |
| 2024.10 | **OASIS** — A Universe in a Transformer | `Video` | `Game` `Interactive` | [Project](https://oasis-model.github.io/) |
| 2024.08 | **GameNGen** — Diffusion Models Are Real-Time Game Engines | `Video` | `Game` `Interactive` | [Paper](https://arxiv.org/abs/2408.14837) · [Project](https://gamengen.github.io/) |
| 2024.06 | **Pandora** — Towards General World Model with Natural Language Actions and Video States | `Video` | `Game` `Interactive` | [Paper](https://arxiv.org/abs/2406.09455) · [Code](https://github.com/maitrix-org/Pandora) |
| 2024.05 | **iVideoGPT** — Interactive VideoGPTs are Scalable World Models | `Token` | `Game` `Interactive` | [Paper](https://arxiv.org/abs/2405.15223) · [Code](https://github.com/thuml/iVideoGPT) |
| 2024.05 | **DIAMOND** — Diffusion for World Modeling: Visual Details Matter in Atari | `Video` | `Game` `Interactive` | [Paper](https://arxiv.org/abs/2405.12399) · [Code](https://github.com/eloialonso/diamond) |
| 2024.02 | **Genie** — Generative Interactive Environments | `Token` | `Game` `Interactive` | [Paper](https://arxiv.org/abs/2402.15391) · [Project](https://sites.google.com/view/genie-2024/) |

## Embodied Simulation

**🤖 Robot-facing world models.** This is deliberately one flat list spanning video, latent, 3D/4D, and unified world models. The `Uses` column allows a paper to be simultaneously classified as evaluation, imitation learning, RL, planning, policy learning, and/or data generation.

| Date | Work | Rep. | Uses | Links |
| --- | --- | --- | --- | --- |
| 2026.08 | **WALL-SS** — Action-conditioned world model for embodied simulation | `Video` | `Eval` `IL` `RL` `Plan` `Policy` | [Project](https://github.com/X-Square-Robot/wall-ss) |
| 2026.07 | **CheckVLA** — Execution-Time Verification with Action-Conditioned World Model for Long-Horizon Mobile Manipulation | `Latent` | `Eval` `Plan` | [Paper](https://arxiv.org/abs/2607.26789) |
| 2026.06 | **Recurrent Generative Replay** — World Action Models Enable Continual Imitation Learning with Recurrent Generative Replays | `Video` | `IL` `Data` | [Paper](https://arxiv.org/abs/2606.27374) |
| 2026.06 | **WAM-RL** — World-Action Model Reinforcement Learning with Reconstruction Rewards and Online Video SFT | `Video` | `RL` `Policy` | [Paper](https://arxiv.org/abs/2606.17906) |
| 2026.06 | **PiL-World** — A Chunk-Wise World Model for VLA Policy-in-the-Loop Evaluation | `Video` | `Eval` | [Paper](https://arxiv.org/abs/2606.05773) |
| 2026.05 | **GE-Sim 2.0** — A Roadmap Towards Comprehensive Closed-loop Video World Simulators for Robotic Manipulation | `Video` | `Eval` `IL` `RL` `Data` | [Paper](https://arxiv.org/abs/2605.27491) · [Project](https://ge-sim-v2.github.io/) |
| 2026.05 | **Sword** — Style-Robust World Models as Simulators via Dynamic Latent Bootstrapping for VLA Policy Post-Training | `Video` | `RL` | [Paper](https://arxiv.org/abs/2605.07288) |
| 2026.04 | **X-WAM** — Unified 4D World Action Modeling from Video Priors with Asynchronous Denoising | `3D/4D` `Unified` | `IL` `Plan` `Policy` | [Paper](https://arxiv.org/abs/2604.26694) · [Project](https://sharinka0715.github.io/X-WAM/) |
| 2026.04 | **dWorldEval** — Scalable Robotic Policy Evaluation via Discrete Diffusion World Model | `Token` | `Eval` | [Paper](https://arxiv.org/abs/2604.22152) |
| 2026.04 | **Hi-WM** — Human-in-the-World-Model for Scalable Robot Post-Training | `Video` | `IL` `RL` `Policy` | [Paper](https://arxiv.org/abs/2604.21741) · [Project](https://hi-wm.github.io/) |
| 2026.04 | **WM-DAgger** — Enabling Efficient Data Aggregation for Imitation Learning with World Models | `Video` | `IL` `Data` | [Paper](https://arxiv.org/abs/2604.11351) · [Code](https://github.com/czs12354-xxdbd/WM-Dagger) |
| 2026.03 | **DreamPlan** — Efficient Reinforcement Fine-Tuning of Vision-Language Planners via Video World Models | `Video` | `RL` `Plan` | [Paper](https://arxiv.org/abs/2603.16860) · [Project](https://psi-lab.ai/DreamPlan/) |
| 2026.03 | **Kinema4D** — Kinematic 4D World Modeling for Spatiotemporal Embodied Simulation | `3D/4D` | `Eval` `Data` | [Paper](https://arxiv.org/abs/2603.16669) · [Project](https://mutianxu.github.io/Kinema4D-project-page/) · [Code](https://github.com/mutianxu/Kinema4D) |
| 2026.03 | **Interactive World Simulator** — Interactive World Simulator for Robot Policy Training and Evaluation | `Video` | `Eval` `IL` `RL` | [Paper](https://arxiv.org/abs/2603.08546) · [Project](https://yixuanwang.me/interactive_world_sim) |
| 2026.02 | **GigaBrain-0.5M\*** — A VLA That Learns From World Model-Based Reinforcement Learning | `Video` | `RL` `Policy` | [Paper](https://arxiv.org/abs/2602.12099) · [Project](https://gigabrain05m.github.io/) |
| 2026.02 | **VLAW** — Iterative Co-Improvement of Vision-Language-Action Policy and World Model | `Video` | `IL` `Policy` `Data` | [Paper](https://arxiv.org/abs/2602.12063) · [Project](https://sites.google.com/view/vla-w) |
| 2026.02 | **RISE** — Self-Improving Robot Policy with Compositional World Model | `Video` | `IL` `RL` `Policy` | [Paper](https://arxiv.org/abs/2602.11075) · [Project](https://opendrivelab.com/kai0-rl/) |
| 2026.02 | **Say, Dream, and Act** — Learning Video World Models for Instruction-Driven Robot Manipulation | `Video` | `Plan` `Policy` | [Paper](https://arxiv.org/abs/2602.10717) |
| 2026.02 | **DreamDojo** — A Generalist Robot World Model from Large-Scale Human Videos | `Video` | `IL` `Policy` `Data` | [Paper](https://arxiv.org/abs/2602.06949) · [Project](https://dreamdojo-world.github.io/) |
| 2026.02 | **World-VLA-Loop** — Closed-Loop Learning of Video World Model and VLA Policy | `Video` | `IL` `Policy` `Data` | [Paper](https://arxiv.org/abs/2602.06508) · [Project](https://showlab.github.io/World-VLA-Loop/) |
| 2026.02 | **WoVR** — World Models as Reliable Simulators for Post-Training VLA Policies with RL | `Video` | `RL` | [Paper](https://arxiv.org/abs/2602.13977) · [Project](https://wovr-corl.github.io/) |
| 2026.02 | **World-Gymnast** — Training Robots with Reinforcement Learning in a World Model | `Video` | `RL` | [Paper](https://arxiv.org/abs/2602.02454) · [Project](https://world-gymnast.github.io/) |
| 2026.01 | **lingbot-va** — Causal World Modeling for Robot Control | `Video` | `Plan` `Policy` | [Paper](https://arxiv.org/abs/2601.21998) · [Project](https://technology.robbyant.com/lingbot-va) · [Code](https://github.com/robbyant/lingbot-va) |
| 2026.01 | **PointWorld** — Scaling 3D World Models for In-The-Wild Robotic Manipulation | `3D/4D` | `Plan` `Policy` | [Paper](https://arxiv.org/abs/2601.03782) · [Project](https://point-world.github.io/) · [Code](https://github.com/NVlabs/PointWorld) · [Model](https://huggingface.co/nvidia/PointWorld_models) |
| 2025.12 | **Veo World Simulator** — Evaluating Gemini Robotics Policies in a Veo World Simulator | `Video` | `Eval` | [Paper](https://arxiv.org/abs/2512.10675) |
| 2025.11 | **Scalable Policy Evaluation** — Scalable Policy Evaluation with Video World Models | `Video` | `Eval` | [Paper](https://arxiv.org/abs/2511.11520) |
| 2025.10 | **Ctrl-World** — A Controllable Generative World Model for Robot Manipulation | `Video` | `Plan` `Policy` | [Paper](https://arxiv.org/abs/2510.10125) · [Project](https://ctrl-world.github.io/) · [Code](https://github.com/Robert-gyj/Ctrl-World) |
| 2025.10 | **VLA-RFT** — Vision-Language-Action Reinforcement Fine-tuning with Verified Rewards in World Simulators | `Video` | `RL` | [Paper](https://arxiv.org/abs/2510.00406) · [Project](https://vla-rft.github.io/) |
| 2025.09 | **World-Env** — Leveraging World Model as a Virtual Environment for VLA Post-Training | `Video` | `RL` | [Paper](https://arxiv.org/abs/2509.24948) · [Code](https://github.com/amap-cvlab/world-env) |
| 2025.09 | **World4RL** — Diffusion World Models for Policy Refinement with Reinforcement Learning for Robotic Manipulation | `Video` | `RL` | [Paper](https://arxiv.org/abs/2509.19080) |
| 2025.08 | **Genie Envisioner** — A Unified World Foundation Platform for Robotic Manipulation | `Video` | `Eval` `IL` `Plan` `Policy` | [Paper](https://arxiv.org/abs/2508.05635) · [Project](https://genie-envisioner.github.io/) |
| 2025.06 | **ParticleFormer** — A 3D Point Cloud World Model for Multi-Object, Multi-Material Robotic Manipulation | `3D/4D` | `Plan` | [Paper](https://arxiv.org/abs/2506.23126) · [Project](https://particleformer.github.io/) |
| 2025.06 | **WorldVLA** — Towards Autoregressive Action World Model | `Video` | `Policy` `Plan` | [Paper](https://arxiv.org/abs/2506.21539) · [Code](https://github.com/alibaba-damo-academy/WorldVLA) |
| 2025.05 | **LaDi-WM** — A Latent Diffusion-based World Model for Predictive Manipulation | `Latent` | `Plan` `Policy` | [Paper](https://arxiv.org/abs/2505.11528) |
| 2025.05 | **FLARE** — Robot Learning with Implicit World Modeling | `Latent` | `Policy` `Data` | [Paper](https://arxiv.org/abs/2505.15659) · [Project](https://research.nvidia.com/labs/gear/flare) · [Code](https://github.com/NVIDIA/Isaac-GR00T) |
| 2025.05 | **WorldEval** — World Model as Real-World Robot Policies Evaluator | `Video` | `Eval` | [Paper](https://arxiv.org/abs/2505.19017) · [Project](https://worldeval.github.io/) |
| 2025.05 | **DreamGen** — Unlocking Generalization in Robot Learning through Video World Models | `Video` | `IL` `Data` | [Paper](https://arxiv.org/abs/2505.12705) · [Code](https://github.com/NVIDIA/GR00T-Dreams) |
| 2025.04 | **TesserAct** — Learning 4D Embodied World Models | `3D/4D` | `Plan` `Policy` | [Paper](https://arxiv.org/abs/2504.20995) · [Project](https://tesseractworld.github.io/) |
| 2025.04 | **PIN-WM** — Learning Physics-INformed World Models for Non-Prehensile Manipulation | `3D/4D` | `Plan` | [Paper](https://arxiv.org/abs/2504.16693) |
| 2025.04 | **UWM** — Unified World Models: Coupling Video and Action Diffusion for Pretraining on Large Robotic Datasets | `Video` `Unified` | `IL` `Policy` `Data` | [Paper](https://arxiv.org/abs/2504.02792) · [Project](https://weirdlabuw.github.io/uwm/) |
| 2024.12 | **Dream to Manipulate** — Compositional World Models Empowering Robot Imitation Learning with Imagination | `Video` | `IL` `Plan` `Data` | [Paper](https://arxiv.org/abs/2412.14957) · [Project](https://leobarcellona.github.io/DreamToManipulate/) |
| 2024.10 | **EVA** — An Embodied World Model for Future Video Anticipation | `Video` | `Plan` `Policy` | [Paper](https://arxiv.org/abs/2410.15461) · [Project](https://sites.google.com/view/eva-publi) |
| 2024.06 | **IRASim** — A Fine-Grained World Model for Robot Manipulation | `Video` | `Eval` `Plan` | [Paper](https://arxiv.org/abs/2406.14540) · [Project](https://gen-irasim.github.io) · [Code](https://github.com/bytedance/IRASim) |
| 2024.04 | **RoboDreamer** — Learning Compositional World Models for Robot Imagination | `Video` | `Plan` `Policy` | [Paper](https://arxiv.org/abs/2404.12377) · [Project](https://robovideo.github.io/) |
| 2024.03 | **3D-VLA** — A 3D Vision-Language-Action Generative World Model | `3D/4D` | `Plan` `Policy` | [Paper](https://arxiv.org/abs/2403.09631) |
| 2024.03 | **ManiGaussian** — Dynamic Gaussian Splatting for Multi-task Robotic Manipulation | `3D/4D` | `Plan` `Policy` | [Paper](https://arxiv.org/abs/2403.08321) · [Project](https://guanxinglu.github.io/ManiGaussian/) |
| 2023.10 | **UniSim** — Learning Interactive Real-World Simulators | `Video` | `IL` `RL` `Plan` `Policy` `Data` | [Paper](https://arxiv.org/abs/2310.06114) · [Project](https://universal-simulator.github.io/) |

## Latent Visual World Models and Control

**🧠 Latent imagination and visual control.** This section covers general visual control and model-based RL work whose action-conditioned dynamics live partly or entirely in learned latent space. Pixel-generative methods are included when they are foundational to this line.

| Date | Work | Rep. | Uses | Links |
| --- | --- | --- | --- | --- |
| 2025.06 | **V-JEPA 2 / V-JEPA 2-AC** — Self-Supervised Video Models Enable Understanding, Prediction and Planning | `Feature` | Action-conditioned planning | [Paper](https://arxiv.org/abs/2506.09985) · [Project](https://ai.meta.com/blog/v-jepa-2-world-model-benchmarks/) · [Code](https://github.com/facebookresearch/vjepa2) |
| 2024.11 | **DINO-WM** — World Models on Pre-trained Visual Features enable Zero-shot Planning | `Feature` | Zero-shot planning | [Paper](https://arxiv.org/abs/2411.04983) · [Project](https://dino-wm.github.io/) · [Code](https://github.com/gaoyuezhou/dino_wm) |
| 2024.10 | **AVID** — Adapting Video Diffusion Models to World Models | `Video` | Action-conditioned diffusion | [Paper](https://arxiv.org/abs/2410.12822) · [Code](https://github.com/microsoft/causica/tree/main/research_experiments/avid) |
| 2024.06 | **Delta-IRIS** — Efficient World Models with Context-Aware Tokenization | `Token` | Visual RL | [Paper](https://arxiv.org/abs/2406.19320) · [Code](https://github.com/vmicheli/delta-iris) |
| 2023.10 | **TD-MPC2** — Scalable, Robust World Models for Continuous Control | `Latent` | Continuous control | [Paper](https://arxiv.org/abs/2310.16828) · [Code](https://github.com/nicklashansen/tdmpc2) |
| 2023.01 | **DreamerV3** — Mastering Diverse Domains through World Models | `Latent` | General RL | [Paper](https://arxiv.org/abs/2301.04104) · [Code](https://github.com/danijar/dreamerv3) |
| 2022.09 | **IRIS** — Transformers are Sample-Efficient World Models | `Token` | Atari control | [Paper](https://arxiv.org/abs/2209.00588) · [Code](https://github.com/eloialonso/iris) |
| 2022.06 | **MWM** — Masked World Models for Visual Control | `Latent` | Visual RL | [Paper](https://arxiv.org/abs/2206.14244) · [Code](https://github.com/younggyoseo/MWM) |
| 2022.06 | **DayDreamer** — World Models for Physical Robot Learning | `Latent` | Real-robot RL | [Paper](https://arxiv.org/abs/2206.14176) · [Code](https://github.com/danijar/daydreamer) |
| 2022.03 | **TD-MPC** — Temporal Difference Learning for Model Predictive Control | `Latent` | MPC and control | [Paper](https://arxiv.org/abs/2203.04955) · [Code](https://github.com/nicklashansen/tdmpc) |
| 2020.10 | **DreamerV2** — Mastering Atari with Discrete World Models | `Latent` | Atari control | [Paper](https://arxiv.org/abs/2010.02193) · [Code](https://github.com/danijar/dreamerv2) |
| 2019.12 | **Dreamer** — Dream to Control: Learning Behaviors by Latent Imagination | `Latent` | Continuous control | [Paper](https://arxiv.org/abs/1912.01603) · [Code](https://github.com/danijar/dreamer) |
| 2019.11 | **MuZero** — Mastering Atari, Go, Chess and Shogi by Planning with a Learned Model | `Latent` | Tree-search planning | [Paper](https://arxiv.org/abs/1911.08265) |
| 2019.03 | **SimPLe** — Model-Based Reinforcement Learning for Atari | `Video` | Atari control | [Paper](https://arxiv.org/abs/1903.00374) |
| 2018.11 | **PlaNet** — Learning Latent Dynamics for Planning from Pixels | `Latent` | MPC and control | [Paper](https://arxiv.org/abs/1811.04551) · [Code](https://github.com/google-research/planet) |
| 2018.03 | **World Models** — World Models | `Latent` | Control by imagination | [Paper](https://arxiv.org/abs/1803.10122) · [Project](https://worldmodels.github.io/) |
| 2016.10 | **Deep Visual Foresight** — Deep Visual Foresight for Planning Robot Motion | `Video` | Visual MPC | [Paper](https://arxiv.org/abs/1610.00696) |
| 2016.05 | **Unsupervised Physical Interaction** — Unsupervised Learning for Physical Interaction through Video Prediction | `Video` | Robot control | [Paper](https://arxiv.org/abs/1605.07157) |
| 2015.07 | **Action-Conditional Video Prediction** — Action-Conditional Video Prediction using Deep Networks in Atari Games | `Video` | Atari prediction | [Paper](https://arxiv.org/abs/1507.08750) |

## Benchmarks

| Date | Benchmark | Domain | Links |
| --- | --- | --- | --- |
| 2026.08 | **WorldSimProbe** — Action-following evaluation for action-conditioned world models | Action-conditioned world models | [Project](https://github.com/pxxq25/WorldSimProbe) |
| 2026.06 | **WorldRoamBench** — Long-horizon stability of interactive world models | Interactive | [Paper](https://arxiv.org/abs/2606.31672) |
| 2026.06 | **RoboTrustBench** — Trustworthiness of video world models for robotic manipulation | Embodied | [Paper](https://arxiv.org/abs/2606.01600) · [Project](https://huiqiongli.github.io/RoboTrustBench/) |
| 2026.05 | **MiraBench** — Action-conditioned reliability in robotic world models | Embodied | [Paper](https://arxiv.org/abs/2605.29360) |
| 2026.05 | **WBench** — Multi-turn interactive video world model evaluation | Interactive | [Paper](https://arxiv.org/abs/2605.25874) · [Project](https://meituan-longcat.github.io/WBench/) |
| 2026.05 | **ACWM-Phys** — Generalized physical interaction in action-conditioned video world models | Embodied | [Paper](https://arxiv.org/abs/2605.08567) · [Project](https://xavihart.github.io/ACWM-Phys) · [Code](https://github.com/xavihart/ACWM-Phys-dev) |
| 2026.05 | **iWorld-Bench** — Interactive world models with a unified action generation framework | Interactive | [Paper](https://arxiv.org/abs/2605.03941) |
| 2026.04 | **WorldMark** — Unified benchmark suite for interactive video world models | Interactive | [Paper](https://arxiv.org/abs/2604.21686) |
| 2026.04 | **RoboWM-Bench** — World models in robotic manipulation | Embodied | [Paper](https://arxiv.org/abs/2604.19092) · [Project](https://robowm-bench.github.io/RoboWM-Bench/) |
| 2026.01 | **Wow, wo, val!** — Embodied world model evaluation Turing test | Embodied | [Paper](https://arxiv.org/abs/2601.04137) |

## Datasets

- **DROID**: Large-scale, in-the-wild robot manipulation trajectories. [[Project](https://droid-dataset.github.io/)] [[Code](https://github.com/droid-dataset/droid)]
- **Open X-Embodiment**: Cross-embodiment robot trajectories and RT-X models. [[Project](https://robotics-transformer-x.github.io/)]
- **BridgeData V2**: Broad manipulation data collected across many environments and tasks. [[Project](https://rail-berkeley.github.io/bridgedata/)]
- **RoboNet**: Multi-robot video data for learning visual dynamics. [[Project](https://www.robonet.wiki/)]
- **BAIR Robot Pushing**: Action-conditioned pushing videos used by early visual-foresight work. [[Dataset](http://rail.eecs.berkeley.edu/datasets/bair_robot_pushing_dataset_v0.tar)]

## Related lists

- [Awesome World Models for Robotics](https://github.com/leofan90/awesome-world-models) — structural inspiration and a broader world-model list.
- [Awesome World Models](https://github.com/knightnemo/Awesome-World-Models) — general world-model resources.
- [Awesome World Model for Robotics Policy](https://github.com/NTUMARS/Awesome-World-Model-for-Robotics-Policy) — robot-policy-oriented world models.
- [Embodied World Models Survey](https://github.com/NJU3DV-LoongGroup/Embodied-World-Models-Survey) — physical simulators and world models for embodied intelligence.
- [Awesome Video Diffusion](https://github.com/showlab/Awesome-Video-Diffusion) — broader video-diffusion literature.

## License

This list is released under [CC0 1.0](LICENSE).
