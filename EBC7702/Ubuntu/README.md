---
vendor: ESWIN
product: EBC7702
cpu: EIC7702X
cpu_core: SiFive P550
ram: 32G/64G LPDDR5

sys: ubuntu
sys_ver: "24.04.2"
sys_var: server-riscv64
status: basic
last_updated: 2026-01-17
---

# Ubuntu ESWIN EBC7702 Test Report

## Test Environment

### Operating System Information

- System Version: Ubuntu 24.04.2 LTS
- Image File: `d560-ubuntu-24.04-preinstalled-server-riscv64_20251210_2234_40.img.zst`
- Download Links:
  - [ESWIN Computing GitHub Releases](https://github.com/eswincomputing/ebc7702-dev-board-ubuntu/releases)
  - [Ubuntu RISC-V Partner Images](https://ubuntu.com/download/risc-v/partner-built)
- Reference Installation Document:
  - [EBC7702 Dev Board Ubuntu Guide](https://github.com/eswincomputing/ebc7702-dev-board-ubuntu)

### Hardware Information

- T EBC7702 Series Motherboard 
- Type-C USB Data Cable 
- USB Flash Drive 
- Serial Terminal Software 

## Installation Steps

### Flash Bootloader

Insert the USB drive into the interface at the bottom of the development board, connect the serial port, power on, and enter the U-Boot terminal interaction mode.

Flash die0
Load and flash the first Bootloader file

Flash die1
Load and flash the second Bootloader file (note the parameter `1` at the end of the command)

Flash Ubuntu Image
Write the system image to the storage medium (MMC)

After flashing is complete, execute the reboot command

## Expected Results

The system boots normally after reboot, and the login prompt appears on the serial port.

## Actual Results

Basic

### Boot Log

*(Excerpt from actual test logs)*

```log
[  OK  ] Started Getty on ttyS0.
[  OK  ] Reached target Login Prompts.

Ubuntu 24.04.2 LTS ebc7702 ttyS0

ebc7702 login: ubuntu
Password: 
Welcome to Ubuntu 24.04.2 LTS (GNU/Linux 6.x.x riscv64)
```

## Test Criteria

Test Success: Actual results match expected results.

Test Failure: Actual results do not match expected results.

## Test Conclusion

Test successful
