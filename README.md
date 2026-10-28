<div align="center">

### 徐创 · XU CHUANG

`嵌入式软件工程师` · `2027 届` · `汽车电子 / 车载网络`

[![Email](https://img.shields.io/badge/1368559499@qq.com-D14836?style=flat-square&logo=gmail&logoColor=white)](mailto:1368559499@qq.com)
[![GitHub](https://img.shields.io/badge/koko--PhyuHtwe-181717?style=flat-square&logo=github&logoColor=white)](https://github.com/koko-PhyuHtwe)

</div>

---

### 👋 你好，我是徐创

> 「让每一帧 CAN 报文都准时到达，让每一次刷写都能回滚。」

2027 届本科应届，就读于 **南京工业职业技术大学 · 汽车服务工程**。
日常在 **NXP S32K144 / STM32G474** 上写 C：Bootloader、UDS 诊断、CAN 通信、FreeRTOS 调度。
比起调界面，我更愿意盯着示波器和 CANoe 的 trace，找那个丢掉的字节。

### 🛠 技术栈

| | |
|:--|:--|
| **语言** | `C` `Python` |
| **芯片** | `S32K144` `STM32G474` |
| **总线 / 协议** | `CAN 2.0B` `UDS ISO 14229` `ISO 15765-2` `UART` |
| **实时系统** | `FreeRTOS` |
| **模型开发** | `Simulink` `Stateflow` `Embedded Coder` |
| **工具链** | `S32DS` `CANoe` `CAPL` `PCAN-View` `J-Link` `Git` |

### 🚀 项目

**[s32k144-uds-bootloader](https://github.com/koko-PhyuHtwe/s32k144-uds-bootloader)** — 在 S32K144 上从零写一个真能用的 UDS Bootloader

- A/B 双分区：Boot 56 KB + App 224 KB × 2，`0xF000` 处 80 字节分区表记录有效区与版本
- FlexCAN `0x7E0` 请求 / `0x7E8` 响应，ISO 15765-2 分包重组，CRC32（多项式 0xEDB88320）
- 覆盖 `0x10 / 0x11 / 0x22 / 0x27 / 0x2E / 0x34 / 0x36 / 0x37`
- 构造 6 类异常场景，验证 NRC 返回 `0x33 / 0x35 / 0x36 / 0x72 / 0x73`

**[electronic-shifter-mbd](https://github.com/koko-PhyuHtwe/electronic-shifter-mbd)** — Simulink + FreeRTOS 的电子换挡控制器

- CAN `0x180` 下发目标档，`0x280` 回读实际档
- FreeRTOS 10 ms 周期任务，500 ms 收不到帧即进 FAULT
- P/R/N/D + M1–M6 档位逻辑，Stateflow 建模，Embedded Coder 生成代码

### 🏆 竞赛

- 全国大学生电子设计竞赛（控制类）· 省级一等奖 · 2024.08
- 蓝桥杯（电子类 · 嵌入式）· 省级二等奖 · 2024.04

### 📫 联系

- 📧 邮箱：[1368559499@qq.com](mailto:1368559499@qq.com)
- 💬 嵌入式、汽车电子、实习机会，都欢迎直接发邮件

<div align="center">

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:1F6FEB,100:58A6FF&height=110&section=footer" width="100%" alt="">

</div>