![](./resources/official_armmbed_example_badge.png)
# System Information Mbed OS Example

This guide reviews the steps required to get system information on Mbed OS platform. It contains an application that can be run on all supported [Mbed boards](https://os.mbed.com/platforms/).

The project can be built with all supported [Mbed OS build tools](https://os.mbed.com/docs/mbed-os/latest/tools/index.html). However, this example project specifically refers to the command line interface tool [Arm Mbed CLI](https://github.com/ARMmbed/mbed-cli#installing-mbed-cli).
(Note: To see a rendered example you can import into the Arm Online Compiler, please see our [import quick start](https://os.mbed.com/docs/mbed-os/latest/quick-start/online-with-the-online-compiler.html#importing-the-code).)

Please install Arm Mbed CLI.

Clone this repository on your system and change the current directory to where the project was cloned.

## Application functionality

The `main()` function outputs on the serial interface information about the hardware (CPU, ROM and RAM), the firmware (Version), as well as the compiler used to build the binary.

## Building and Running

1. Connect a USB cable between the USB port on the target and the host computer.
2. Run the following command to build the example project and program the microcontroller flash memory:
```bash
$ mbed compile -m <TARGET> -t <TOOLCHAIN> --flash
```
Your PC may take a few minutes to compile your code.

The binary is located at `./BUILD/<TARGET>/<TOOLCHAIN>/mbed-os-example-sys-info.bin` and can alternatively be manually copied to the target which gets mounted on the host computer via USB.

Depending on the target, the example project can be built with GCC_ARM, ARM or IAR toolchain. Run the command below after installing ARM Mbed CLI to determine which toolchain supports your target.

```bash
$ mbed compile -S
```

## Expected output 
The LED blinks and the serial terminal shows an output similar to the following: 
``` 
--- Terminal on /dev/ttyACM0 - 9600,8,N,1 --- 
Mbed OS Version: 999999  
CPU ID: 0x410fc241  
Compiler ID: 1  
Compiler Version: 6130008  
RAM0: Start 0x20000000 Size: 0x30000  
RAM1: Start 0x1fff0000 Size: 0x10000  
ROM0: Start 0x0 Size: 0x100000 
``` 

## Troubleshooting 
If you have problems, you can review the [documentation](https://os.mbed.com/docs/latest/tutorials/debugging.html) for suggestions on what could be wrong and how to fix it. 

## Related Links 

* [Mbed OS Stats API](https://os.mbed.com/docs/latest/apis/mbed-statistics.html). 
* [Mbed OS Configuration](https://os.mbed.com/docs/latest/reference/configuration.html). 
* [Mbed OS Serial Communication](https://os.mbed.com/docs/latest/tutorials/serial-communication.html). 
* [Mbed boards](https://os.mbed.com/platforms/).

### License and contributions
The software is provided under Apache-2.0 license. Contributions to this project are accepted under the same license. Please see contributing.md for more info.

This project contains code from other projects. The original license text is included in those source files. They must comply with our license guide.
