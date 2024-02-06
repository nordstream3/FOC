# Assembly Guide

<img src="https://github.com/nordstream3/FOC/assets/129880401/9e6a898e-c8aa-4e33-9f68-3b07cfdb93b5" width="400" style="float:left; margin-right:10px;">

Wauw, it looks cool, but unfortunately something has gone wrong in this assembly.


What we want to build here will look like this:

<img src="https://github.com/nordstream3/FOC/assets/129880401/da2cea22-1f1f-4b8b-ab5b-a13add054a24" width="400" style="float:left; margin-right:10px;">

> The 3d printed enclosure you can find in the /production folder as obj files. You don't necessarily need an enclosure, but it will protect the components from short circuits etc.

For a complete assembly of Free Drive you will need:

<img src="https://github.com/nordstream3/FOC/assets/129880401/f58cc206-b7ed-49ce-b436-6f655d200584" width="600" style="float:left; margin-right:10px;">

Pcs | Part | LCSC order no.
| ----- | ----- | ----- |
1 | Pre-assembled pcb
46 | Standard pin header pins | C7494870
6 or 12 | Mosfets of type CRST030N10N | C841369
6 | 330uF Aluminum Electrolytic Capacitors D10xL25mm | C443085
3 | Female banana bullet connectors | C99865
1 | XT90H-M Male battery connector | C3040683
1 | JST	1x7P XH 2.5mm | C144398
1 | JST	1x4P XH 2.5mm | C144395
1 | JST	1x3P XH 2.5mm | C158003
1 | JST	1x2P XH 2.5mm | C158012
1 | JST 1x6P 6 pin JST (p=200) | C7465571
6 or 12 | Mica Insulation Sheet | Aliexpress
6 or 12 | White Insulation Washer TO-220 | Aliexpress
6 or 12 | M3 Stainless Steel Allen Bolts and Screws | Aliexpress
x | Cables
x | Aluminum for sinking heat
x | 3D printed enclosure (production folder)

> The board is produced by the manufacturer as a single pcb. JLCPCB will charge you for the number of designs on a pcb, but this is a single design where the modules are going to be assembled to a single unit. The separation is just for convenience purposes and none of the modules will work on their own.

The 3 modules are connected by taps, and you separate these using a suitable manual saw. Be careful not to damage the traces on the FREE/PILL and POWER modules in particular, as the traces here are close to the edges.

<div>
<img src="../images/20240120_114045.jpg" width="300" style="float:left; margin-right:10px;">
<img src="../images/20240120_114333.jpg"  width="300" style="float:left; margin-right:10px;">
<img src="../images/20240120_115154.jpg" width="300" style="float:left;">
</div>

You should straighten the edges of the separated modules with sandpaper or a file.

## How to avoid creating solder bridges and other errors by testing throughout the Assembly Procedure
> Any error that you accidentally introduce to the board is really not a big deal, as long as you catch the error early on. This is why it is very important to verify the hardware after each step in the assembly.

Test or you will regret that you didn't!
| -------- |


## Step 1: Uploading Firmware and testing FREE/PILL

FREEPILL can be powered from USB +5V by temporarily bridging the two pads next to the USB-C connector.

<div>
<img src="../images/20240120_115645.jpg" width="300" style="float:left; margin-right:10px;">
<img src="../images/20240120_115723.jpg" width="300" style="float:left; margin-right:10px;">
<img src="../images/20240120_121407.jpg" width="300" style="float:left;">
</div>

Now, Connect the FreePill via a USB-C cable to your computer.
In this example I use a STM32F4 Discovery board for uploading firmware, but there are other options available:

