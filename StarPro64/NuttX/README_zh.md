# Apache NuttX on StarPro64 (EIC7700X) 测试报告

## 测试环境

### 系统信息
- **系统版本**: Apache NuttX RTOS 12.4.0
- **编译分支**: `starpro64` (nuttx & apps)
- **引导方式**: TFTP 网络引导
- **下载链接**:
  - NuttX 源码 (StarPro64 分支): [https://github.com/lupyuen2/wip-nuttx/tree/starpro64](https://github.com/lupyuen2/wip-nuttx/tree/starpro64)
  - Apps 源码 (StarPro64 分支): [https://github.com/lupyuen2/wip-nuttx-apps/tree/starpro64](https://github.com/lupyuen2/wip-nuttx-apps/tree/starpro64)
- **参考安装文档**:
  - [NuttX Official StarPro64 Documentation](https://nuttx.apache.org/docs/latest/platforms/risc-v/eic7700x/boards/starpro64/index.html)
  - [Lup Yuen's StarPro64 NuttX Porting Guide](https://github.com/lupyuen/nuttx-starpro64)

### 硬件信息
- StarPro64 (EIC7700X) 开发板
- USB 串口线 (用于控制台交互)
- 建议配备外部散热风扇 (防止 PLL/Thermal 错误)

## 安装步骤
下载源代码
克隆 NuttX 主线代码仓库与 apps 应用代码仓库的 starpro64 分支。

配置与构建
对构建系统进行配置。

导入应用并编译
将应用层代码整合至内核构建系统中完成编译。

镜像打包
生成初始内存盘（InitRD），并将其与内核打包为一体


#### U-Boot 引导 (TFTP)
在 StarPro64 的 U-Boot 串口终端中执行以下命令（请根据实际网络环境修改 IP）：

```bash
# 假设 TFTP 服务器 IP 为 192.168.31.10
setenv tftp_server 192.168.31.10

# 通过网络下载内核与设备树
dhcp ${kernel_addr_r} ${tftp_server}:Image-starpro64
tftpboot ${fdt_addr_r} ${tftp_server}:jh7110-star64-pine64.dtb

# 设置设备树地址并启动
fdt addr ${fdt_addr_r}
booti ${kernel_addr_r} - ${fdt_addr_r}
```

## 预期结果
系统应能通过网络引导成功，U-Boot 加载内核后，串口终端正常进入 NuttShell (NSH) 交互界面。

## 实际结果
Basic

## 测试判定标准

测试成功：实际结果与预期结果相符。

测试失败：实际结果与预期结果不符。

## 测试结论

测试成功