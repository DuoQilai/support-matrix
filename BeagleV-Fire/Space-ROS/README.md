---
vendor: BeagleV
product: BeagleV-Fire
cpu: MPFS025T
cpu_core: SiFive U54 + SiFive E51
ram: 2G

sys: yocto
sys_ver: "Space-ROS-5.1"
sys_var: beaglev-fire
status: cft
last_updated: 2026-01-17
---

# Space-ROS BeagleV-Fire Test Report

## Test Environment

### Operating System Information

- System Version: Space-ROS 5.1 (Based on Yocto Project)
- Download Link:
  - Project Source: [https://github.com/yassine-cherni/beaglev-fire-space-ros](https://github.com/yassine-cherni/beaglev-fire-space-ros)
  - KAS Build Tool: [https://github.com/siemens/kas](https://github.com/siemens/kas)
- Reference Installation Document:
  - [Space ROS Official Documentation](https://space-ros.github.io/docs/rolling/index.html)
  - [BeagleV-Fire Official Documentation](https://docs.beagleboard.org/boards/beaglev/fire/index.html)

### Hardware Information

- BeagleV-Fire Development Board
- A USB-C Data Cable 
- A microSD card 
- A microSD card reader
- Host Machine: Ubuntu 22.04/24.04 LTS 

## Installation Steps

Set Up Build Environment and Download Source Code
Install Docker and KAS tools on the Ubuntu host, and pull the project code

Build System Image
Compile the minimal file system using the KAS container environment

### Flashing Image 

*Note: The following steps need to be performed on physical hardware; currently for reference only.*

Write the generated image file to the microSD card:

```bash
cd build/tmp/deploy/images/beaglev-fire/
sudo dd if=core-image-minimal-beaglev-fire.wic of=/dev/sdX bs=4M status=progress conv=fsync
```

### Boot and Log In to System 

 Connect using a serial tool (baud rate 115200) and observe boot logs.

## Expected Results

The flashed SD card should boot the development board into the Linux system.
The system should allow login to the `root` account via serial port without a password.

## Actual Results

CFT

**Boot Phase: Unverified**
- Specific boot logs and runtime screenshots are to be added.

## Test Criteria

Successful: The actual result matches the expected result.

Failed: The actual result does not match the expected result.

## Test Conclusion

CFT
