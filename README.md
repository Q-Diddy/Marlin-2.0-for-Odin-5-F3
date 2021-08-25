# Mks-Robin-Nano-Marlin2.0-Firmware for FoKoos Odin 5-F3 3D Printer

**UPDATE UPDATE UPDATE**

All my patches have now been folded back into MARLIN 2.0-Bugfix as of Aug 25th, 2021.  FOKOOS Odin 5-F3 printers are now fully supported using the robin-nano-1.2 profile and a couple changes to the pins.h file.

This repository will remain online as a resource, but if you want to use the MOST up-to-date firmware, you should head on over to:

https://github.com/MarlinFirmware/Marlin/tree/bugfix-2.0.x

I will soon be REMOVING ALL FIRMWARE IMAGES AND SOURCE CODE from this repository ( Sept 1st, 2021 ) and leaving only suggested configuration files, images, and slicer configuration profiles.   

Sincerely,
Martin

## Purpose

This is a fork of the MKS-Robin-Nano-Marlin2.0-Firwmare GitHub with configurations and changes made to specifically support the FOKOOS Odin 5-F3 ( and eventually F4 ) 3D printer. 

![](https://github.com/martinbogo/Marlin-2.0-for-Odin-5-F3/blob/main/Images/odin-5-f3.jpg)

## Features
The printer firmware is based on that of the MKS Robin Nano, which itself is forked from [Marlin2.0.x](https://github.com/MarlinFirmware/Marlin) and adds the [LittlevGL](https://github.com/littlevgl/lvgl) adds a colourful GUI and touch screen suport.  LittlevGL support is being folded back into the main Marlin 2.0 firmware tree and at that point this firmware will be refactored to operate off that branch until everything can be folded back in the main line.

![](https://github.com/makerbase-mks/Mks-Robin-Nano-Marlin2.0-Firmware/blob/master/Images/MKS_Robin_Nano_printing.png)

## Build
As the firmware is based on Marlin2.0.x which is built on the core of PlatformIO, the buid compiling steps are the same as Marlin2.0.x. 

You can build it directly using [PlatformIO Shell Commands](https://docs.platformio.org/en/latest/core/installation.html#piocore-install-shell-commands)

Or you can use IDEs that integrate PlatformIO Core(CLI), for example, [VSCode](https://docs.platformio.org/en/latest/integration/ide/vscode.html#ide-vscode) and [Atom](https://docs.platformio.org/en/latest/integration/ide/atom.html). **VSCode is recommended.**

## About the gcode file preview
MKS has developed a [plugin for Cura](https://github.com/makerbase-mks/mks-wifi-plugin) to add image previews to the g-code files.  It is compatible with Cura 4.4 and higher.

## Image conversion for the "asset" directory
- The Odin 5-F3 uses a 480x320 display for full-screen items such as the boot logo
- Pay attention to the size of icons. You have to create them at the correct size.
- Open [LVGL online image converter tool](https://lvgl.io/tools/imageconverter). 
- Open bmp images.
- Enter the saved file name.
- Choose color format:True color.
- Choose file output format:Binary RGB565.
- Start convertion.
- Save bin file.
- Copy the converted bin file to the assets folder.
- Copy the assets folder to the SD card.
- SD card is connected to the motherboard, and you can see the update interface after powering on.

## Firmware Can be run on Robin Nano V1.x / V2.x boards and V3.x boards

## MKS Robin Nano V1.x build and update firmware

1. Build config:
     
- platformio.ini: 
     
     default_envs = mks_robin_nano35    
- Configuation.h:  
     #define SERIAL_PORT 3  
     #define MKS_ROBIN_TFT35  
     #define MOTHERBOARD BOARD_MKS_ROBIN_NANO  
     #define TFT_LVGL_UI  
     #define TOUCH_SCREEN  

2. Update firmware:
   
- Enter the `.pio\build\mks_robin_nano35` directory, copy the `assets` folder and `Robin_nano35.bin` to the sd card
- Insert SD card to the motherboard, and you can see the update interface after power on.   

## For more information and configuration options, please refer to Robin nano series Wiki
- [MKS Robin Nano V1.x Wiki](https://github.com/makerbase-mks/MKS-Robin-Nano-V1.X/wiki). 
- [MKS Robin Nano V2.x Wiki](https://github.com/makerbase-mks/MKS-Robin-Nano-V2.X/wiki). 
- [MKS Robin Nano V3.x Wiki](https://github.com/makerbase-mks/MKS-Robin-Nano-V3.X/wiki).

## More information about the Robin Nano V1.X
Please refer to [MKS Robin Nano github](https://github.com/makerbase-mks/MKS-Robin-Nano-V1.X).