[Existing VESC hardware](https://www.youtube.com/watch?v=PFFiVxFHDM4&t=312s)

[stm32f4 Discovery](https://geekilyinteresting.wordpress.com/2014/05/04/using-your-stm32f4-discovery-board-as-a-programmer-and-debugger/)

[ST-LINK windows](https://www.youtube.com/watch?v=etglJKNJSCY)

[stlink-gui on Ubuntu Linux](https://www.youtube.com/watch?v=VhLIKFwoGjo)

<div>
<img src="../images/20240120_120229.jpg" width="400" style="float:left; margin-right:10px;">
<img src="../images/swd.png" width="400" style="float:left;">
</div>

> There is no specific need for soldering pin-headers to the SWD terminals. Usually you only need a connection for a few seconds, and just applying a bit of tension to the terminals during the upload is enough. The pill is going to be soldered to the bottom side of the main module, and permanent pin-headers are not convenient on this side of the board.
>> The square pad on the pill SWD header is VCC (+3.3V).
>> 
>> In this example I use "stlink-gui" on Linux for uploading firmware. If you're on Widows or Mac use one of the other options.

Flash the bootloader to address 0x08000000. Bootloader can be found in the "binaries" folder.

<img src="../images/Screenshot from 2024-01-20 12-05-59.png"  width="600" style="float:left; margin-right:10px;">

Next, flash the Vesc firmware, also to address 0x08000000. Can also be found in the "binaries" folder.

<img src="../images/Screenshot from 2024-01-20 12-08-56.png"  width="600" style="float:left; margin-right:10px;">

Once you have flashed the firmware and the FreePill is booted, the LEDs on the board will show a constant green light and a blinking red light. You should be able to discover the board in the Vesc Tool under the name "FREE_DRIVE".

<div>
<img src="../images/20240120_121016.jpg" width="450" style="float:left;">
<img src="../images/Screenshot from 2024-01-20 15-52-31.png" width="300" style="float:left;">
</div>


**REMEMBER** to remove the solder bridge again. The assembled FreeDrive will **NOT** work properly if powered by USB.
| ------- |
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

## Step 3: Solder FreePill and Main Module together

Some JST connectors will overlap with the Pill at the terminals marked with red:

<div>
<img src="https://github.com/nordstream3/FOC/assets/129880401/99fdda21-d9fe-4e09-8cc0-22bf581b20a4" width="400" style="float:left; margin-right:10px;">
</div>

This is a challenge, because we are going to solder the FreePill and Main Module together using standard pin headers. Because terminals are shared with JST connectors, we remove the pins of the JST sockets where there is overlap, and then the pin-header pins with replace these.

To end up with a proper JST-pin length, we need to pull out the pin-header pins around 1.5 mm at these spots.

<div>
<img src="https://github.com/nordstream3/FOC/assets/129880401/a095acde-4886-4657-abde-4e53204bb996" width="400" style="float:left;">
<img src="https://github.com/nordstream3/FOC/assets/129880401/a5687b8f-4f25-495b-a070-af99cf916f18" width="400" style="float:left; margin-right:10px;">
<img src="https://github.com/nordstream3/FOC/assets/129880401/af5f007d-3e23-405a-9804-2ed85d561858" width="400" style="float:left;">
<img src="https://github.com/nordstream3/FOC/assets/129880401/69c51785-c3c9-4fee-a5ae-2bdf6b18780a" width="400" style="float:left; margin-right:10px;">
</div>

Follow this procedure in this order:

1. With a set of pliers, on the standard pin headers, pull out the "shared" pins around 1.5 mm with reference to the black plastic spacer.
2. Solder pin headers to the FreePill.
3. Mount the FreePill on the back side of the 'Main Module'.
4. On the front side of the Main Module, solder the FreePill pins to the Main Module. Where you see cutouts for JST connectors, be VERY careful to apply only the slightest amount of solder, or else you will be in trouble when mounting the "plastic only" part of these JSTs later. The GND and +3V terminals will need a lot of heat. If too much solder is applied, you can scrape it off gently using a hobby knife.
5. Pull out JST pins of the JST sockets in those locations where they overlap with the pin-headers that you've already soldered.
6. Carefully, mount these sockets in their respective places on top of the respective pins (pin headers).

<img src="https://github.com/nordstream3/FOC/assets/129880401/1b25a1ec-3314-4709-92e2-f6bb2645d137" width="600" style="float:left;">

## Step 4: Solder power connector pins

Solder 5 power connector pins onto the Main Module.

<div>
<img src="https://github.com/nordstream3/FOC/assets/129880401/bc49a59b-0ad5-479a-9270-0a4a1bb37860"  width="350" style="float:left; margin-right:10px;">
<img src="https://github.com/nordstream3/FOC/assets/129880401/5d9624e4-19ce-48cc-8c8d-76164a3cf3bd"  width="350" style="float:left;">
</div>

You can now temporarily attact the Power Module to the Main Module. You can bend the pins slightly in order to secure a good connection. Do not solder the two modules together yet (until you have attached heat sinks to mosfets). You should be able to power the complete board by applying +16V across the main supply terminals. **Use a current limit of 0.1A**.

<div>
<img src="../images/20240120_144254.jpg"  width="315" style="float:left; margin-right:10px;">
<img src="../images/20240120_144436.jpg"  width="245" style="float:left;">
</div>

At this stage, the board should draw around 0.05A at 16V.

## Step 5: Apply solder to exposed copper planes

Apply around 0.3-0.5 mm of solder to the large exposed copper planes of both sides of the Main Module (however, not anything yet to the "phase" planes in between the mosfets).

You can adjust the "height" of the temperature sensor pad by applying a thin layer of solder to it. This is to encure that there is physical contact with the mosfet for temperature reading.

<div>
<img src="../images/20240120_153355.jpg"  width="300" style="float:left; margin-right:10px;">
<img src="../images/20240120_151904.jpg"  width="235" style="float:left;">
</div>

> Putting a layer of solder on the planes is done for thermal management reasons rather than for enhancing electrical conductivity.
> Solder has better thermal conductivity than the bare copper, so adding a thin layer of solder can enhance the thermal performance further. This can help in better heat dissipation from the switching mosfets, which generate significant heat during operation.


## Step 6: Solder first 6 mosfets

<img src="https://github.com/nordstream3/FOC/assets/129880401/9fe8507a-689a-4e36-8991-787deb67086a" width="400" style="float:left; margin-right:10px;">

Bending the caps at the right spot is an advantage, if you want to use the screw holes for mounting the heat sink.

> The screw holes for attachment of heat sink doesn't need to align up perfectly, but should not be too much off.

<img src="../images/20240120_154244.jpg"  width="400" style="float:left; margin-right:10px;">

> You choose if you want to attach the remaining 6 mosfets. This obviously depends on the wattage spec you want of the board.

Power up the complete board by applying +16V across the main supply terminals. **Use a current limit of 0.1A**.

<img src="../images/20240120_154948.jpg"  width="400" style="float:left; margin-right:10px;">

The board should obviously draw less than 0.1A - probably around 0.05A.

## Step 7: Solder the wires for main supply positive and negative. Also solder wires for all three phases

<img src="https://github.com/nordstream3/FOC/assets/129880401/127139e2-60cc-441b-a3e4-03f4d176d097"  width="400" style="float:left; margin-right:10px;">

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

For better thermal management, apply a layer of solder to the top-side exposed copper planes.

<img src="https://github.com/nordstream3/FOC/assets/129880401/1373153e-eb97-4cde-87a0-2f29e74d1ab2" width="400" style="float:left; margin-right:10px;">

> Don't use the amount of solder applied in this image as a reference. This is too much solder!


When mounting and soldering the 330uF capacitors, remember that the three small pads are positive V_in, and the large exposed copper plane is negative (GND).

<img src="https://github.com/nordstream3/FOC/assets/129880401/35347a95-2e42-433b-b364-f8e1caa4d5fa" width="400" style="float:left; margin-right:10px;">
