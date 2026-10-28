<!-- GitHub 主页 README · 徐创 仓库：koko-PhyuHtwe/koko-PhyuHtwe 内容取自简历 v12（嵌入式版）；只剩「博客徽章」需要你决定要不要加。 --> <!-- 想启用顶部横幅？删掉下面这段注释的两行标记即可（assets/ 里已备好深浅两版）： <picture> <source media="(prefers-color-scheme: dark)" srcset="./assets/banner-dark.svg"> <source media="(prefers-color-scheme: light)" srcset="./assets/banner-light.svg"> <img alt="徐创 · 嵌入式软件工程师" src="./assets/banner-light.svg" width="100%"> </picture> --> <div align="center">
徐创
<sub>嵌入式软件工程师  ·  2027 届本科应届</sub>

<br><br>

在 S32K144 和 STM32 上写 C：Bootloader、UDS、CAN、FreeRTOS。

<br><br>

<a href="mailto:1368559499@qq.com"><img alt="Email" src="https://img.shields.io/badge/1368559499@qq.com-24292F?style=flat-square&logo=gmail&logoColor=white"></a>   <a href="https://github.com/koko-PhyuHtwe"><img alt="GitHub" src="https://img.shields.io/badge/koko--PhyuHtwe-24292F?style=flat-square&logo=github&logoColor=white"></a>

</div>
关于
2027 届本科应届，南京工业职业技术大学 · 汽车服务工程，求职方向：嵌入式软件开发 / 汽车电子。
两个项目都是从零做到硬件联调：自研的 A/B 双分区 Bootloader，和一套 MBD 建模 → 生成 C → 双 ECU 闭环的换挡器。
更愿意盯异常路径 —— 掉电、超时、NRC 码，比正常流程更值得写进代码。
技术栈
语言<br> <img alt="C" src="https://img.shields.io/badge/C-24292F?style=flat-square&logo=c&logoColor=white"> <img alt="Python" src="https://img.shields.io/badge/Python-24292F?style=flat-square&logo=python&logoColor=white">

平台<br> <img alt="S32K144" src="https://img.shields.io/badge/S32K144-24292F?style=flat-square"> <img alt="STM32G474" src="https://img.shields.io/badge/STM32G474-24292F?style=flat-square"> <img alt="FreeRTOS" src="https://img.shields.io/badge/FreeRTOS-24292F?style=flat-square">

协议<br> <img alt="CAN" src="https://img.shields.io/badge/CAN_2.0B-24292F?style=flat-square"> <img alt="UDS" src="https://img.shields.io/badge/UDS_ISO_14229-24292F?style=flat-square"> <img alt="ISO 15765-2" src="https://img.shields.io/badge/ISO_15765--2-24292F?style=flat-square"> <img alt="UART" src="https://img.shields.io/badge/UART-24292F?style=flat-square">

工具<br> <img alt="CANoe" src="https://img.shields.io/badge/CANoe_/_CAPL-24292F?style=flat-square"> <img alt="Simulink" src="https://img.shields.io/badge/Simulink_/_Stateflow-24292F?style=flat-square"> <img alt="S32DS" src="https://img.shields.io/badge/S32DS-24292F?style=flat-square"> <img alt="Git" src="https://img.shields.io/badge/Git-24292F?style=flat-square&logo=git&logoColor=white">

项目
S32K144 Bootloader 固件升级系统
NXP S32K144 · CAN 500 kbps · UDS · CANoe CAPL · 2026.06 – 至今

A/B 双分区在线刷写，断电可回滚 —— 最坏停在 Bootloader，不会跳错固件。

分区：Boot 56 KB + A/B 224 KB×2，只擦非激活槽；提交时改写 0xF000 处 80 字节分区表，新旧槽在同一张表里翻转落盘。
协议栈：FlexCAN 500 kbps（0x7E0/0x7E8）实现 8 个 UDS 服务 —— 0x10 0x11 0x22 0x27 0x2E 0x34 0x36 0x37，含 Seed-Key 与 S3 超时。
跳转：CRC32（0xEDB88320 查表）双点比对；跳转前 Deinit 外设、VTOR 重定向、校验 MSP，消掉 App 侧 HardFault。
验证：CAPL 自动刷写，0x22 选 bin、200 ms 超时重试 5 次、0x73 重同步，注入 6 类异常；全部命中预期 NRC（0x33 0x35 0x36 0x72 0x73）。
电子换挡器 MBD 开发与双 ECU 联调
Simulink / Stateflow · Embedded Coder · S32K144 + STM32G474 · FreeRTOS · 2026.04 – 2026.08

从模型到双板硬件的闭环：建模 → 生成 C → 移植 → CAN 联调。

流程：Stateflow 建模后经 Embedded Coder 出码并移植到 S32K144，处理 C Action Language 不支持 else-if 等落地问题。
逻辑：P/R/N/D 逐级换挡 + M1–M6 手动模式状态机，x_prev 自锁防连跳，叠加车速门槛与红区强制升降挡。
联调：CAN 闭环 0x180 目标档 / 0x280 实际档，FreeRTOS 10 ms 调度；500 ms 无帧判 FAULT，STM32G474 保持当前档位。
竞赛
时间	竞赛	结果
2024.08	全国大学生电子设计竞赛（控制类）· MSPM0 循迹小车	省级一等奖
2024.04	蓝桥杯大赛（电子类 · 嵌入式）	省级二等奖
教育
南京工业职业技术大学 · 汽车服务工程（全日制本科）

2023.09 – 2027.06 ｜ C 语言 · 嵌入式系统开发 · 车载网络控制技术 · 汽车电气与电控技术

现在
<p> <b>在做</b>　继续打磨 S32K144 Bootloader：补异常用例、补文档<br> <b>在找</b>　2027 届嵌入式软件开发 / 汽车电子方向（校招） </p>
<p align="center"> <sub>写代码，也写清楚为什么。</sub> </p>
