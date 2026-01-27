# Space-ROS BeagleV-Fire 测试报告

## 测试环境

### 操作系统信息
- **系统版本**：Space-ROS 5.1 (基于 Yocto Project)
- **下载链接**：
  - 项目源码: [https://github.com/yassine-cherni/beaglev-fire-space-ros](https://github.com/yassine-cherni/beaglev-fire-space-ros)
  - KAS 构建工具: [https://github.com/siemens/kas](https://github.com/siemens/kas)
- **参考安装文档**：
  - [Space ROS 官方文档](https://space-ros.github.io/docs/rolling/index.html)
  - [BeagleV-Fire 官方文档](https://docs.beagleboard.org/boards/beaglev/fire/index.html)

### 硬件信息
- BeagleV-Fire 开发板
- USB-C 数据线
- microSD 卡及读卡器
- Ubuntu 22.04/24.04 LTS 

## 安装步骤

搭建构建环境与下载源码
在 Ubuntu 宿主机上安装 Docker 和 KAS 工具，并拉取项目代码

构建系统镜像
使用 KAS 容器环境编译最小化文件系统


### 刷入系统镜像 

将生成的镜像文件写入 microSD 卡：

```bash
cd build/tmp/deploy/images/beaglev-fire/
sudo dd if=core-image-minimal-beaglev-fire.wic of=/dev/sdX bs=4M status=progress conv=fsync
```

### 登录系统 

使用串口工具（波特率 115200）连接并观察启动日志。

## 预期结果
烧录后的 SD 卡能引导开发板进入 Linux 系统。
系统启动后能通过串口免密登录。

## 实际结果

CFT

**启动信息：未验证**

- 具体的启动日志和运行截图待补充。

## 测试判定标准

测试成功：实际结果与预期结果相符。

测试失败：实际结果与预期结果不符。

## 测试结论

CFT