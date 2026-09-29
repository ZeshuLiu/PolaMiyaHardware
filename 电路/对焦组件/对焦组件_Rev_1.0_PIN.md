# 对焦组件 Rev 1.0 PIN

## PCB 信息

| 项目 | 内容 |
| --- | --- |
| PCB 名称 | Focus Unit Drive |
| 工程文件 | `对焦组件.kicad_pcb` |
| 版本 | Rev 1.0 |
| MCU | U2 — STM32F030F4Px |
| 数据来源 | PCB 设计文件中的网络与封装焊盘定义 |

## STM32 引脚

下表列出 U2 的全部封装引脚。网络名以 KiCad PCB 文件中的定义为准；后缀数字为 STM32F030F4Px 的封装引脚号。

| U2 焊盘 | STM32 信号 | 网络 | 类型 |
| ---: | --- | --- | --- |
| 1 | BOOT0 | `Net-(U2-BOOT0)` | 输入 |
| 2 | PF0 | `Net-(U2-PF0)` | 双向 |
| 3 | PF1 | `Net-(U2-PF1)` | 双向 |
| 4 | NRST | `Net-(U2-NRST)` | 输入 |
| 5 | VDDA | `Net-(U2-VDDA)` | 电源输入 |
| 6 | PA0 | `/ADC_NTC1` | 双向 |
| 7 | PA1 | `/ADC_3V3` | 双向 |
| 8 | PA2 | `/USART1 _TX` | 双向 |
| 9 | PA3 | `/USART1 _RX` | 双向 |
| 10 | PA4 | `/ADC_NTC2` | 双向 |
| 11 | PA5 | `/ADC_6V` | 双向 |
| 12 | PA6 | `/MOT_ENC_A` | 双向 |
| 13 | PA7 | `/MOT_ENC_B` | 双向 |
| 14 | PB1 | `/ADC_MT` | 双向 |
| 15 | VSS | `GND` | 电源输入 |
| 16 | VDD | `+3V3` | 电源输入 |
| 17 | PA9 | `/MotorPWM_B` | 双向 |
| 18 | PA10 | `/MotorPWM_A` | 双向 |
| 19 | PA13 | `/SWDIO` | 双向 |
| 20 | PA14 | `/SWCLK` | 双向 |

## 外部连接器中与 STM32 网络相连的引脚

### J1 — SWD 调试接口

| J1 引脚 | 网络 | 对应 U2 引脚 | 说明 |
| ---: | --- | ---: | --- |
| 1 | `+3V3` | U2-16 | MCU 供电 |
| 2 | `/SWDIO` | U2-19 / PA13 | SWD 数据 |
| 3 | `/SWCLK` | U2-20 / PA14 | SWD 时钟 |
| 4 | `GND` | U2-15 | 地 |

### CN2 — 对焦组件接口

以下引脚与 U2 使用同一 PCB 网络，属于 MCU 侧直连或电源/地连接。CN2-1、CN2-2 的电机输出经过板上驱动级，不属于 STM32 引脚的直接网络连接。

| CN2 引脚 | 网络 | 对应 U2 引脚 | 说明 |
| ---: | --- | ---: | --- |
| 3 | `/ADC_NTC1` | U2-6 / PA0 | NTC1 模拟采样 |
| 4 | `/ADC_NTC2` | U2-10 / PA4 | NTC2 模拟采样 |
| 5 | `+3V3` | U2-16 | 3.3 V 电源 |
| 6 | `/MOT_ENC_B` | U2-13 / PA7 | 电机编码器 B 相 |
| 7 | `/MOT_ENC_A` | U2-12 / PA6 | 电机编码器 A 相 |
| 8 | `GND` | U2-15 | 地 |

## 备注

- `/MotorPWM_A` 与 `/MotorPWM_B` 分别由 U2-18 / PA10、U2-17 / PA9 输出，并连接到板上电机驱动级。
- `/ADC_3V3`、`/USART1 _TX`、`/USART1 _RX`、`/ADC_6V`、`/ADC_MT` 目前在 PCB 网络中属于 U2 信号，但未在 J1/CN2 上直接引出。
- 连接器编号、网络名和引脚号均按 Rev 1.0 PCB 文件记录；PCB 改版后应同步更新本文档。
