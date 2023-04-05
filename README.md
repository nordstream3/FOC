# FOCAL - Open Source Vesc6 compatible hardware for Field Oriented Control (FOC)
FOCAL is an open-source motor controller board based on the VESC6 hardware design, modified to use individual gate drivers for each phase instead of the DRV8323RS chip. It is powered by an STM32F405 CPU and is capable of running Field Oriented Control (FOC) firmware.

## Features
75V/150A continuous rating
3-phase FOC motor control
Individual gate drivers for each phase
STM32F405 CPU
Onboard IMU
12V for gate drivers, 5V for USB-C and IMU, and 3.3V for CPU and current-sense amplification (op-amps for all three phases)
Cheap and always up-to-date with cheapest and **well stocked** components available for ordering at [JLCPCB](https://jlcpcb.com/) and [LCSC](https://www.lcsc.com)
![](ns.png)

## Getting Started
Prerequisites
To use FOCAL, you will need the following:

A brushless motor
A power source capable of supplying up to 75V and 150A. Minimum voltage is 12V
A USB cable to connect to a computer for programming and configuration
Motor control software, such as the VESC firmware

## Installation
To install the FOCAL board, follow these steps:

Order the PCB from JLCPCB using the provided gerber files
Purchase the necessary components (BOM available in the repository)
Solder the components onto the PCB
Program the firmware onto the board using a programmer
Connect the motor, power source, and USB cable

## Usage
After installation, use the VESC firmware to configure the motor controller according to your specific motor and application requirements.

## Contributions
Contributions to the FOCAL project are welcome and encouraged. If you have any suggestions or improvements, please open an issue or a pull request on the GitHub repository.

## Donate
If you find this project useful and would like to support its development, you can donate to the creator via PayPal (link to be provided).

## License
FOCAL is released under the MIT License. See the LICENSE file for more information.

## Contact
For any questions or inquiries about the FOCAL project, please contact the creator at [email address to be provided].

## Acknowledgements
FOCAL is built on the work of the VESC project and the contributions of its many developers and contributors. We would like to thank the VESC community for their support and inspiration in the development of FOCAL.

Motor Controller hardware running [VESC6](https://github.com/vedderb/bldc) open source software.

Schematics based on [VESC6 75V 300A Schematics](https://vesc-project.com/sites/default/files/Benjamin%20Posts/vesc_75_300.pdf) and [Cheap Focer2](https://github.com/shamansystems/Cheap-FOCer-2/blob/Developer-Branch/README.md).
