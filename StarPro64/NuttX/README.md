---
vendor: ESWIN
product: StarPro64
cpu: EIC7700X
cpu_core: SiFive P550
ram: 32G LPDDR5

sys: Apache NuttX RTOS
sys_ver: "12.4.0"
status: basic
last_updated: 2026-01-17
---

# Apache NuttX on StarPro64 (EIC7700X) Test Report

## Test Environment

### System Information
- **System Version**: Apache NuttX RTOS 12.4.0
- **Build Branch**: `starpro64` (nuttx & apps)
- **Boot Method**: TFTP Network Boot
- **Download Links**:
  - NuttX Source (StarPro64 Branch): [https://github.com/lupyuen2/wip-nuttx/tree/starpro64](https://github.com/lupyuen2/wip-nuttx/tree/starpro64)
  - Apps Source (StarPro64 Branch): [https://github.com/lupyuen2/wip-nuttx-apps/tree/starpro64](https://github.com/lupyuen2/wip-nuttx-apps/tree/starpro64)
- **Reference Installation Document**:
  - [NuttX Official StarPro64 Documentation](https://nuttx.apache.org/docs/latest/platforms/risc-v/eic7700x/boards/starpro64/index.html)
  - [Lup Yuen's StarPro64 NuttX Porting Guide](https://github.com/lupyuen/nuttx-starpro64)

### Hardware Information
- StarPro64 (EIC7700X) Development Board
- USB Serial Cable
- External cooling fan recommended

## Installation Steps

Download Source Code
Clone the `starpro64` branch of the NuttX mainline and apps repositories

Configure and Build
Configure the build system

Import Apps and Compile
Import the application layer into the kernel build system

Pack Image
Generate the Initial RAM Disk (InitRD) and pack it with the kernel

####  U-Boot Boot (TFTP)
Execute the following commands in the StarPro64 U-Boot serial terminal (please modify the IP according to your actual network environment):

```bash
# Assuming TFTP server IP is 192.168.31.10
setenv tftp_server 192.168.31.10

# Download kernel and device tree via network
dhcp ${kernel_addr_r} ${tftp_server}:Image-starpro64
tftpboot ${fdt_addr_r} ${tftp_server}:jh7110-star64-pine64.dtb

# Set device tree address and boot
fdt addr ${fdt_addr_r}
booti ${kernel_addr_r} - ${fdt_addr_r}
```

## Expected Results
The system should be able to boot successfully via network. After U-Boot loads the kernel, the serial terminal should normally enter the NuttShell (NSH) interactive interface.

## Actual Results

Basic

## Test Criteria

Successful: The actual result matches the expected result.

Failed: The actual result does not match the expected result.

## Test Conclusion

Test successful.
