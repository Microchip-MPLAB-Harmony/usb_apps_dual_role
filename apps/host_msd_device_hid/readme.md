---
parent: Harmony 3 USB Dual Role application examples
title: MSD Host and HID Device Example 
has_children: false
has_toc: false
---

[![MCHP](https://www.microchip.com/ResourcePackages/Microchip/assets/dist/images/logo.png)](https://www.microchip.com)

# MSD Host and HID Device Example (host_msd_device_hid)

This application demonstrates the ability of the MPLAB Harmony USB Stack to support USB dual role operation - USB Device and Host.

## Description

This application creates a USB Dual Role application that can switch between USB Host MSD Stack and USB Device HID function. The role switch is trigger by a switch press. In the USB Host mode, the application performs read and write operations to a USB pen drive. In the USB Device mode, the application emulates a HID mouse.

## Downloading and building the application

To clone or download this application from Github, go to the [main page of this repository](https://github.com/Microchip-MPLAB-Harmony/usb_apps_dual_role) and then click **Clone** button to clone this repository or download as zip file.
This content can also be downloaded using content manager by following these [instructions](https://github.com/Microchip-MPLAB-Harmony/contentmanager/wiki).

Path of the application within the repository is [usb_apps_dual_role/apps/host_msd_device_hid](https://github.com/Microchip-MPLAB-Harmony/usb_apps_dual_role/apps/host_msd_device_hid).

Following table gives the details of project configurations, target device used, hardware and its IDE. Open the project using the respective IDE and build it. 

| Project Name                    | IDE    | Target Device       | Hardware / Configuration                                                   |
| ------------------------------- | ------ | ------------------- | -------------------------------------------------------------------------- |
| pic32mz_ef_sk.X                 | MPLABX | PIC32MZ2048EFH144   | [PIC32MZ Embedded Connectivity with FPU (EF) Starter Kit](#config_16)      |

## <a name="config_title"></a> Configuring the Hardware

### <a name="config_16"></a> [PIC32MZ Embedded Connectivity with FPU (EF) Starter Kit](https://www.microchip.com/Developmenttools/ProductDetails/DM320007)

- Initially application will not operate in any role. Press the corresponding switch to change the operating role.
    - Press SW2 to change to USB Device mode.
    - Press SW3 to change to USB Host mode
- Device mode operation
    - Connect the device to the Type A connector J4, which is located on the bottom side of the starter kit.
    - The application will emulate a USB HID mouse function. The cursor on the PC will rotate. Pressing SW1 will enable and disable the cursor movements.
- Host mode Operation
    - Connect the device to the Type A connector J5, which is located on the top side of the starter kit.
    - LED2 indicates the file write is complete..

## Running the Application

This application demonstrates the Dual Role capability of the MPLAB Harmony USB Stack. The application project includes both, the USB Host and Device Stacks. Both the stacks are initialized during application initialization. During operation, the application polls a switch on the starter kit to trigger a USB role switch. Note that the application cannot simultaneously operate as a host and device. The one USB role is exclusive of the other. 

Prior to using this demonstration, it is recommended to review the MPLAB Harmony USB Release Notes for any known issues. 

1. Open the project and in MPLAB X IDE.
2. Build the code and program the device. The application initially will not operate in any USB role.
3. Press SW2 on the starter kit. This places the application in a USB Device mode.
4. Connect a USB cable between micro USB connector (J4) on the starter kit and a PC USB host. The application will emulate a USB HID mouse function. The cursor on the PC will rotate. Pressing SW1 will enable and disable the cursor movements. Exercise device plug-n-play operation to confirm USB Device operation
5. Now try switching the USB role to Host mode. Disconnect the USB cable between micro USB connector (J4) on the starter kit and a PC USB host. Press SW3 on the starter kit.
6. The application now will be in USB Host role. Connect a USB pen drive to the Type-A USB Host connector (J5) on the starter kit. The application will create a file (file.txt) on the pen drive. The completion of the operation is indicated by LED2 on the starter kit. Disconnect the pen driver and connect it to a PC to verify the contents of the file.
7. Repeat steps 3 through 6 to exercise the role switching capability.