# ⏱️ Embodied Time-Series Sync

[![Python 3.11+](https://img.shields.io/badge/python-3.11+-blue.svg)](https://www.python.org/downloads/)
[![Pandas](https://img.shields.io/badge/pandas-2.0+-150458.svg?logo=pandas)](https://pandas.pydata.org/)
[![Jupyter](https://img.shields.io/badge/Jupyter-Lab-F37626.svg?logo=Jupyter)](https://jupyter.org/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

> 🚀 **一行代码搞定具身智能多频传感器的时间戳对齐 (A lightweight Jupyter Demo for asynchronous sensor alignment)**

---

## 📖 Overview | 简介

在具身智能（Embodied AI）或机器人操作场景中，不同硬件（如 30Hz 视觉相机与 500Hz 底盘 IMU）的传感器采样率往往不一致。

本项目提供了一个极简且开箱即用的 Jupyter Notebook 演示（Demo）。带你彻底告别低效的 `for` 循环，利用 Pandas 强大的时序引擎和 `merge_asof()` 方法，实现工业级、严丝合缝的多模态数据对齐。

---

## ⚙️ Prerequisites | 环境要求

* Python 3.11+
* Pandas & NumPy
* Jupyter Notebook / JupyterLab

---

## 🚀 Quick Start | 快速开始

请在终端中执行以下标准命令，将 Demo 运行在你的本地环境中：

```bash
# 1. 克隆本仓库 (Clone the repository)
git clone https://github.com/knight008848/Time_Series_Demo.git

# 2. 进入项目目录 (Navigate to the directory)
cd notebooks

# 3. 安装核心依赖 (Install dependencies)
pip install pandas numpy jupyterlab

# 4. 启动 Jupyter 并打开 Demo (Launch Jupyter)
jupyter notebook time_series_alignment_demo.ipynb
```

---

## 🧠 Core Concept | 核心原理预览

打开 Notebook 后，你将亲手跑通以下核心数据流：

1.  **时间戳物理化：** 将原始的浮点数电平时间（Float Timestamp）极速转化为带有物理意义的时间差格式（`pd.Timedelta`）。
2.  **异步模糊匹配：** 运用 `pd.merge_asof(direction='backward')`，严格遵循物理因果律，以低频主传感器为基准，向后寻找最近的高频状态。
3.  **死区安全截断：** 利用 `tolerance` 参数设置容忍度阀值。当硬件发生断联超过 50ms 时，自动拦截过期脏数据并填充为 `NaN`，防止梯度爆炸。

---

## 📄 License | 开源协议

本项目基于 [MIT License](LICENSE) 协议开源。欢迎自由 Fork、修改，并无缝集成到你自己的机器人算法管线中！

---

**✎ Maintained by:** knight008848
