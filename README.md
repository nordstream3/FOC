# King of FOC motor control hardware aka FOC_KING

## The DIY Open Source Vesc6 and FOC capable HW with onboard IMU and CAN
<div>
<img src="https://github.com/nordstream3/FOC/assets/129880401/316b892a-555c-4632-94d1-f3a5aa92823f" width="300" style="float:left; margin-right:10px;">
<img src="https://github.com/nordstream3/FOC/assets/129880401/ffd7d584-e124-4ee1-bf63-155ca58bfea3" width="300" style="float:left;">
</div>

[![IMAGE ALT TEXT](https://github.com/nordstream3/FOC/assets/129880401/6b1483e7-21d7-4d83-af18-93e87dd7afbc)](https://www.youtube.com/watch?v=1HfkBNfPIXc "FreeDRIVE")

Date | Manufacturer | amount | includes | shipping & tax | price
| -------- | -------- | -------- | -------- | -------- | -------- |
2024-01-17 | JLCPCB | 10 boards | All assembled excl fets and caps | YES, to EU | $241.08

An open-source motor controller board based on a JLCPCB friendly [VESC6 75V/300A](https://vesc-project.com/sites/default/files/Benjamin%20Posts/vesc_75_300.pdf) so-called "driverless" design with individual gate drivers for all three phases. It is powered by an STM32F405 MCU and is capable of running FOC at high power and voltages.

A motor controller designed for FOC (Field Oriented Control) and HFI (High Frequency Injection), a sensorless teqnique enabling full torque at zero speed without sensor feedback. The hardware is separated in 3 sub-modules which are assembled using standard pin headers.

POWER BRIDGE | MCU | SUPPLY
|----|----|----|
<img src="https://github.com/nordstream3/FOC/assets/129880401/dfa8d088-c647-4df2-9465-01d347643fa1" width="200" style="float:left;"> | <img src="https://github.com/nordstream3/FOC/assets/129880401/23899814-eda4-4109-83fc-18060b6d4e02" width="100" style="float:left;"> | <img src="https://github.com/nordstream3/FOC/assets/129880401/7a79abc4-aa75-44de-9f78-ca9ab5f3dfe6" width="50" style="float:left;">
3 phase power bridge | STM32F405 PILL | +12,+5V,+3V



Intended for "small" electric vehicles like Skateboards, OneWheels, Bicycles, Robotics, Boats, and is designed in sub-modules as a reference design for further development.

The standard design includes 12 mosfets, but it will also work with just 6 fets. You choose.

## Features
* 84V/200A continuous rating
* 20s battery voltage rating
* 3-phase FOC motor control
* 4-layer pcb design with individual gate drivers for all three phases
* STM32F405 MCU
* USB-C
* CAN, 5 mbps
* Onboard IMU (Bosch BMI270)
* Momentary on/off switch connection via 4-pin jst connector
* Led data pin for programmable LEDs
* Compact design with fets mounted on the bottom side
* 12V for gate drivers, 5V for CAN and IMU, and 3.3V for MCU and op-amped current-sense amplification
* Cheap and up-to-date with cheapest and **well stocked** components available for ordering at [JLCPCB](https://jlcpcb.com/) and [LCSC](https://www.lcsc.com)
* **Dimensions of assembled board: 65 x 78 mm**

<div>
<img src="/images/foc_setup.jpg"  width="200" style="float:left; margin-right:10px;">
<img src="/images/focpill.jpg"  width="200" style="float:left; margin-right:10px;">
<img src="/images/power.jpg"  width="200" style="float:left;">
</div>

<div>
<img src="/images/foc_assembly.jpg"  width="200" style="float:left; margin-right:10px;">
<img src="/images/f.png"  width="200" style="float:left; margin-right:10px;">
<img src="/images/b.png"  width="200" style="float:left;">
</div>

[FOC_KING thread on esk8](https://forum.esk8.news/t/f-of-c-open-source-free-of-charge-vesc6-board-in-development-schematics-available/74888/277)

Advantages of separation into modules?
* Suitable for further development by DIY people
* Compatibility with other FOC projects
* Understanding of FOC HW is easier
* HW development is cheaper
* Debugging is easier

Disadvantages
* Assembly takes longer time. You need to solder 46 pinheader pins manually

## How to order at JLCPCB.COM

In the /production folder there is a guide for the [ordering procedure](./production/ordering_guide.md).

## How to assemble

Below is an image of the whole kit needed for assemble. The guide for the [assembly procedure](./production/README.md) is in the /production folder.

<img src="https://github.com/nordstream3/FOC/assets/129880401/f58cc206-b7ed-49ce-b436-6f655d200584" width="400" style="float:left; margin-right:10px;">

## Usage
Use the [VESC Tool](https://vesc-project.com/vesc_tool) to configure the motor controller according to your specific motor and application requirements.

## Contributions
Contributions to this project are welcome and encouraged. If you have any suggestions or improvements, please open an issue or a pull request on the GitHub repository.

## Donate
If you find this project useful and would like to support bread-and-butter for very time consuming development and maintenance, you can [donate 1$](https://www.paypal.com/donate/?business=R5QUC7RNEPKDC&no_recurring=0&item_name=A+small+but+important+contribution+for+Development+and+Maintenance.+Thank+You+very+much.&currency_code=USD) to the creator via [PayPal](https://www.paypal.com/donate/?business=R5QUC7RNEPKDC&no_recurring=0&item_name=A+small+but+important+contribution+for+Development+and+Maintenance.+Thank+You+very+much.&currency_code=USD).
<img align="right" src="/images/QR-kode.png">


## License
FOC_KING is released under the CERN Open Hardware License (OHL), developed by the European Organization for Nuclear Research. In short, it is a permissive license that allows anyone to use, modify, and distribute the licensed hardware, as long as they provide attribution to the original creators and distribute their modifications under the same license.

## Acknowledgements
FOC_KING is built on the work of the [VESC project](https://github.com/vedderb/bldc) and the contributions of its developers and contributors. Many thanks to *mxlemming* (aka [David Molony](https://github.com/davidmolony/MESC_FOC_ESC)) and *crinq* on the vesc forum on discord for their careful review and advice. Also this project is inspired by the format and concept of the [MP2](https://github.com/badgineer/MP2-ESC) by *badgineer* and the [Cheap Focer2](https://github.com/shamansystems/Cheap-FOCer-2/blob/Developer-Branch/README.md) by *shaman*.

><sub>[markdownguide.org/basic-syntax](https://www.markdownguide.org/basic-syntax/)</sub>  
><sub>[www.markdownguide.org/hacks/](https://www.markdownguide.org/hacks/)</sub>  
><sub>[support.squarespace.com Markdown-cheat-sheet](https://support.squarespace.com/hc/en-us/articles/206543587-Markdown-cheat-sheet)
