# Assembly Guide

The board is produced by the manufacturer as a single pcb. The 3 modules are connected by taps, and you will need to separate the modules using a manual saw. JLCPCB will charge you for the number of designs on a pcb, but this is a single design where the modules are going to be assembled to a single unit. The separation is just for convenience purposes and none of the modules will work on their own.

<div>
<img src="../images/20240120_114045.jpg" width="300" style="float:left; margin-right:10px;">
<img src="../images/20240120_114333.jpg"  width="300" style="float:left; margin-right:10px;">
<img src="../images/20240120_115154.jpg" width="300" style="float:left;">
</div>

Use a suitable manual hand saw for separating the 3 modules. Be careful not to damage the traces on the FREE/PILL and POWER modules in particular, as the traces here are close to the edges.

When the modules are separated you should straighten the edges with sandpaper or a file.

## How to avoid creating solder bridges and other errors by testing throughout the Assembly Procedure
Any error that you accidentally introduce to the board is really not a big deal, as long as you catch the error early on. This is why it is very important to verify the hardware after each step in the assembly.

Test or you will regret that you didn't!
| -------- |


## Step 1: Uploading Firmware and testing FREE/PILL

FREEPILL can be powered from USB +5V by temporarily bridging the two pads next to the USB-C connector.

<div>
<img src="../images/20240120_115645.jpg" width="300" style="float:left; margin-right:10px;">
<img src="../images/20240120_115723.jpg" width="300" style="float:left; margin-right:10px;">
<img src="../images/20240120_121407.jpg" width="300" style="float:left;">
</div>

Now, Connect the FreePill via a USB-C cable to your computer. In this example I use a STM32F4 Discovery board for uploading firmware, but there are other options available:

