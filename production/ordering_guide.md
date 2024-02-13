# Ordering Guide

Follow [this](./gerber.zip) link to download the gerber zip file located in the /production folder.

Follow [this](https://cart.jlcpcb.com/quote) link to go to the upload of Gerber Files at jlcpcb.

When the gerbers are uploaded, you should see this:

![image](https://github.com/nordstream3/FOC/assets/129880401/9111ae31-2044-4c74-a86f-a5aa5678b7de)

Choose the decired **pcb quantity**. Minimum quantity is 5.

Leave all the other choices at their default, and scroll to the bottom of the page:
![image](https://github.com/nordstream3/FOC/assets/129880401/dfb52719-19e5-4a74-8983-317298adc47c)

Select "Free Assembly for your PCB order".

![image](https://github.com/nordstream3/FOC/assets/129880401/1b312794-cd56-4b14-b092-cc3bc9a1fe4a)

Again, you need to specify the how many of you ordered pcbs you would like to be pre-assembled with components.

Leave the remaining choices at their defaults and scroll to the bottom of the page and click "Confirm".

## Process BOM & CPL

After your confirmation, you will be presented with a kind of Wizard, with the first page showing a top view of the pcb.

Click "Next" to go to the relevant page for upload of BOM and CPL files.

![image](https://github.com/nordstream3/FOC/assets/129880401/09f819ce-4bdc-4bc4-87c6-56ad387d1e9e)

Follow [this](./bom.csv) link to download the BOM located in the /production folder.  
Follow [this](./foc_cpl_top.csv) link to download the CPL located in the /production folder.

When you have successfully uploaded the BOM and CPL click on "Process BOM & CPL", whereafter you will be presented with an "ERROR".

![image](https://github.com/nordstream3/FOC/assets/129880401/266d4226-bf7f-43dd-bc55-7330815aef22)

Which is in fact not an error, but a notice that there is a mismatch between BOM and CPL, since the CPL only contains coordinates of components on the **top side** of the pcb. 

Importantly, you should click on "Continue", and you will presented with a **long** list of all the components matched in the BOM & CPL.

Scroll down the list to find if there are any components that fall short:

![image](https://github.com/nordstream3/FOC/assets/129880401/0c6b2d77-0f82-404a-b278-cccca2f03bd2)

At the time of writing, jlcpcb falls short of almost anything that smells like a diode in their **Basic Library**.  
If you can live with blue or yellow LEDS, these colors are available in **basic library** versions. For the 2 Zener Diodes, you will need to find replacements for these in the **Extended Library**.

> FreeDRIVE is optimized for lowest jlcpcb price. Where possible, **basic library** is always first choice.  
> Basic Library: These are the components pre-loaded in the SMD Automatic Pick and Place Machine.  
> Extended Library: These are the components requiring manual setup, and you will be charged an extra fee per component type.

After you have found replacements for any shortfall components, you should scroll to find the "Connector_PinHeader_2.54mm footprints:
![image](https://github.com/nordstream3/FOC/assets/129880401/5552c263-93cb-4ac6-b863-2c156b197f62)

Importantly, you must **deselect** these two connector types.

Also, **deselect** the large 330uF Capacitors. We want to solder these manually.
![image](https://github.com/nordstream3/FOC/assets/129880401/14ed772c-012e-47b4-9475-35be82235ff5)

When all is done, choose "Next", and you will be presented with a dialog:

![image](https://github.com/nordstream3/FOC/assets/129880401/ab6f0623-c9d0-4346-9c47-24c949097522)

Select "Do not place".

<img src="https://github.com/nordstream3/FOC/assets/129880401/eb4aa5be-d4a4-423b-8feb-e367a095fffe" width="200" style="float:left;">


Image | Components | To Do
|----|----|----|
<img src="https://github.com/nordstream3/FOC/assets/129880401/9c5dd429-dd3d-4481-bf42-7a76c873ea35" width="500" style="float:left;"> | 3 Gate Drivers | Rotate all three 180 deg. so white and cyan dots lign up
<img src="https://github.com/nordstream3/FOC/assets/129880401/906306c6-3d80-473e-b5e0-4fa147e8fdaf" width="150" style="float:left;"> | CYA0650-68UH2 | Nothing. Image missing, but OK
<img src="https://github.com/nordstream3/FOC/assets/129880401/d5e896df-a020-4ab3-a556-019d4dd7ea88" width="150" style="float:left;"> | CAN Driver | Rotate 180 deg.
<img src="https://github.com/nordstream3/FOC/assets/129880401/7c25abb4-0ae6-4803-8c9b-492c2c4c33d7" width="400" style="float:left;"> | 3 Op Amps | Rotate all three 180 deg. so legs match pads
<img src="https://github.com/nordstream3/FOC/assets/129880401/b6f96403-d176-4810-99dc-00fd9c5190ee" width="200" style="float:left;"> | IMU | Rotate 90 deg. right




![image](https://github.com/nordstream3/FOC/assets/129880401/b0895cf7-5900-4ef2-83c9-59fa5d4e2a93)
![image](https://github.com/nordstream3/FOC/assets/129880401/aedc2241-3bd2-4054-baec-9be55176529a)

