# OpenWrt Banana Pi BPI-RV2 测试报告

## 测试环境

### 系统信息

- **系统版本**：OpenWrt 24.10 BSP (Snapshot/Master)
- **编译环境**：Ubuntu 20.04/22.04 LTS (x64)
- **参考资料**：
  - 项目源码: [https://github.com/openwrt/openwrt](https://github.com/openwrt/openwrt)
  - 编译指南: [https://openwrt.org/docs/guide-developer/build-system/install-buildsystem](https://openwrt.org/docs/guide-developer/build-system/install-buildsystem)

### 硬件信息

- Banana Pi BPI-RV2
- MicroSD 卡（建议 Class 10, 8GB+）及读卡器
- USB 转 UART 串口调试器（波特率通常为 115200）

## 安装步骤

### 搭建构建环境

安装编译依赖

在 Ubuntu 宿主机上更新并安装 OpenWrt 编译所需的依赖包

下载源码

克隆 OpenWrt 官方仓库（或 BPI 指定分支）

### 刷入系统镜像

编译完成后，镜像通常位于 `bin/targets/[架构]/[子架构]/` 目录下


### 登录系统

连接串口调试器（TX->RX, RX->TX, GND->GND）。上电启动。


## 预期结果

开发板上电后串口有 U-Boot 和 Kernel 日志输出，最终进入 Shell。

## 实际结果

CFT

### 启动信息


```log
[    0.000000] Linux version 5.x.x ...
...
Press please press Enter to activate this console.
root@OpenWrt:/#
```

## 测试判定标准

测试成功：实际结果与预期结果相符。

测试失败：实际结果与预期结果不符。

## 测试结论

CFT