[Existing VESC hardware](https://www.youtube.com/watch?v=PFFiVxFHDM4&t=312s)

[stm32f4 Discovery](https://geekilyinteresting.wordpress.com/2014/05/04/using-your-stm32f4-discovery-board-as-a-programmer-and-debugger/)

[ST-LINK windows](https://www.youtube.com/watch?v=etglJKNJSCY)

[stlink-gui on Ubuntu Linux](https://www.youtube.com/watch?v=VhLIKFwoGjo)

<div>
<img src="../images/20240120_120229.jpg" width="400" style="float:left; margin-right:10px;">
<img src="../images/swd.png" width="400" style="float:left;">
</div>

There is no specific need for soldering pin-headers to the SWD terminals. Usually you only need a connection for a few seconds, and just applying a bit of tension to the terminals during the upload is enough. The pill is going to be soldered to the bottom side of the main module, and permanent pin-headers are not convenient on this side of the board.

Info: The square pad on the pill SWD header is VCC (+3.3V).

In this example I use "stlink-gui" on Linux for uploading firmware. If you're on Widows or Mac use one of the other options.

Flash the bootloader to address 0x08000000. Bootloader can be found in the "binaries" folder.

<img src="../images/Screenshot from 2024-01-20 12-05-59.png"  width="600" style="float:left; margin-right:10px;">

Next, flash the Vesc firmware, also to address 0x08000000. Can also be found in the "binaries" folder.

<img src="../images/Screenshot from 2024-01-20 12-08-56.png"  width="600" style="float:left; margin-right:10px;">

Once you have flashed the firmware and the FreePill is booted, the LEDs on the board will show a constant green light and a blinking red light. You should be able to discover the board in the Vesc Tool under the name "FREE_DRIVE".

<div>
<img src="../images/20240120_121016.jpg" width="450" style="float:left;">
<img src="../images/Screenshot from 2024-01-20 15-52-31.png" width="300" style="float:left;">
</div>


**REMEMBER** to remove the solder bridge between the pads again, as the assembled FreeDrive will **NOT** work properly if powered by USB.

<div>
<img src="../images/pow_pads.png" width="200" style="float:left;">
</div>


## Step 2: Verify the POWER hardware

Connect the Power Module to a power supply as shown on the image below. Be VERY careful not to short the connections. Set the voltage to +16V with a **current limit of 0.1 Amps**.

<div>
<img src="../images/power.jpg"  width="400" style="float:left; margin-right:10px;">
<img src="../images/20240120_155628.jpg"  width="100" style="float:left;">
</div>

The module is working properly when the LED on the module shows a constant blue light.

## Step 3: Align and fix FreePil and Main Module together

If you want in any way to be able to desolder the FreePill from the Main Module at some point in the future, you should use pin-headers for all terminals. In general, pin-headers are the only way to avoid that things get messy.

Those terminals that are difficult to heat to sufficient temperatures, and that you would therefore want to pay special attention to are:

GND | +3V
| ------------- | ------------- |

If we look at the pcb you will notice that some of the JST connectors are in fact located directly on top of pins that go through BOTH sandwiched boards. You might ask, how am I going to mount a JST connector socket on top of a pin header? Well, you can't, and that is why we will have to do a trick here, which is to pull out the pins of these particular JST connector sockets and then mount the remaining "plastic" socket on top of the pins of pin headers. It will work, but more about this later.

<img src="../images/gnd.png" width="600" style="float:left;">

Start by following this procedure:

1. Start by aligning the modules so the FreePill is located on the back-side of the MAIN module. Place the first JST in its right positions on the front side of the main module, and solder the connector pins on the back side. Be careful not to use more than just enough solder for these pins. We don't want solder in between the pcbs.
2. Turn the board around and temporarily remove the plastic socket of the JST, using e.g. a hobby knife or pliers.
3. While making sure that the modules are perfectly aligned, solder the pins on this side also.
4. Do the same thing for the remaining JSTs.
5. Position pin-headers in the remaining terminals, solder these, remove plastic spacers, and solder the other side as well. Be careful not to use too much solder, as this will make it difficult to de-solder the pill.
6. Carefully, you can re-attach the JST plastic sockets on their corresponding pins, and shorten the length of the (non JST) pins.

<div>
<img src="../images/20240120_123247.jpg"  width="300" style="float:left; margin-right:10px;">
<img src="../images/20240120_134931.jpg"  width="300" style="float:left; margin-right:10px;">
<img src="../images/20240120_135212.jpg"  width="165" style="float:left;">
</div>

## Step 4: Solder power connector pins

Solder 5 power connector pins onto the Main Module.

[image of soldered power connectors]

You can now temporarily attact the Power Module to the Main Module. You can bend the pins slightly in order to secure a good connection. Do not solder the two modules together yet. You should be able to power the complete board by applying +16V across the main supply terminals. **Use a current limit of 0.1A**.

<div>
<img src="../images/20240120_135625.jpg"  width="350" style="float:left; margin-right:10px;">
<img src="../images/20240120_144254.jpg"  width="315" style="float:left; margin-right:10px;">
<img src="../images/20240120_144436.jpg"  width="245" style="float:left;">
</div>

At this stage, the board should draw around 0.05A at 16V.

## Step 5: Apply solder to exposed copper planes

Apply around 0.3-0.5 of solder to the large exposed copper planes of both sides of the Main Module (however, not anything yet to the "phase" planes in between the mosfets). Also apply around the same amount to the small temperature sensor plane on the bottom of the Main Module. This, because there will be around 0.5mm of gap between mosfets and pcb.

<div>
<img src="../images/20240120_153355.jpg"  width="300" style="float:left; margin-right:10px;">
<img src="../images/20240120_151904.jpg"  width="235" style="float:left;">
</div>

## Step 6: Solder first 6 mosfets

Bend the legs of these 6 mosfets in such a way that there is a spacing of around 0.5mm between mosfets and pcb. In other words, we want the screw-holes for attaching mosfets to the aluminum heat sink to be not too much off. Also, the USB connector should not be in the way of an aluminum heat-sink.

[image of mosfet-2-pcb gap]

<img src="../images/20240120_154244.jpg"  width="400" style="float:left; margin-right:10px;">

You choose if you want to attach the remaining 6 mosfets. This obviously depends on the wattage spec you want of the board.

Power up the complete board by applying +16V across the main supply terminals. **Use a current limit of 0.1A**.

<img src="../images/20240120_154948.jpg"  width="400" style="float:left; margin-right:10px;">

The board should obviously draw less than 0.1A - probably around 0.05A.

## Step 7: Solder the wires for main supply positive and negative. Also solder wires for all three phases

[Image]

Attach a bldc motor to the three phase wires.

Again, apply the same test as in "Step 6"

## Step 8: Test run the motor

If you were successful so far, increase the voltage to +24V and **set a current limit of 0.3A**.
Connect to "FREE_DRIVE" in the Vesc Tool and go to the "Vesc Dev Tools" menu and type the command "help". This should give you a long list of available developer command line options.

<img src="../images/Screenshot from 2024-01-20 16-49-27.png"  width="700" style="float:left; margin-right:10px;">

Scroll up til you find the "single_bridge_duty" command (a very helpful command currently only available for the FreeDrive firmware).
Write the command:

```
single_bridge_duty 0 0.04 10
```

(which is equivalent to: Apply 4% duty cycle to phase no. 0 for 10 seconds)

If you try to turn the motor by hand now, you should feel some mechanical resistance. Note down the draw of current during this 10 second period.

If you run the same command for the two other phases, the draw of current should be around the same value. Also the felt mechanical resistance should be comparable. The commands for the two other phases are:

```
single_bridge_duty 1 0.04 10
```
```
single_bridge_duty 2 0.04 10
```

If something looks or feels odd in this procedure, maybe you accidentally bridged traces during soldering of mosfets?

If you open up the "Sampled Data" menu under "Data Analysis" and click on the "Sample Now" button, you should see something like this:

<img src="../images/Screenshot from 2024-01-20 16-51-23.png"  width="600" style="float:left; margin-right:10px;">

All phase currents should be centered around zero.

If you lock a single phase for e.g. 20 seconds and do a current measurement during this period, you should see that the current of phase 1 stands out from phase 2 and 3
```
single_bridge_duty 0 0.04 20
```
<img src="../images/Screenshot from 2024-01-20 16-52-16.png"  width="600" style="float:left; margin-right:10px;">

Phase 2:
```
single_bridge_duty 1 0.04 20
```
<img src="../images/Screenshot from 2024-01-20 16-52-59.png"  width="600" style="float:left; margin-right:10px;">

Phase 3:
```
single_bridge_duty 2 0.04 20
```
<img src="../images/Screenshot from 2024-01-20 16-53-25.png"  width="600" style="float:left; margin-right:10px;">

## Step 9: Finish assembly by adding large capacitors or more fets


<img src="../images/20240120_144227.jpg"  width="400" style="float:left; margin-right:10px;">
<img src="../images/20240120_121015.jpg"  width="400" style="float:left; margin-right:10px;">
<img src="../images/20240120_121016.jpg"  width="400" style="float:left; margin-right:10px;">
<img src="../images/20240120_123123.jpg"  width="400" style="float:left; margin-right:10px;">
<img src="../images/20240120_123245.jpg"  width="400" style="float:left; margin-right:10px;">
<img src="../images/20240120_134929.jpg"  width="400" style="float:left; margin-right:10px;">
<img src="../images/20240120_134949.jpg"  width="400" style="float:left; margin-right:10px;">
<img src="../images/20240120_135616.jpg"  width="400" style="float:left; margin-right:10px;">
<img src="../images/20240120_153355.jpg"  width="400" style="float:left; margin-right:10px;">
<img src="../images/20240120_154146.jpg"  width="400" style="float:left; margin-right:10px;">
<img src="../images/20240120_154244.jpg"  width="400" style="float:left; margin-right:10px;">
<img src="../images/20240120_154516.jpg"  width="400" style="float:left; margin-right:10px;">
<img src="../images/20240120_154718.jpg"  width="400" style="float:left; margin-right:10px;">
<img src="../images/20240120_154834.jpg"  width="400" style="float:left; margin-right:10px;">
<img src="../images/20240120_154948.jpg"  width="400" style="float:left; margin-right:10px;">
<img src="../images/20240120_165030.jpg"  width="400" style="float:left; margin-right:10px;">
<img src="../images/Screenshot from 2024-01-20 16-48-07.png"  width="400" style="float:left; margin-right:10px;">





















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
