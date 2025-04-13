# CAN to SPI Controller Based on MCP2518FD and Raspberry Pi Pico

## Description

This project is a CAN-to-SPI controller built using the MCP2518FD CAN controller and the Raspberry Pi Pico (RP2040). It allows communication between CAN and SPI-enabled devices, making it useful for embedded applications, automotive networks, and industrial control systems.

## Features

- CAN FD support (up to 8 Mbps)
- SPI interface to host system
- Supports standard and extended CAN IDs
- Configurable bit rates and filters
- Built with Raspberry Pi Pico (RP2040) and MCP2518FD
- Easy-to-modify firmware in C/C++ or MicroPython

## Hardware Requirements

- Raspberry Pi Pico (RP2040)
- MCP2518FD CAN controller with SPI interface
- TJA1051 or equivalent CAN transceiver
- Power supply (3.3V/5V depending on CAN transceiver)
- Optional: CAN bus terminator (120Ω)

## Pin Connections

| MCP2518FD | Pico (RP2040) |
|-----------|----------------|
| SCK       | GP2 (SPI0 SCK) |
| MOSI      | GP3 (SPI0 TX)  |
| MISO      | GP4 (SPI0 RX)  |
| CS        | GP5 (Chip Select) |
| INT       | GP6 (Interrupt) |
| GND       | GND            |
| VCC       | 3.3V           |

## Software Setup

1. Clone this repository.
2. Flash the provided firmware to the Raspberry Pi Pico using [Thonny](https://thonny.org/) or other uploader tools.
3. Connect to the device via SPI on the host system.
4. Use your preferred SPI library to send/receive CAN messages.

## Usage

Send SPI commands to the Pico, which will translate and forward them to the CAN bus via MCP2518FD. Incoming CAN messages are forwarded back to the host via SPI.

## TODO

- Add Python/C demo for host-side communication
- Add support for CAN filters
- Add error handling/logging

---

# 基于 MCP2518FD 和 Raspberry Pi Pico 的 CAN 转 SPI 控制器

## 项目简介

本项目基于 MCP2518FD CAN 控制器和 Raspberry Pi Pico（RP2040）实现了一个 CAN 到 SPI 的通信控制器。该控制器可以实现 CAN 与 SPI 设备之间的通信，广泛适用于嵌入式系统、汽车网络以及工业控制系统。

## 功能特点

- 支持 CAN FD（速率最高达 8 Mbps）
- SPI 接口连接主控系统
- 支持标准帧和扩展帧格式
- 可配置的波特率与过滤器
- 采用 Raspberry Pi Pico 和 MCP2518FD 芯片
- 固件易于使用 C/C++ 或 MicroPython 修改

## 硬件需求

- Raspberry Pi Pico（RP2040）
- MCP2518FD（SPI接口）
- TJA1051 或兼容 CAN 收发器
- 电源（3.3V 或 5V，视 CAN 收发器而定）
- 可选：CAN 总线终端电阻（120Ω）

## 引脚连接

| MCP2518FD | Pico (RP2040) |
|-----------|----------------|
| SCK       | GP2（SPI0 SCK）|
| MOSI      | GP3（SPI0 TX） |
| MISO      | GP4（SPI0 RX） |
| CS        | GP5（片选）     |
| INT       | GP6（中断）     |
| GND       | GND            |
| VCC       | 3.3V           |

## 软件配置

1. 克隆本项目代码。
2. 使用 [Thonny](https://thonny.org/) 或其他烧录工具将固件烧录到 Pico。
3. 将主控设备通过 SPI 接口连接到 Pico。
4. 使用 SPI 库与 Pico 通信并发送/接收 CAN 消息。

## 使用说明

主控系统通过 SPI 向 Pico 发送命令，Pico 再通过 MCP2518FD 将其转发至 CAN 总线。同时，CAN 总线接收到的数据也会被 Pico 通过 SPI 回传至主控系统。

## 待办事项

- 添加 Python/C 示例程序（主机端）
- 支持更多 CAN 过滤器功能
- 添加错误处理与日志功能
