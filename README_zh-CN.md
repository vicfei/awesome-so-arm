<div align="center">

# Awesome SO-ARM

[![Awesome](https://awesome.re/badge.svg)](https://github.com/sindresorhus/awesome)
[![License: CC0](https://img.shields.io/badge/License-CC0_1.0-blue.svg)](LICENSE)

**SO-ARM 家族（SO-ARM100 / 101 / 102）的软件、硬件、仿真、策略与实践指南清单——LeRobot 生态的开源机械臂。**

[English](README.md) · 简体中文

</div>

---

[TheRobotStudio](https://github.com/TheRobotStudio/SO-ARM100) 的 SO-ARM 设计已成为模仿学习研究的事实标准开源硬件平台：低成本总线舵机、3D 打印结构、[LeRobot](https://github.com/huggingface/lerobot) 一等公民支持，变体生态快速增长。本清单追踪"有什么、好不好使、要避什么坑"。

欢迎投稿，见 [CONTRIBUTING.md](CONTRIBUTING.md)。Star 数为快照值（非实时）。

## 官方与核心

- [TheRobotStudio/SO-ARM100](https://github.com/TheRobotStudio/SO-ARM100) — 原始开源臂：BOM、3D 文件、装配指南，一切生态的源头。
- [huggingface/lerobot](https://github.com/huggingface/lerobot) — 参考框架：标定/遥操作/采集/训练全链工具，SO-ARM 为一等公民。
- [roboninecom/SO-ARM-102](https://github.com/roboninecom/SO-ARM-102) — 下一代套件：5 自由度+夹爪、PET-CF 碳纤框架、平行夹爪。

## 硬件与升级

- [roboninecom/SO-ARM100-101-Parallel-Gripper](https://github.com/roboninecom/SO-ARM100-101-Parallel-Gripper) — 兼容 STS3215 级舵机的 3D 打印平行夹爪，抓取能力较原厂单舵机手指是质变。
- [brukg/SO-100-arm](https://github.com/brukg/SO-100-arm) — v1.3 的 C++ 固件线。
- 舵机批次提示：兼容克隆（如 HX 系列）说 Feetech 协议但出厂波特率可能是非默认值——先扫描再假设 115200。

## 标定与工具

- [fport/so101-calibrator](https://github.com/fport/so101-calibrator) — 终端里的 SO-101 分步标定：检查电机 ID、供电电压、运动范围和关节方向，每次标定都保存为一个版本，并导出 LeRobot 文件。自带模拟机械臂。

## 仿真与 ROS

- [ros-physical-ai/ros2_so_arm](https://github.com/ros-physical-ai/ros2_so_arm) — SO-ARM100/101 的 ROS 2 描述+驱动+MoveIt 配置。
- [MuammerBay/isaac_so_arm101](https://github.com/MuammerBay/isaac_so_arm101) — Isaac Lab 的 RL 任务与教程（URDF→OpenUSD 管线）。
- [mujocolab/mjlab](https://github.com/mujocolab/mjlab) — Isaac Lab API × MuJoCo Warp；日益成为免费 GPU 加速的机械臂+运动 RL 默认选择（不锁 NVIDIA 栈）。

## 策略、训练与数据

- [lerobot/smolvla_base](https://huggingface.co/lerobot/smolvla_base) — 450M VLA（预训练含 SO-100 数据）；同 org 下有各基准微调版（`smolvla_libero` 等）。
- [aalmuzairee/squint](https://github.com/aalmuzairee/squint) — 真机 SO-101 上的视觉 SAC sim-to-real：reach/lift/place/stack 分钟级训练解决。
- 数据集：在 `lerobot` org 搜 `so100`/`so101` 可得社区遥操作数据集（可用于预训练）。

## Agent 与 Harness（新兴）

SO-ARM 的 VLM-agent/harness 生态还很稀疏——多数 robot-use agent 工作针对其他平台。相关努力：

- [jixinyan/Embodied-DeepSeek-Harness](https://github.com/jixinyan/Embodied-DeepSeek-Harness) — 可组合 agent 团队+可插拔机器人接口（TypeScript，插件架构值得借鉴）。
- 如果你在做驱动 SO-ARM 的 LLM/VLM harness，欢迎提 PR 入列。

## 实践指南（社区）

- [SO-ARM101：从开箱到首批数据（WSL2 笔记本）](https://github.com/vicfei/robot-learning-journey/blob/main/docs/05-so101-real-robot-first-data.md) — 无 sudo 的 WSL2、USB 串口走 TCP 桥、Feetech SDK 补丁、校准、程序专家数据采集、MJPEG 相机流；附完整排障记录（先抓原始字节、串口句柄卫生、增量保存）。
- [SO-ARM 的 Robot Use Agent 路线图](https://github.com/vicfei/robot-learning-journey/blob/main/docs/06-robot-use-agent-roadmap.md) — planner/原语/executor/verifier 的 harness 设计，含代码否决安全分层。

## 生态快照

- [Robot harness 生态快照（2026-10）](https://github.com/vicfei/robot-learning-journey/blob/main/docs/references-robot-harness-landscape.md) — 五仓调研，SO-ARM agent 工具在 harness 浪潮中的位置。
- [腿足与世界模型快照（2026-10）](https://github.com/vicfei/robot-learning-journey/blob/main/docs/references-locomotion-worldmodel-2026-10.md) — microduck 技术栈 + SuperMimic；与机械臂 RL 相关的省算力路线。

## 许可

[CC0-1.0](LICENSE)
