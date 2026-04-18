---
title: "{{title}}"
date: <% tp.date.now("YYYY-MM-DD") %>
tags:
  - 机械臂
  - 具身智能
  - VLA
status: 进行中
---
## 项目背景
<!-- 为什么做这个，解决什么问题 -->
PPO强化学习
Unitree/PPO/Isaac sim/Mujoco
## 成果展示
<!-- 拖入图片或粘贴截图 -->

1500steps
![[RL_Unitree_dog_1500steps.webm]]
 
 49600steps
![[RL_Unitree_dog_49600steps 1.webm]]

Mujoco
![[RL_Unitree_dog_Mujoco.webm]]

## 系统架构
<!-- 在这里插入 Excalidraw 图：点击左侧工具栏的 Excalidraw 图标新建 -->

## 核心实现
<!-- 关键技术点、代码思路 -->



## 我的思考
<!-- 发现、踩坑、反思 -->

## 参考资料
1. https://github.com/unitreerobotics/unitree_rl_lab 
2. https://github.com/mujocolab/mjlab.git
3. https://github.com/unitreerobotics/unitree_rl_mjlab
|维度|unitree_rl_lab|mjlab|unitree_rl_mjlab|
|---|---|---|---|
|**仓库地址**|unitreerobotics/unitree_rl_lab|mujocolab/mjlab|unitreerobotics/unitree_rl_mjlab|
|**维护者**|宇树官方|社区第三方|宇树官方|
|**定位**|宇树机器人训练 + 部署全链路|通用 RL 研究框架|宇树机器人训练 + 部署全链路|
|**Star 数**|803|1.8k|92|
|**提交数**|77 次|867 次|5 次（非常新）|
|**许可证**|Apache-2.0|Apache-2.0|Apache-2.0|
|**— 技术架构 —**||||
|**物理引擎**|IsaacSim PhysX|MuJoCo Warp GPU|MuJoCo Warp GPU|
|**上层框架**|IsaacLab|自研（借鉴 IsaacLab API）|mjlab|
|**RL 算法**|RSL-RL PPO|RSL-RL PPO|RSL-RL PPO|
|**策略格式**|.pt (LibTorch)|.pt (LibTorch)|.onnx (ONNX Runtime)|
|**— 安装与环境 —**||||
|**安装复杂度**|重：Docker + IsaacSim|极轻：uv 单命令|轻：pip / uv|
|**依赖 Omniverse**|是|否|否|
|**Docker 支持**|官方提供 Dockerfile|官方提供 Dockerfile|参考 mjlab Dockerfile|
|**— 机器人与任务 —**||||
|**支持机器人**|Go2 / H1 / G1-29dof|G1 / Go1 / YAM 机械臂|Go2 / A2 / G1 / H1_2 / R1 / H2|
|**支持任务**|速度跟踪（平地 / 崎岖）|速度跟踪 / 动作模仿 / 操作|速度跟踪 / 动作模仿|
|**可视化**|IsaacSim GUI（5070Ti 有渲染 bug）|MuJoCo Viewer / 网页 Viser|MuJoCo Viewer|
|**— 部署链路 —**||||
|**Sim2Sim**|需要，用 unitree_mujoco|无（纯训练框架）|不需要（训练即 MuJoCo）|
|**实机部署**|有，C++ + unitree_sdk2|无|有，C++ + unitree_sdk2|
|**部署流程**|训练 → Sim2Sim → Sim2Real|训练（无部署）|训练 → 直接 Sim2Real|
|**策略导出时机**|play.py 手动导出|play.py 手动导出|训练中自动同步导出|
|**— 适用场景 —**||||
|**最适合**|已有 IsaacLab 环境、需要完整宇树部署链路|研究人员快速原型、非宇树机器人定制任务|想用 MuJoCo 物理精度 + 宇树完整部署链路|
