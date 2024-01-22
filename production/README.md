# Assembly Guide

The board is produced by the manufacturer as a single pcb. The 3 modules are connected by taps, which you will need to separate using a manual saw. JLCPCB will charge you for the number of designs, but this is a single design assembled to a single unit. The separation is just for convinience purposes and none of the modules will work on their own.

<div>
<img src="../images/20240120_114045.jpg" width="300" style="float:left; margin-right:10px;">
<img src="../images/20240120_114333.jpg"  width="300" style="float:left; margin-right:10px;">
<img src="../images/20240120_115154.jpg" width="300" style="float:left;">
</div>

Use a suitable manual hand saw for separating the 3 modules. Be careful not to damage the traces on the FOCPILL and POWER modules in particular, as the traces here are close to the edges.

When the modules are separated you should straighten the edges with sandpaper or a file.

## How to avoid creating solder bridges and other errors by testing throughout the assembly
Any error that you accidentally introduce to the board is really not a big deal, as long as you catch the error early on. This is why it is very important to verify the hardware after each step in the assembly. Test or you will regret that you didn't!



## Uploading Firmware and testing the FOC/PILL

The FOCPILL can be powered from USB +5V by temporarily bridging the two pads next to the USB-C connector.

<div>
<img src="../images/20240120_115645.jpg" width="300" style="float:left; margin-right:10px;">
<img src="../images/20240120_115723.jpg" width="300" style="float:left; margin-right:10px;">
<img src="../images/20240120_121407.jpg" width="300" style="float:left;">
</div>



<img src="../images/focpill.jpg"  width="400" style="float:left; margin-right:10px;">
<img src="https://github.com/nordstream3/FOC/assets/129880401/765e72d6-6183-4d98-8290-5aad64784e7b)"  width="200" style="float:left; margin-right:10px;">

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

Connect the Power Module to a power supply as shown on the image below. Be VERY careful not to short the connections. Set the power to minimum +16V, and I advise you to **set a current limit of 0.1 Amps**.

<img src="../images/power.jpg"  width="400" style="float:left; margin-right:10px;">

The module is working properly if the LED on the module shows a constant blue light.

## Solder power connector pins

Solder 5 power connector pins onto the Main Module.

[image of soldered power connectors]

You can now temporarily attact the Power Module to the Main Module. You can bend the pins slightly in order to secure a good connection. Do not solder the two modules together yet.

[image of tmp connected modules - with blue light]

If you apply min. +16V to the main connectors on the Main Module, the blue LED on the Power Module should light up. Still **current limit of 0.1 Amps**.

## Connect FOCPILL and Main Module together

If this is your first time assembling a board, I advise you to connect the modules using 2.54mm pitch pin headers.
**current limit of 0.1 Amps**

<img src="../images/foc_assembly.jpg"  width="400" style="float:left; margin-right:10px;">


<img src="../images/20240120_115643.jpg"  width="400" style="float:left; margin-right:10px;">
<img src="../images/20240120_120229.jpg"  width="400" style="float:left; margin-right:10px;">
<img src="../images/20240120_121015.jpg"  width="400" style="float:left; margin-right:10px;">
<img src="../images/20240120_121016.jpg"  width="400" style="float:left; margin-right:10px;">
<img src="../images/20240120_123123.jpg"  width="400" style="float:left; margin-right:10px;">
<img src="../images/20240120_123245.jpg"  width="400" style="float:left; margin-right:10px;">
<img src="../images/20240120_123247.jpg"  width="400" style="float:left; margin-right:10px;">
<img src="../images/20240120_134929.jpg"  width="400" style="float:left; margin-right:10px;">
<img src="../images/20240120_134931.jpg"  width="400" style="float:left; margin-right:10px;">
<img src="../images/20240120_134949.jpg"  width="400" style="float:left; margin-right:10px;">
<img src="../images/20240120_135212.jpg"  width="400" style="float:left; margin-right:10px;">
<img src="../images/20240120_135616.jpg"  width="400" style="float:left; margin-right:10px;">
<img src="../images/20240120_135625.jpg"  width="400" style="float:left; margin-right:10px;">
<img src="../images/20240120_144227.jpg"  width="400" style="float:left; margin-right:10px;">
<img src="../images/20240120_144254.jpg"  width="400" style="float:left; margin-right:10px;">
<img src="../images/20240120_144436.jpg"  width="400" style="float:left; margin-right:10px;">
<img src="../images/20240120_151904.jpg"  width="400" style="float:left; margin-right:10px;">
<img src="../images/20240120_153355.jpg"  width="400" style="float:left; margin-right:10px;">
<img src="../images/20240120_154146.jpg"  width="400" style="float:left; margin-right:10px;">
<img src="../images/20240120_154244.jpg"  width="400" style="float:left; margin-right:10px;">
<img src="../images/20240120_154516.jpg"  width="400" style="float:left; margin-right:10px;">
<img src="../images/20240120_154718.jpg"  width="400" style="float:left; margin-right:10px;">
<img src="../images/20240120_154834.jpg"  width="400" style="float:left; margin-right:10px;">
<img src="../images/20240120_154948.jpg"  width="400" style="float:left; margin-right:10px;">
<img src="../images/20240120_155628.jpg"  width="400" style="float:left; margin-right:10px;">
<img src="../images/20240120_165030.jpg"  width="400" style="float:left; margin-right:10px;">
<img src="../images/Screenshot from 2024-01-20 12-05-25.png"  width="400" style="float:left; margin-right:10px;">
<img src="../images/Screenshot from 2024-01-20 12-05-59.png"  width="400" style="float:left; margin-right:10px;">
<img src="../images/Screenshot from 2024-01-20 12-08-56.png"  width="400" style="float:left; margin-right:10px;">
<img src="../images/Screenshot from 2024-01-20 15-52-31.png"  width="400" style="float:left; margin-right:10px;">
<img src="../images/Screenshot from 2024-01-20 16-48-07.png"  width="400" style="float:left; margin-right:10px;">
<img src="../images/Screenshot from 2024-01-20 16-49-27.png"  width="400" style="float:left; margin-right:10px;">
<img src="../images/Screenshot from 2024-01-20 16-51-23.png"  width="400" style="float:left; margin-right:10px;">
<img src="../images/Screenshot from 2024-01-20 16-52-16.png"  width="400" style="float:left; margin-right:10px;">
<img src="../images/Screenshot from 2024-01-20 16-52-59.png"  width="400" style="float:left; margin-right:10px;">
<img src="../images/Screenshot from 2024-01-20 16-53-25.png"  width="400" style="float:left; margin-right:10px;">





















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
