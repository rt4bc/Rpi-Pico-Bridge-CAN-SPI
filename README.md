# CAN to SPI Controller Based on MCP2518FD and Raspberry Pi Pico

## Description

This project is a CAN-to-SPI controller built using the MCP2518FD CAN controller and the Raspberry Pi Pico (RP2040). It allows communication between CAN and SPI-enabled devices, making it useful for embedded applications, automotive networks, and industrial control systems.

RP2040's SPI1&I2C1 defaualt configured as a controller, which make it possbile bridge the CAN bus and other SPI&I2C peripherals.

![RP2040-CAN-Bridge](https://github.com/rt4bc/Rpi-Pico-Bridge-CAN-SPI/blob/master/output/RP2040-Bridge-CAN-SPI.png)

## Features
- Built with Raspberry Pi Pico (RP2040) and MCP2518FD
- RP2040 SPI1 as SPI controller which can communicate with mikro interface
- RP2040 SPI0 as SPI controller which works with MCP2518FD
- CAN FD support (up to 8 Mbps)
- Supports standard and extended CAN IDs
- Configurable bit rates and filters

## Hardware Requirements

- Raspberry Pi Pico (RP2040)
- MCP2518FD CAN controller with SPI interface
- Power supply (3.3V/5V depending on CAN transceiver)
- Optional: CAN bus terminator (120Ω)

## Software Setup

1. Clone this fw repository.
2. Use PC GUI 

## Usage

Send SPI commands to the Pico, which will translate and forward them to the CAN bus via MCP2518FD. Incoming CAN messages are forwarded back to the host via SPI.

## TODO

- CAN Bus GUI Tools
- USB configure tools

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

## 硬件需求

- Raspberry Pi Pico（RP2040）
- MCP2518FD（SPI接口）
- 电源（3.3V 或 5V，视 CAN 收发器而定）
- 可选：CAN 总线终端电阻（120Ω）

## 软件配置

1. 克隆本项目代码。
3. 将主控设备通过 SPI 接口连接到 Pico。
4. 使用 SPI 库与 Pico 通信并发送/接收 CAN 消息。

## 使用说明

主控系统通过 SPI 向 Pico 发送命令，Pico 再通过 MCP2518FD 将其转发至 CAN 总线。同时，CAN 总线接收到的数据也会被 Pico 通过 SPI 回传至主控系统。

