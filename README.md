# Basic-RISC-V-CPU

一个基于 RISC-V 指令集的五级流水线 CPU 设计，支持中断、UART、GPIO 和定时器外设。

## 特点

- **五级流水线**：取指(IF)、译码(ID)、执行(EX)、访存(MEM)、写回(WB)
- **RISC-V 基础整数指令集 (RV32I)** + **乘法扩展 (M)**
- **中断支持**：完整的中断响应与返回机制
- **外设支持**：
  - UART 串口通信
  - GPIO（输入/输出/中断）
  - 可编程定时器（中断）
- **仿真与验证**：
  - Modelsim 仿真，可直接观察波形
  - Vivado 综合与烧录，可部署到 FPGA

## 开发环境

| 工具 | 用途 |
|------|------|
| Modelsim | 仿真验证，观察波形 |
| Vivado | 综合、烧录 FPGA |
| Verilog | 硬件描述语言 |

## 快速开始

### 1. 仿真（Modelsim）

```bash
# 打开 Modelsim，进入项目目录
# 编译所有 .v 文件
# 运行仿真 tb_core_top
在波形窗口中添加需要观察的信号，运行仿真即可。

2. 烧录（Vivado）
bash
# 打开 Vivado，创建新项目
# 添加所有 rtl 文件夹下的 .v 文件
# 综合、实现、生成比特流
# 下载到 FPGA 开发板
文件结构
text
Basic-RISC-V-CPU/
├── rtl/               # 所有 RTL 源文件
│   ├── bus/           # 总线仲裁器
│   ├── csr/           # CSR 寄存器
│   ├── exu/           # 执行单元
│   ├── hazard/        # 冒险检测与前递
│   ├── id/            # 译码阶段
│   ├── ifu/           # 取指阶段
│   ├── interrupt/     # 中断控制器
│   ├── mem/           # 访存阶段
│   ├── periph/        # 外设（UART/GPIO/Timer）
│   ├── pipeline/      # 流水线寄存器
│   └── top/           # 顶层模块
├── tb/                # 测试平台
└── docs/              # 文档
地址映射
外设	基址	大小
RAM	0x0000_0000	64KB
UART	0x1000_0000	4KB
GPIO	0x1000_1000	4KB
TIMER	0x1000_2000	4KB
联系方式
作者：易逢鑫 (Yi Fengxin)

单位：北京航空航天大学杭州国际创新研究院

邮箱：

1596215367@qq.com

1596215367@buaa.edu.cn

许可证
本项目仅供学习交流使用。

# Basic-RISC-V-CPU

A 5-stage pipeline RISC-V CPU design with interrupt support, UART, GPIO, and Timer peripherals.

## Features

- **5-Stage Pipeline**: IF (Instruction Fetch), ID (Instruction Decode), EX (Execute), MEM (Memory Access), WB (Write Back)
- **RISC-V Base Integer Instruction Set (RV32I)** + **Multiplication Extension (M)**
- **Interrupt Support**: Complete interrupt handling and return mechanism
- **Peripherals**:
  - UART Serial Communication
  - GPIO (Input/Output/Interrupt)
  - Programmable Timer (Interrupt)
- **Simulation & Deployment**:
  - Modelsim simulation for waveform observation
  - Vivado synthesis and FPGA programming

## Development Environment

| Tool | Purpose |
|------|---------|
| Modelsim | Simulation and waveform observation |
| Vivado | Synthesis and FPGA programming |
| Verilog | Hardware description language |

## Quick Start

### 1. Simulation (Modelsim)

```bash
# Open Modelsim and navigate to the project directory
# Compile all .v files
# Run simulation with tb_core_top
Add desired signals to the waveform window and run the simulation.

2. Programming (Vivado)
bash
# Open Vivado and create a new project
# Add all .v files from the rtl folder
# Run synthesis, implementation, and generate bitstream
# Download to FPGA board
File Structure
text
Basic-RISC-V-CPU/
├── rtl/               # All RTL source files
│   ├── bus/           # Bus arbiter
│   ├── csr/           # CSR registers
│   ├── exu/           # Execution unit
│   ├── hazard/        # Hazard detection & forwarding
│   ├── id/            # Instruction decode
│   ├── ifu/           # Instruction fetch
│   ├── interrupt/     # Interrupt controller
│   ├── mem/           # Memory access
│   ├── periph/        # Peripherals (UART/GPIO/Timer)
│   ├── pipeline/      # Pipeline registers
│   └── top/           # Top module
├── tb/                # Testbench
└── docs/              # Documentation
Memory Map
Peripheral	Base Address	Size
RAM	0x0000_0000	64KB
UART	0x1000_0000	4KB
GPIO	0x1000_1000	4KB
TIMER	0x1000_2000	4KB
Contact
Author: Yi Fengxin

Affiliation: Beijing University of Aeronautics and Astronautics (BUAA), Hangzhou International Innovation Institute

Email:

1596215367@qq.com

1596215367@buaa.edu.cn

License
This project is for educational purposes only.