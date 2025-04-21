# tiny_rack
tiny_rack is a eurorack case (with power board) project for DIYer who just started DIY eurorack modular synthesizers.

![tiny_rack_v2](https://github.com/KevinKeWang/tiny_rack/blob/1ec8adb37ddefb6aa67bc693148d2fd5fae44477/images/with-opz-s.jpg)

## Main features:

* One-piece 3D printed, no splicing, no metal rails required.
* Maximum current: +12V 2000mA, -12V 1000mA, +5V not available.
* Full load tested.
* The +12V and -12V output ripple is less than 100mV under all load conditions.
* Fully test powered by **[Mi 50w Power Bank 20000mAh](https://www.mi.com/global/product/mi-50w-power-bank-20000/)** (using a 15V USB decoy cable) 

## Instructions
This is a V2 version of tiny_rack. With the release of the BambuLab H2D it's easy to print larger models. So I updated the eurorack case model for the 6U52HP, and the power board circuit for a more convenient and easy to use design. This version is closer to the aluminum eurorack enclosure I sell. they are exactly the same in power and functionality. Now you can print your own 6U52hp eurorack case in any color you like! 

**If you want to see the old version of tiny_rack, go here: https://github.com/KevinKeWang/tiny_rack/tree/V1**

The main reason I started this project was the difficulty in finding a simple power bank solution when I was just starting out with DIY modules. Most of the solutions required specialized rails. needed to control the precision otherwise the modules would be difficult to install. there were many power board solutions but I couldn't be sure about the quality of their output. Some switching power supplies cause digital modulars to fail to boot.

This series contains the complete series of racks. and a power board with a decent quality of output. The racks is built entirely using 3D printing. one piece (including the rails) and simple to print. the screw holes are not threaded and need to be force screwed in using M3 screws to create the threads. this sacrifices the strength of the racks somewhat. but again makes the build very simple and ready to use straight after printing.

The power supply uses the original 7812/7912 LDO scheme. which is simple and reliable. and I've tested the ripple on the +/-12V rails to under 100mV under all load conditions. You can check the test report. it's not a perfect solution at the moment. but you can see exactly what kind of standards it can achieve.

**I no longer provide 5V in the power supply since most modules that use 5V can be switched to convert 5V from 12V**

## 3D Print Instructions
* Be sure to place the model vertically, otherwise the dimensions will be off after printing, resulting in the modular not being installed.
* I have provided BambuStudio project files that can be used as a reference for the support structure. gcode files can be used directly for printing.
* Because different brands or different diameters of nozzles may produce different results when printing small circular holes. I made a screw hole diameter test model here. It is recommended to use this model to test before printing the modular case, and select the appropriate screw hole diameter to modify the plasticity source file. When I use the BambuLab H2D printer with a 0.4mm nozzle, a 2.7mm screw hole is the best size. If you use the same printer as me, you can directly use my gcode file for printing.

![3D Printing Parameters 1](https://github.com/KevinKeWang/tiny_rack/blob/e36263a818f07229017a311b007da57f763257ab/images/3d-print-1.png)
![3D Printing Parameters 2](https://github.com/KevinKeWang/tiny_rack/blob/e36263a818f07229017a311b007da57f763257ab/images/3d-print-2.png)
![3D Printing Parameters 3](https://github.com/KevinKeWang/tiny_rack/blob/e36263a818f07229017a311b007da57f763257ab/images/3d-print-4.png)

## Schematics and PCB

**PCB front side**

![pcb-front-side](https://github.com/KevinKeWang/tiny_rack/blob/a701374cc4902f302682367b0e058243ed0a212c/power%20pcb/tiny-psu-main/smt.jpg)

**PCB back side**

![pcb-back-side](https://github.com/KevinKeWang/tiny_rack/blob/a701374cc4902f302682367b0e058243ed0a212c/power%20pcb/tiny-psu-main/smt.jpg)

**How to connect two PCBs**

![pcb-connect](https://github.com/KevinKeWang/tiny_rack/blob/a701374cc4902f302682367b0e058243ed0a212c/power%20pcb/tiny-psu-main/smt.jpg)

**There is no circuit on the back of the expansion board, so it can be directly attached to any surface with tape.**

![pcb-exp-back](https://github.com/KevinKeWang/tiny_rack/blob/a701374cc4902f302682367b0e058243ed0a212c/power%20pcb/tiny-psu-main/smt.jpg)

## Bill of materials (Core PCB)
| Designator                   | Qty | Value              | Footprint     | Description                    | Ref. Mouser                          | Ref. LCSC | References                            |
|------------------------------|-----|--------------------|---------------|--------------------------------|--------------------------------------|-----------|---------------------------------------|
| **SMT parts**                |     |                    |               |                                |                                      |           |                                       |
| LED1, LED2, LED3, LED4       | 4   | LED                | 0805          | LED                            | 638-1215UYCS530A28                   | C2987021  | EVERLIGHT 17-215/GHC-YP1Q2B16Y/3T     |
| R1, R2, R3, R5, R6, R10, R4  | 7   | 2.4k               | 0805          | Resistor                       | 667-ERJ-6ENF2401V                    | C17526    | UNI-ROYAL 0805W8F2401T5E              |
| R7, R8, R9                   | 3   | 510R               | 0805          | Resistor (Optional)            | 667-ERJ-6ENF5100V                    | C17734    | UNI-ROYAL 0805W8F5100T5E              |
| C4, C9                       | 2   | 100nF              | CASE-A-3216   | tantalum                       | 581-TAJA104K035                      | C7173     | Kyocera AVX TAJA104K035RNJ            |
| C3, C8                       | 2   | 330nF              | CASE-A-3216   | tantalum                       | 581-TAJA334K035                      | C8014     | Kyocera AVX TAJA334K035RNJ            |
| C11                          | 1   | 1uF                | CASE-A-3216   | tantalum                       | 581-TAJA105K035R                     | C7176     | Kyocera AVX TAJA105K035RNJ            |
| C10                          | 1   | 2.2uF              | CASE-B-3528   | tantalum                       | 581-TAJB225K035                      | C19276    | Kyocera AVX TAJB225K035RNJ            |
| D1, D2, D3                   | 3   | DIODE              | SMA(DO-214AC) | DIODE                          | 621-B360A-F                          | C94193    | DIODES B360A-13-F                     |
| **PTH parts**                |     |                    |               |                                |                                      |           |                                       |
| C2                           | 1   | 22uF               | D6.3xL7mm     | Electrolytic                   | 647-UKL1V220KEDANA                   | C433313   | Nichicon USV1V220MFD                  |
| C1                           | 1   | 120uF              | D8xL7mm       | Electrolytic                   | 667-50SEK120M                        | C3010233  | PANASONIC 50SEK120M                   |
| KK1, KK3, KK4                | 3   | Heat sink          |               | Heat sink                      | 532-529702B25G                       | C286227   | Heat sink                             |
| J1                           | 1   | DC Power Connector |               | 2.1 mm, 5.5 mm                 | 710-694106301002                     | C136744   | Wurth Elektronik 694106301002         |
| J2, J6                       | 2   | M3 screw terminal  |               | terminal (Optional)            | 534-7770                             | C481448   | Keystone 7770                         |
| **Adapter**                  |     |                    |               |                                |                                      |           |                                       |
| 15V Adapter                  | 1   | 15V Adapter        |               | GST60A15-P1J                   | 709-GST60A15-P1J                     | -         | MEANWELL 15V DC Adapter               |

**It is recommended to use the adapter model I have tested.**

## Bill of materials (EXP PCB)
| Designator                   | Qty | Value              | Footprint     | Description                    | Ref. Mouser                          | Ref. LCSC | References                            |
|------------------------------|-----|--------------------|---------------|--------------------------------|--------------------------------------|-----------|---------------------------------------|
| **SMT parts**                |     |                    |               |                                |                                      |           |                                       |
| J1, J2, J6, J7, J8, J9, J11, J12, J13, J14, J15, J16, J17, J18, J19, J20, J21, J22, J23, J24, J25, J26, J27, J28, J29, J30, J31, J32, J33, J34 | 30   | 2x8 header         | 2.54mm pitch  | 2x8 header                     | 710-61231620621                      | C2685064   | 2x8 male header, 2.54mm pitch         |
| J3, J4, J5, J10              | 4   | 2x3 header         | 2.54mm pitch  | 2x3 header                     | 710-61300621121                      | C358692   | 2x3 male header, 2.54mm pitch         |

## Mechanical assembly

![mount_pic_1](https://github.com/KevinKeWang/tiny_rack/blob/007ceb8c4b0aa8a4d65c0e45a3b01d15e0115c3a/images/mount-a.jpg)

![mount_pic_2](https://github.com/KevinKeWang/tiny_rack/blob/007ceb8c4b0aa8a4d65c0e45a3b01d15e0115c3a/images/mount-b.jpg)

## Test Report
Test equipment:
* Gwinstek GPP-3323 DC Power Supply (as an electronic load) **for +12V -12V**
* Itech IT8500G+ DC Electronic Load **for +5V**
* Rigol MSO5000 Oscilloscopes **for ripple measurement**
* Software for automated testing
Test methods:
Each channel is cycled from 0mA to maximum load, 50mA in one step, to test all combinations of loads and output a CSV file.

**There are some power supply solutions that can generate large ripple or even fail in specific load scenarios, such as when the gap between positive and negative rail loads is too large. That's why my tests cover all load scenarios.**

![test_workflow](https://github.com/KevinKeWang/tiny_rack/blob/f1acfb4a67a3ef867dcafc481e8d05a54906aa7b/images/test_workflow.jpg)

![test_software](https://github.com/KevinKeWang/tiny_rack/blob/1c423f3f79a77b4dd25c15d54115a057bbe4e6dc/test%20report/EurorackPowerTesterV1.png)

## License
**The tiny_rack v2 project 3D model and PCB layout is made available under a CC-BY-NC-SA-3.0 license.**

If you want to make a few boxes for your own use, go ahead and make them. If you're a synth studio and want to use them for product testing/demonstration etc, that's also welcome as long as it doesn't involve selling these case directly. **Please do not make and sell these case in bulk.**

## Links
Official website:  https://bitiworkshop.com/

Purchase here: https://store.bitiworkshop.com/
