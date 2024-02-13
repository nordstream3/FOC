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

Which is in fact not an error, but a notice that there is a mismatch between BOM and CPL, since the CPL only contains coordinates of components on the **top side** of the pcb. Importantly, you should click on "Continue".

