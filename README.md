# Climbing_robot

攀爬机器人（GEKKO-1 × RDK）的视觉资料与结构模型仓库。

## 项目简介

机器人通过 C 形夹持机构固定在护栏 / 横杆上，机身携带一台云台相机与一条机械臂，可在栏杆、床架等场景中完成视觉识别与目标抓取（如下图中夹取耳机）。

## 系统架构

整体分三层：**机器人功能模块（产品侧）— RDK 开发板（计算与接口侧）— 执行与驱动层（机电侧）**。

| 层级 | 主要内容 |
|---|---|
| 机器人功能模块 | 语音交互、视觉识别、机械臂抓取、爬行移动、安全与监控 |
| RDK 开发板（以 X5 为例） | 音频采集与输出（I2S / PDM、Codec）、图像采集与处理（MIPI CSI ×2、ISP、BPU 10 TOPS）、计算与通信（CPU 8×A55、LPDDR4、Wi-Fi 6 / BT 5.0）、运动控制接口（UART 40pin、GPIO / PWM、USB 3.0 / 以太网）、电源与驱动（DC 12 V、ADC 采样、eMMC / microSD） |
| 执行与驱动层 | 声学终端（麦克风阵列、3 W 扬声器）、视觉终端（双目相机模组、红外补光）、抓取执行（MCU 实时控制、机械臂 4-DOF）、爬行执行（抱爪舵机 ×4）、供电与保护（3S 锂电 11.1 V、降压与急停） |

> 架构图按通用功能划分，接口数量与引脚定义以所选 RDK 型号为准；图中数值为工程估算，不作为加工依据。

## 图片

| 文件 | 说明 |
|---|---|
| `images/01-system-architecture.jpg` | GEKKO-1 机器人 × RDK 开发板系统架构 |
| `images/02-robot-rail-mount.jpg` | 机器人夹持在护栏上的实拍 |
| `images/03-exploded-view.jpg` | 结构爆炸图（夹持机构、相机模组、控制板、机械臂、抱爪） |
| `images/04-three-views.jpg` | 三视角线稿 |
| `images/05-desk-scene.jpg` | 书桌场景：机械臂抓取耳机 |

## 模型文件

| 文件 | 说明 |
|---|---|
| `model/零件5.SLDPRT` | SolidWorks 零件文件 |

## 软件平台

Ubuntu 22.04 / TROS / ROS 2 中间件，配合 RDK 官方算法包（`hobot_dnn` / `hobot_audio` / `hobot_clip` / `hobot_tts`）。

## 目录结构

```
Climbing_robot/
├── images/          # 架构图、实拍、爆炸图、三视图、场景图
├── model/           # SolidWorks 零件模型
└── README.md
```
