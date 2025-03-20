# 中文Chinese
# NexGen ISA

NexGen ISA 是一个全新的指令集架构，专为高性能计算和游戏优化设计。它完全独立于 RISC-V，但保持二进制兼容性，支持标量、向量、矩阵和张量计算。本仓库包含完整的指令集定义、CSV 对照表和开发文档。

## 指令集特性

- **高性能计算**：支持 512 位向量寄存器和 4x4 矩阵运算。
- **游戏优化**：内置光线追踪、物理碰撞检测和纹理采样指令。
- **操作系统支持**：完整支持虚拟内存、多核调度和系统调用。
- **设备驱动**：提供 UART、SPI、I2C、GPU 和音频设备驱动指令。
- **中断优先级**：支持 16 级中断优先级。
- **CSR 扩展**：支持硬件线程管理和定时器。

## 指令集 CSV 文件(指令.csv)

**涵盖以下类别**：

1. **标量指令**：整数和浮点运算。
2. **向量指令**：SIMD 加速计算。
3. **矩阵指令**：4x4 矩阵运算。
4. **内存管理**：加载、存储和内存屏障。
5. **特权指令**：系统调用、异常处理和 CSR 操作。
6. **原子操作**：多核同步支持。
7. **I/O 指令**：设备交互和配置。
8. **设备驱动指令**：UART、SPI、I2C、GPU 和音频设备支持。
9. **CSR 定义**：新增 10 个 CSR，支持硬件线程管理和定时器。

## 开发指南

### 1. CPU 设计

- **流水线**：建议采用 7 级流水线（取指、译码、发射、执行、内存、写回、提交）。
- **缓存**：分离式 L1 Cache，共享 L2 Cache。
- **分支预测**：TAGE-SC 预测器 + RAS 返回地址栈。

### 2. 操作系统移植

- **Linux 内核**：实现 `arch/nexgen/` 目录，支持虚拟内存、中断处理和系统调用。
- **Debian 根文件系统**：使用 `debootstrap` 构建基础系统，配置内核启动参数。

### NexGen ISA 采用固定 32 位指令长度，支持以下编码格式：
- R-Type	opcode[6] + rd[5] + funct3[3] + rs1[5] + rs2[5] + funct7[7]	 寄存器-寄存器操作
- I-Type	opcode[6] + rd[5] + funct3[3] + rs1[5] + imm[12]	立即数操作
- S-Type	opcode[6] + imm[5] + funct3[3] + rs1[5] + rs2[5] + imm[7]	存储操作
- B-Type	opcode[6] + imm[5] + funct3[3] + rs1[5] + rs2[5] + imm[7]	条件分支
- M-Type	opcode[6] + rd[5] + funct3[3] + rs1[5] + rs2[5] + funct7[7]	矩阵操作
- V-Type	opcode[6] + vd[5] + funct3[3] + vs1[5] + vs2[5] + funct7[7]	向量操作

## 联系方式

- 邮箱：**studiofp@126.com**
# 英语English
# NexGen ISA
NexGen ISA is a brand-new instruction set architecture specifically designed for high-performance computing and gaming optimization. It is entirely independent of RISC-V but maintains binary compatibility, supporting scalar, vector, matrix, and tensor computations. This repository contains the complete instruction set definition, CSV reference tables, and development documentation.

## Instruction Set Features
- **High-Performance Computing**: Supports 512-bit vector registers and 4x4 matrix operations.

- **Gaming Optimization**: Built-in instructions for ray tracing, physical collision detection, and texture sampling.

- **Operating System Support**: Full support for virtual memory, multi-core scheduling, and system calls.

- **Device Drivers**: Provides instructions for UART, SPI, I2C, GPU, and audio device drivers.

- **Interrupt Priority**: Supports 16 levels of interrupt priority.

- **CSR Extension**: Supports hardware thread management and timers.

## Instruction Set CSV File (指令.csv)
- **Covers the following categories**:

- **Scalar Instructions**: Integer and floating-point operations.

- **Vector Instructions**: SIMD-accelerated computations.

- **Matrix Instructions**: 4x4 matrix operations.

- **Memory Management**: Load, store, and memory barrier instructions.

- **Privileged Instructions**: System calls, exception handling, and CSR operations.

- **Atomic Operations**: Multi-core synchronization support.

- **I/O Instructions**: Device interaction and configuration.

- **Device Driver Instructions**: Support for UART, SPI, I2C, GPU, and audio devices.

- **CSR Definitions**: Adds 10 new CSRs for hardware thread management and timers.

## Development Guide
### 1. CPU Design
- **Pipeline**: A 7-stage pipeline is recommended (fetch, decode, issue, execute, memory, writeback, commit).

- **Cache**: Separate L1 Cache with shared L2 Cache.

- **Branch Prediction**: TAGE-SC predictor + RAS return address stack.

### 2. Operating System Porting
- **Linux Kernel**: Implement the arch/nexgen/ directory to support virtual memory, interrupt handling, and system calls.

- **Debian Root Filesystem**: Use debootstrap to build the base system and configure kernel boot parameters.

### NexGen ISA uses a fixed 32-bit instruction length and supports the following encoding formats:
- R-Type: opcode[6] + rd[5] + funct3[3] + rs1[5] + rs2[5] + funct7[7] (Register-Register operations)

- I-Type: opcode[6] + rd[5] + funct3[3] + rs1[5] + imm[12] (Immediate operations)

- S-Type: opcode[6] + imm[5] + funct3[3] + rs1[5] + rs2[5] + imm[7] (Store operations)

- B-Type: opcode[6] + imm[5] + funct3[3] + rs1[5] + rs2[5] + imm[7] (Conditional branches)

- M-Type: opcode[6] + rd[5] + funct3[3] + rs1[5] + rs2[5] + funct7[7] (Matrix operations)

- V-Type: opcode[6] + vd[5] + funct3[3] + vs1[5] + vs2[5] + funct7[7] (Vector operations)

## Contact Information

- Email: **studiofp@126.com**

