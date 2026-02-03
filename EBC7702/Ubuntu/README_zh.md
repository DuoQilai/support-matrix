# Ubuntu ESWIN EBC7702 测试报告

## 测试环境

### 系统信息

- **系统版本**：Ubuntu 24.04.2 LTS
- **镜像文件**：`d560-ubuntu-24.04-preinstalled-server-riscv64_20251210_2234_40.img.zst`
- **下载链接**：
  - [ESWIN Computing GitHub Releases](https://github.com/eswincomputing/ebc7702-dev-board-ubuntu/releases)
  - [Ubuntu RISC-V Partner Images](https://ubuntu.com/download/risc-v/partner-built)
- **参考安装文档**：
  - [EBC7702 Dev Board Ubuntu Guide](https://github.com/eswincomputing/ebc7702-dev-board-ubuntu)

### 硬件信息

- EBC7702 系列主板 
- Type-C USB 数据线 
- USB 闪存盘 
- 串口终端软件 

## 安装步骤

### 烧录 Bootloader

将 USB 盘插入开发板下方接口，连接串口并上电，进入 U-Boot 终端交互模式。

烧录 die0
加载并烧录第一个 Bootloader 文件.

烧录 die1
加载并烧录第二个 Bootloader 文件.

Ubuntu 镜像
将系统镜像写入存储介质 (MMC).

烧录完成后，执行重启命令


## 预期结果

 系统重启后能正常引导，串口出现登录提示符。


## 实际结果

Basic

### 启动信息


```log
[  OK  ] Started Getty on ttyS0.
[  OK  ] Reached target Login Prompts.

Ubuntu 24.04.2 LTS ebc7702 ttyS0

ebc7702 login: ubuntu
Password: 
Welcome to Ubuntu 24.04.2 LTS (GNU/Linux 6.x.x riscv64)
```

## 测试判定标准

测试成功：实际结果与预期结果相符。

测试失败：实际结果与预期结果不符。

## 测试结论

测试成功。