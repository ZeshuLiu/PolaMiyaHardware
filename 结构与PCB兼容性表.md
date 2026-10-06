# 结构与 PCB 兼容性表

更新：2026-10-06。结构与 PCB 分别编号，PCB 版本以设计文件标题栏为准。

| 结构 | PCB | 版本 | 工程 | 备注 |
| --- | --- | --- | --- | --- |
| Rev2N | 主控器 PM_Controller | 1.3 | [历史主控](电路/主控器/主要历史版本/PM_Controller_Rev1.3/) | 已归档，与 DispKey 1.0 配套 |
| Rev2N | 显示按键板 DispKey | 1.0 | [显示按键板](电路/主控器/主要历史版本/PM_Controller_Rev1.3/DispKey/) | 与主控器 1.3 一并归档 |
| Rev2N | 吐片电机驱动 MotroDrive | 1.2 | [电机驱动](电路/电机驱动/MotroDrive/) | 该版验证结果未记录 |
| Rev2N | 闪光灯转接 FlashAdapter | 未编号，2025-11-23 版 | [闪光灯转接](电路/闪光灯转接/FlashAdapter/) | 工程未标版本号 |
| Rev3 | 对焦组件 Focus Unit Drive | 1.0 | [对焦组件](电路/对焦组件/) | STM32F030F4 |
| Rev3 | 主控器 PM_Controller | 2.0 | [当前主控](电路/主控器/PM_Controller/) | ESP32-S3；装配已确认，已投产，待首件验证 |

- 主控器 1.3 丝印为 Rev1.2；电机驱动 1.2 丝印为 Rev1.0。两者均未找到按当前设计版本命名的加工包，使用旧包前需核对内容。主控器归档细节见[版本说明](电路/主控器/主要历史版本/PM_Controller_Rev1.3/版本说明.md)。
- 主控器 2.0 的加工包为 [PM_Controller_2.0.zip](电路/主控器/PM_Controller/production/PM_Controller_2.0.zip)。首件待办见 [README](ReadMe.md#pm_controller-rev-20-状态与-features)。
- Rev2N 的 DispKey、电机驱动和闪光灯转接板尚未确认适用于 Rev3。

固件对应关系见软件仓库的[软件与 PCB 兼容性表](../PolaMiyaSoftware/软件与PCB兼容性表.md)。
