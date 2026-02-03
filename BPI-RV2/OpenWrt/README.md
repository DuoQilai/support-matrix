---
vendor: BananaPi
product: Banana Pi BPI-RV2
cpu: SF21H8898
cpu_core: XuanTie C908
ram: 512MB DDR3

sys: openwrt
sys_ver: "24.10"
sys_var: bsp
status: wip
last_updated: 2026-01-17
---

# OpenWrt Banana Pi BPI-RV2 Test Report

## Test Environment

### Operating System Information

- System Version: OpenWrt 24.10 BSP (Snapshot/Master)
- Build Environment: Ubuntu 20.04/22.04 LTS (x64)
- Reference Material:
  - Project Source: [https://github.com/openwrt/openwrt](https://github.com/openwrt/openwrt)
  - Build Guide: [https://openwrt.org/docs/guide-developer/build-system/install-buildsystem](https://openwrt.org/docs/guide-developer/build-system/install-buildsystem)

### Hardware Information

- Banana Pi BPI-RV2
- MicroSD Card  and Card Reader
- USB to UART Serial Debugger

## Installation Steps

### Setup Build Environment

Install Compilation Dependencies

Update and install the required dependencies for OpenWrt compilation on the Ubuntu host

Download Source Code

Clone the official OpenWrt repository (or the specific BPI branch)

### Flash Image

After compilation is complete, the image is usually located in the `bin/targets/[architecture]/[subtarget]/` directory.


### Boot and Log In to System

Connect the serial debugger (TX->RX, RX->TX, GND->GND).
Power on and observe the serial output.


## Expected Results

 After the board powers on, U-Boot and Kernel logs appear on the serial port, finally entering the Shell.

## Actual Results

CFT

### Boot Log


```log
[    0.000000] Linux version 5.x.x ...
...
Press please press Enter to activate this console.
root@OpenWrt:/#
```

## Test Criteria

Successful: The actual result matches the expected result.

Failed: The actual result does not match the expected result.

## Test Conclusion

CFT
