<div align="center">

# Awesome SO-ARM

[![Awesome](https://awesome.re/badge.svg)](https://github.com/sindresorhus/awesome)
[![License: CC0](https://img.shields.io/badge/License-CC0_1.0-blue.svg)](LICENSE)

**A curated list of software, hardware, simulators, policies, and practice guides for the SO-ARM family (SO-ARM100 / 101 / 102) — the open-source arm of the LeRobot ecosystem.**

English · [简体中文](README_zh-CN.md)

</div>

---

The SO-ARM design by [TheRobotStudio](https://github.com/TheRobotStudio/SO-ARM100) has become the de-facto open hardware platform for imitation-learning research: low-cost bus servos, 3D-printable structure, first-class support in [LeRobot](https://github.com/huggingface/lerobot), and a rapidly growing variant ecosystem. This list tracks what exists, what works, and what to watch out for.

Contributions welcome — see [CONTRIBUTING.md](CONTRIBUTING.md). Star counts are snapshots (not live).

## Official & Core

- [TheRobotStudio/SO-ARM100](https://github.com/TheRobotStudio/SO-ARM100) — the original open arm: BOM, 3D files, assembly guides. Everything else descends from here.
- [huggingface/lerobot](https://github.com/huggingface/lerobot) — reference framework: calibrate / teleoperate / record / train toolchain with SO-ARM as a first-class citizen.
- [roboninecom/SO-ARM-102](https://github.com/roboninecom/SO-ARM-102) — next-gen kit: 5-DOF + gripper, PET-CF frame, parallel gripper.

## Hardware & Upgrades

- [roboninecom/SO-ARM100-101-Parallel-Gripper](https://github.com/roboninecom/SO-ARM100-101-Parallel-Gripper) — 3D-printed parallel gripper for STS3215-class servos; a step change in grasp capability over the stock single-servo finger.
- [brukg/SO-100-arm](https://github.com/brukg/SO-100-arm) — v1.3 C++ firmware line.
- Servo batch notes: compatible clones (e.g. HX-series) speak the Feetech protocol but may ship at non-default baudrates — scan before you assume 115200.

## Simulation & ROS

- [ros-physical-ai/ros2_so_arm](https://github.com/ros-physical-ai/ros2_so_arm) — ROS 2 description + drivers + MoveIt config for SO-ARM100/101.
- [MuammerBay/isaac_so_arm101](https://github.com/MuammerBay/isaac_so_arm101) — Isaac Lab RL tasks and tutorials for SO-ARM (URDF → OpenUSD pipeline).
- [mujocolab/mjlab](https://github.com/mujocolab/mjlab) — Isaac Lab API on MuJoCo Warp; increasingly the default free/GPU-accelerated choice for arm+locomotion RL (no NVIDIA stack lock-in).

## Policies, Training & Data

- [lerobot/smolvla_base](https://huggingface.co/lerobot/smolvla_base) — 450M VLA pretrained incl. SO-100 data; benchmark-finetuned siblings (`smolvla_libero`, `_metaworld`, `_robotwin`) on the same org.
- [aalmuzairee/squint](https://github.com/aalmuzairee/squint) — visual SAC with sim-to-real on a real SO-101: reach/lift/place/stack solved in minutes of training.
- [MuammerBay/SO-ARM101_MoveIt_IsaacSim](https://github.com/MuammerBay/SO-ARM101_MoveIt_IsaacSim) — earlier MoveIt integration (superseded by the Isaac Lab repo above).
- Datasets: search `so100`/`so101` on the `lerobot` org for community teleop datasets usable for pretraining.

## Agents & Harnesses (emerging)

The VLM-agent / harness niche for SO-ARM is still sparse — most robot-use agent work targets other platforms. Related efforts:

- [jixinyan/Embodied-DeepSeek-Harness](https://github.com/jixinyan/Embodied-DeepSeek-Harness) — composable agent teams with pluggable robot interfaces (TypeScript, plugin architecture worth studying).
- If you are building an LLM/VLM harness that drives an SO-ARM, please open a PR.

## Practice Guides (community)

- [SO-ARM101: from unboxing to first dataset on a WSL2 laptop](https://github.com/vicfei/robot-learning-journey/blob/main/docs/05-so101-real-robot-first-data.md) — no-sudo WSL2, USB-serial via TCP bridge, Feetech-SDK patching, calibration, scripted-expert data collection, MJPEG camera streaming; includes a full troubleshooting log (raw-bytes-first rule, COM handle hygiene, incremental saves).
- [Robot Use Agent roadmap for SO-ARM](https://github.com/vicfei/robot-learning-journey/blob/main/docs/06-robot-use-agent-roadmap.md) — planner/primitives/executor/verifier harness design with code-veto safety layering.
- [Paper vs hardware: papers re-tested on an SO-101](https://shissorobotics.com/papers/) — robot-learning papers re-run on an SO-101 and a Jetson Orin NX, each with the bar written before the run, the verdict (most fail or are not proven), the cost and a folder that reproduces the numbers ([code](https://github.com/ravediamond/paper-vs-hardware)).

## Ecosystem Landscape

- [Robot harness ecosystem snapshot (2026-10)](https://github.com/vicfei/robot-learning-journey/blob/main/docs/references-robot-harness-landscape.md) — five-repo survey situating SO-ARM agent tooling in the broader harness wave.
- [Locomotion & world-model snapshot (2026-10)](https://github.com/vicfei/robot-learning-journey/blob/main/docs/references-locomotion-worldmodel-2026-10.md) — microduck stack + SuperMimic; the low-compute training routes relevant to arm RL too.

## License

[CC0-1.0](LICENSE)
