# 结构与 PCB 兼容性表

更新日期：2026-09-29。

本表记录已确认的结构与 PCB 对应关系，结构版本与 PCB 版本独立编号。**Rev2N 的既有电路与 Rev3 对焦组件按下表对应；新增主控器 Rev 2.0 单列为开发中，结构兼容性待确认。**

PCB 版本以对应 `.kicad_pcb` 标题栏的 `rev` 为准，并核对原理图；未标注版本的板不推定版本号。Rev2N 主控板及与其绑定的 Display Key 指向同一历史版本目录，其他板指向现有工程。本表记录版本归属，不代表已完成各板的装配、电气联调或新版投产验证，也不推定 Rev3 整机其余电路的兼容性。

## 兼容性表

| 对应结构 | PCB / 功能 | 当前 PCB 版本 | 设计文件 | 版本与投产资料说明 |
| --- | --- | --- | --- | --- |
| Rev2N | 主控板 PM_Controller | **Rev 1.3（冻结归档）** | [PM_Controller.kicad_pcb](电路/主控器/主要历史版本/PM_Controller_Rev1.3/PM_Controller.kicad_pcb) | **与 Display Key Rev 1.0 绑定使用，一并归档**；PCB / 原理图均为 1.3，PCB 日期为 2026-02-03；丝印仍为 Rev1.2；归档 `production/` 中有 `PM_Controller_1.2.zip` 和 `PM_Controller_Rev1.zip`，未见按 1.3 命名的投产包；见[版本说明](电路/主控器/主要历史版本/PM_Controller_Rev1.3/版本说明.md)。 |
| Rev2N | 显示与按键板 Display Key / DispKey / PM_DISP | **Rev 1.0（配套冻结归档）** | [DispKey.kicad_pcb](电路/主控器/主要历史版本/PM_Controller_Rev1.3/DispKey/DispKey.kicad_pcb) | **与 PM_Controller Rev 1.3 绑定使用**；PCB / 原理图均为 1.0，PCB 日期为 2025-06-04；投产包为 `PM_DISP_1.0.zip`，与主控板一并归档。 |
| Rev2N | 吐片电机驱动板 MotroDrive | **Rev 1.2** | [MotroDrive.kicad_pcb](电路/电机驱动/MotroDrive/MotroDrive.kicad_pcb) | PCB / 原理图均为 1.2，PCB 日期为 2026-03-15；丝印仍为 Rev1.0；`production/` 中有 `MotroDrive_1.1.zip` 和 `MotroDriveR1_20250410.zip`，未见按 1.2 命名的投产包。 |
| Rev2N | 闪光灯转接板 FlashAdapter | **未标注 Rev（2025-11-23 版）** | [FlashAdapter.kicad_pcb](电路/闪光灯转接/FlashAdapter/FlashAdapter.kicad_pcb) | PCB 标题栏仅标日期 2025-11-23；原理图也未标 Rev；投产包为 `FlashAdapter.zip`，不将其默认记为 1.0。 |
| Rev3 | 对焦组件 / Focus Unit Drive | **Rev 1.0** | [对焦组件.kicad_pcb](电路/对焦组件/对焦组件.kicad_pcb) | PCB / 原理图及丝印均为 1.0，PCB 日期为 2026-09-19；投产包为 `Focus_Unit_Drive_1.0.zip`；[引脚说明](电路/对焦组件/对焦组件_Rev_1.0_PIN.md)。 |
| 待确认（开发中） | 新版主控板 PM_Controller | **Rev 2.0** | [PM_Controller.kicad_pcb](电路/主控器/PM_Controller/PM_Controller.kicad_pcb) | PCB / 原理图标题栏均为 2.0，日期为 2026-09-29；采用 STM32G030K8Tx + ESP32-S3-WROOM-1；尚未确认结构兼容性及电气联调，Display Key Rev 1.0 的历史绑定关系不自动沿用。 |

## 当前改动与版本注意事项

- 主控器 Rev 1.3 完整归档至 `电路/主控器/主要历史版本/PM_Controller_Rev1.3/`，由归档复制建立 `电路/主控器/PM_Controller/` 开发副本。归档时两份电路内容相同；今后开发副本的变更不自动改变 Rev2N 的对应版本。
- 当前开发工程已开始 Rev 2.0 独立设计，旧版库、BOM 和加工输出已从开发目录移除，仍保存在 Rev 1.3 归档中；当前工程与历史归档的电路内容已不同。
- 绑定的 Display Key Rev 1.0 从 `电路/主控器/DispKey/` 整体移至该主控器历史版本的 `DispKey/` 子目录；原有工程、库和加工资料保持不变。
- 对焦组件由 `电路/硬件Rev3电路/对焦组件/` 移至 `电路/对焦组件/`。提交目录调整前已核对 PCB、原理图、工程文件和引脚说明内容一致，本次目录调整不构成 PCB 升版。
- 主控器 Rev 1.3 的提交记录为“硬件1.3版本，调整闪光灯为默认过MCU”（`43d0dd1`）。
- 电机驱动 Rev 1.2 的标题栏记录：升压二极管改为 SS34、修改为单面布局、输入储能电容改为电源 GND；对应提交为“驱动电路升级至R1.2 未验证”（`c09a9e7`），现有记录不能据此认定该版已验证。
- 主控器和电机驱动的当前设计版本与丝印、投产包名称不一致。选择加工文件时应核对实际包内内容；旧版本包不能仅凭目录位置视为当前设计的加工输出。
