# Assembly Guide

When the board arrive from the pcb manufacturer it will look like this:

[image]

Use a suitable manual hand saw for separating the 3 modules. Be careful not to damage the traces on the FOCPILL and POWER module in particular, as the traces here are close to the edges.

When the modules are separated you can straighten the edges with sandpaper or a file.

[image of saparated modules]

## Verify the FOCPILL hardware

The FOCPILL can be powered from USB +5V by bridging the two pads next to the USB-C connector.

[image of bridged pads]

Connect the FOCPILL via a USB-C cable to your computer. No LEDs on the board will light up before you have uploaded the VESC Firmware.

Upload Boot Loader and FOCKING VESC6 firmware binaries using e.g. STLINK, stm32f4 Discovery Board or an existing VESC as a programmer. Here are guides on how to do this:

[Existing VESC hardware](https://www.youtube.com/watch?v=PFFiVxFHDM4&t=312s)

[stm32f4 Discovery](https://geekilyinteresting.wordpress.com/2014/05/04/using-your-stm32f4-discovery-board-as-a-programmer-and-debugger/)

[ST-LINK windows](https://www.youtube.com/watch?v=etglJKNJSCY)

[stlink-gui on Ubuntu Linux](https://www.youtube.com/watch?v=VhLIKFwoGjo)

Bootloader and FOCKING binaries are located in the "binaries" folder.

Once you have uploaded the firmware and the FOCPILL is booted, the LEDs on the board will show a constant green light and a blinking red light, and you have now successfully veryfied that the FOCPILL is working as is should - so far.

**REMEMBER** to remove the solder bridge between the pads again, as the assembled FOCKING will **NOT** work properly if powered by USB.

## Verify the POWER hardware

Connect the Power Module to a power supply as shown on the image below. Be VERY careful not to short the connections. Set the power to minimum +16V, and I advise you to set a current limit of 0.1 Amps.

[Image of powered Power Module]

The module is working properly if the LED on the module shows a constant blue light.

## Solder power connector pins

Solder 5 power connector pins onto the Main Module.

[image of soldered power connectors]

You can now temporarily attact the Power Module to the Main Module. You can bend the pins slightly in order to secure a good connection. Do not solder the two modules together yet.

[image of tmp connected modules - with blue light]

If you apply min. +16V to the main connectors on the Main Module, the blue LED on the Power Module should light up. Still current limit of 0.1 Amps.

## Connect FOCPILL and Main Module together

If this is your first time assembling a board, I advise you to connect the modules using 2.54mm pitch pin headers.



# Markdown syntax guide

## Headers

# This is a Heading h1
## This is a Heading h2
###### This is a Heading h6

## Emphasis

*This text will be italic*  
_This will also be italic_

**This text will be bold**  
__This will also be bold__

_You **can** combine them_

## Lists

### Unordered

* Item 1
* Item 2
* Item 2a
* Item 2b

### Ordered

1. Item 1
2. Item 2
3. Item 3
    1. Item 3a
    2. Item 3b

## Images

![This is an alt text.](/image/sample.webp "This is a sample image.")

## Links

You may be using [Markdown Live Preview](https://markdownlivepreview.com/).

## Blockquotes

> Markdown is a lightweight markup language with plain-text-formatting syntax, created in 2004 by John Gruber with Aaron Swartz.
>
>> Markdown is often used to format readme files, for writing messages in online discussion forums, and to create rich text using a plain text editor.

## Tables

| Left columns  | Right columns |
| ------------- |:-------------:|
| left foo      | right foo     |
| left bar      | right bar     |
| left baz      | right baz     |

## Blocks of code

```
let message = 'Hello world';
alert(message);
```

## Inline code

This web site is using `markedjs/marked`.
