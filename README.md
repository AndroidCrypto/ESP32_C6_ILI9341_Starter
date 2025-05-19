# ESP32-C6 Supermini with ILI9341 TFT display Starter
Getting started with an **ESP32-C6 Supermini** device and a TFT display with driver chip **ILI9341**.

This is the accompanying repository for my article "**Getting Started with an ESP32-C6 Supermini device connected to an ILI9341 TFT display**": .

My display is a 2.8 inch large TFT display with 240 x 320 pixels.

## Settings for the display specific setup file

I'm using a display specific setup file for the combination ESP32-C6 Supermini with TFT display driver ILI9341.This file contains e.g. the display driver, size and pins for the ESP32-device. If your display has a different size please change the height and width accordingly. 

### Copy a file to the User_Setups folder

Please copy the file

    Setup704_C6_SM_ILI9341_240x320.h

to the **User_Setups** folder.

### Edit the User_Setup_Select.h file

You need to place the following line in the root folder's "**User_Setup_Select.h**" file

    #include <User_Setups/Setup704_C6_SM_ILI9341_240x320.h> // ESP32-C6 Supermini, 80 MHz

Second: please comment all other "#include..." entries like this, especially the "//#include <User_Setup.h>" entry.

````
// Example User_Setup files are stored in the "User_Setups" folder. These can be used
// unmodified or adapted for a particular hardware configuration.
#ifndef USER_SETUP_LOADED //  Lets PlatformIO users define settings in
                          //  platformio.ini, see notes in "Tools" folder.
///////////////////////////////////////////////////////
//   User configuration selection lines are below    //
///////////////////////////////////////////////////////
// Only ONE line below should be uncommented to define your setup.  Add extra lines and files as needed.
//#include <User_Setup.h>                       // Default setup is root library folder
// Setup file in folder Arduino/libraries (updates will not overwrite your setups)
#include <User_Setups/Setup704_C6_SM_ILI9341_240x320.h> // ESP32-C6 Super Mini, 80 MHz
````

## Display Troubleshooting

I own two similar looking ILI9341 displays, but although both are driven by an ILI9341 chip, they need different setups. For this reason, I included two setup files with this sketch (**"Setup704_C6_SM_ILI9341_240x320.h"** and **"Setup704_C6_SM_ILI9341_2_240x320.h"**). If you encounter the problem, just select the other setup file in the "User_Setup_Select.h" file.

## Important note

You need to modify the display library TFT_eSPI to get the code to work. Please find instructions on how to do this in my forked TFT_eSPI repository here on GitHub: [https://github.com/AndroidCrypto/TFT_eSPI](https://github.com/AndroidCrypto/TFT_eSPI).
