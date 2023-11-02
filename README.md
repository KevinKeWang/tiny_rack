# tiny_rack
tiny_rack is a eurorack case (with power board) project for DIYer who just started DIY eurorack modular synthesizers.

![tiny_rack](https://github.com/KevinKeWang/tiny_rack/blob/1ec8adb37ddefb6aa67bc693148d2fd5fae44477/images/with-opz-s.jpg)

![powered_by_power_bank](https://github.com/KevinKeWang/tiny_rack/blob/bff1faffcf42d668e23ff30304d923c977059271/images/powered_by_power_bank_out.jpg)

## Main features:

* One-piece 3D printed, no splicing, no metal rails required.
* Maximum current: +12V 1500mA, -12V 1500mA, +5V 6500mA.
* Optional +3.3V 500mA for easy project prototyping.
* Full load tested.
* The +12V and -12V output ripple is less than 100mV under all load conditions.
* Exposed M3 screw terminals for direct connection to the test power supply. Clamps can be directly.
* Fully test powered by **[Mi 50w Power Bank 20000mAh](https://www.mi.com/global/product/mi-50w-power-bank-20000/)** (using a 15V USB decoy cable) 

**While this project puts the case and circuit together, they are both independently. This +/-12V 1500mA power supply is usually enough even in a 9U84hp case.**

## Type of rack
| Rack                | Min depth          | Max depth         | Description                         |
|---------------------|--------------------|-------------------|-------------------------------------|
| tiny-box-18hp       | 28mm               | 50mm              | 18hp                                |
| tiny-box-26hp       | 28mm               | 50mm              | 26hp                                |
| tiny-box-34hp       | 28mm               | 50mm              | 34hp                                |
| tiny-box-42hp       | 28mm               | 50mm              | 42hp                                |
| tiny-cube-26hp      | 78mm               | 100mm             | 26hp, ultra deep                    |
| tiny-workbench-34hp | 50mm               | 50mm              | 34hp, for modular testing           |
| tiny-rack-2x44hp    | 55mm               | 65mm              | 2x44hp, more inner space for DIY    |

![more_size](https://github.com/KevinKeWang/tiny_rack/blob/007ceb8c4b0aa8a4d65c0e45a3b01d15e0115c3a/images/more-size.jpg)

![workbench](https://github.com/KevinKeWang/tiny_rack/blob/007ceb8c4b0aa8a4d65c0e45a3b01d15e0115c3a/images/workbench.jpg)

## Instructions
The main reason I started this project was the difficulty in finding a simple power bank solution when I was just starting out with DIY modules. Most of the solutions required specialized rails. needed to control the precision otherwise the modules would be difficult to install. there were many power board solutions but I couldn't be sure about the quality of their output. Some switching power supplies cause digital modulars to fail to boot.

It took me some time to find the balance between ease of production and quality. This series contains the complete series of racks. and a power board with a decent quality of output. The racks is built entirely using 3D printing. one piece (including the rails) and simple to print. the screw holes are not threaded and need to be force screwed in using M3 screws to create the threads. this sacrifices the strength of the racks somewhat. but again makes the build very simple and ready to use straight after printing. All sizes of the racks are covered in 4CM x 4CM screw holes on the bottom and are compatible with all the PCBs in the project. so there is no need to change the power supply board if you need to change case sizes.

For the power supply. I tested several DC-DC isolation regulators and chose the model with the better output. the +12V rail provides 1500mA current output; the -12V rail can provide 1500mA or 400mA depending on the component selection. 5V rail is optional and can provide 3500mA or 6000A power output. which is perfectly adequate for the Raspberry Pi as well. Finally I have designed an optional 3.3V output pin. which is useful for DIY. if you have some project prototypes that need to use 3.3V this will give you some convenience.

The power supply uses the original 7812/7912 LDO scheme. which is simple and reliable. and I've tested the ripple on the +/-12V rails to under 100mV under all load conditions. You can check the test report. it's not a perfect solution at the moment. but you can see exactly what kind of standards it can achieve.
Regarding the heatsink. I designed two options. One is a standard component with soldering and the other is a customized heatsink with a hole spacing of 32mm x 32mm. with customized heat sink the height of power board can be much lower. 

**In the current scheme, the use of +5V is not recommended and will increase the output ripple on all channels.**

## 3D Print Instructions
* Be sure to place the model vertically, otherwise the dimensions will be off after printing, resulting in the modular not being installed.
* Do not add supports in the screw holes, extremely difficult to remove.
* I have provided BambuStudio project files in the "bumbu p1s" folder that can be used as a reference for the support structure. gcode files can be used directly for printing.
* PLA Basic material is recommended, easiest to print. 

![3d-print](https://github.com/KevinKeWang/tiny_rack/blob/825108e056bc47a1c86c06eaf0f1a0fd0326eaad/images/3d-print-en.png)

## Schematics and PCB
[All the PCB design files here](https://github.com/KevinKeWang/tiny_rack/tree/93aa4f3181c854528b71964095c1c5eb0407a9e2/power%20pcb "PCB Files")
![pcb](https://github.com/KevinKeWang/tiny_rack/blob/a701374cc4902f302682367b0e058243ed0a212c/power%20pcb/tiny-psu-main/smt.jpg)

## Bill of materials
| Designator                   | Qty | Value              | Footprint     | Description                    | Ref. Mouser                          | Ref. LCSC | References                            |
|------------------------------|-----|--------------------|---------------|--------------------------------|--------------------------------------|-----------|---------------------------------------|
| **SMT parts**                |     |                    |               |                                |                                      |           |                                       |
| LED1, LED2, LED3, LED4       | 4   | LED                | 0805          | LED                            | 638-1215UYCS530A28                   | C2987021  | EVERLIGHT 17-215/GHC-YP1Q2B16Y/3T     |
| R3                           | 1   | 1.2k               | 0805          | Resistor                       | 667-ERJ-6ENF1201V                    | C17379    | UNI-ROYAL 0805W8F1201T5E              |
| R1, R2, R4                   | 3   | 2.4k               | 0805          | Resistor                       | 667-ERJ-6ENF2401V                    | C17526    | UNI-ROYAL 0805W8F2401T5E              |
| R5, R6                       | 2   | 2.4k               | 0805          | Resistor (Optional)            | 667-ERJ-6ENF2401V                    | C17526    | UNI-ROYAL 0805W8F2401T5E              |
| R7, R8                       | 2   | 510R               | 0805          | Resistor (Optional)            | 667-ERJ-6ENF5100V                    | C17734    | UNI-ROYAL 0805W8F5100T5E              |
| C9                           | 1   | 100nF              | CASE-A-3216   | tantalum                       | 581-TAJA104K035                      | C7173     | Kyocera AVX TAJA104K035RNJ            |
| C8                           | 1   | 330nF              | CASE-A-3216   | tantalum                       | 581-TAJA334K035                      | C8014     | Kyocera AVX TAJA334K035RNJ            |
| C11                          | 1   | 1uF                | CASE-A-3216   | tantalum                       | 581-TAJA105K035R                     | C7176     | Kyocera AVX TAJA105K035RNJ            |
| C10                          | 1   | 2.2uF              | CASE-B-3528   | tantalum                       | 581-TAJB225K035                      | C19276    | Kyocera AVX TAJB225K035RNJ            |
| D1, D2                       | 2   | DIODE              | SMA(DO-214AC) | DIODE                          | 621-B360A-F                          | C94193    | DIODES B360A-13-F                     |
| C15                          | 1   | 100nF              | 0402          | Ceramic (Optional for 3.3V)    | 187-CL05B104KB54PNC                  | C307331   | SAMSUNG CL05B104KB54PNC               |
| C3, C17, C19                 | 3   | 22uF               | 1206          | Ceramic (Optional for 3.3V)    | 187-CL31A226KAHNNNE                  | C12891    | SAMSUNG CL31A226KAHNNNE               |
| L3                           | 1   | 33uH               | 0805          | Inductor (Optional for 3.3V)   | 810-MLZ2012M330WT000                 | C383405   | TDK MLZ2012M330WT000                  |
| **PTH parts**                |     |                    |               |                                |                                      |           |                                       |
| C2, C6                       | 2   | 22uF               | D6.3xL7mm     | Electrolytic                   | 647-UKL1V220KEDANA                   | C433313   | Nichicon USV1V220MFD                  |
| C1                           | 1   | 120uF              | D8xL7mm       | Electrolytic                   | 667-50SEK120M                        | C3010233  | PANASONIC 50SEK120M                   |
| IC3                          | 1   | 7812               | TO-220        | LDO                            | 511-L7812CV-DG                       | C2914     | ST L7812CV-DG                         |
| IC4                          | 1   | 7912               | TO-220        | LDO                            | 511-L7912CV-DG                       | C3797     | ST L7912CV-DG                         |
| IC1                          | 1   | dc-dc converter    |               | dc-dc converter                | 709-SKMW06F-15 **or** 709-SKMW30F-15 |           | isolated dc-dc regulated converter    |
| KK1, KK2, KK3, KK4           | 2   | Heat sink          |               | Heat sink                      | 532-529702B25G                       | C286227   | Heat sink                             |
| J7                           | 1   | DC Power Connector |               | 2.1 mm, 5.5 mm                 | 710-694106301002                     | C136744   | Wurth Elektronik 694106301002         |
| IC2                          | 1   | dc-dc converter    |               | Converter (Optional for 5V)    | 709-NID65-5                          |           | MEANWELL NID65-5 (support +5V 6500mA) |
| J5                           | 1   | USB Connector      | USB2.0 TYPE-A | Connector (Optional for 5V)    | 710-614004190021                     | C2880666  | Wurth Elektronik 614004190021         |
| IC5                          | 1   | 3.3V converter     |               | Converter (Optional for 3.3V)  | 919-ROF78E3.3-.5SMDR                 | -         | RECOM Power ROF-78E3.3-0.5SMD-R       |
| J3                           | 1   | 2x3 header         | 2.54mm pitch  | 2x3 header (Optional for 3.3V) | 710-61300621121                      | C358692   | 2x3 male header, 2.54mm pitch         |
| J2, J6, J8, J9, J10, J11     | 6   | M3 screw terminal  |               | terminal (Optional)            | 534-7770                             | C481448   | Keystone 7770                         |
| X1, X7                       | 2   | 2x8 header         | 2.54mm pitch  | 2x8 header                     | 710-61201621621                      | C429960   | 2x8 male header, 2.54mm pitch         |
| **Hardware Mount**           |     |                    |               |                                |                                      |           |                                       |
| flathead screw               | 4   | M2.5 x 20mm        |               |                                |                                      |           | for pcb mount                         |
| hex nylon nuts               | 4   | M2.5 x 8mm         |               |                                |                                      |           | for pcb mount                         |
| mounting screws              | 4   | M3 x 10mm + 6mm    |               |  (Optional for heat sink)      |                                      |           | for heat sink mount                   |
| spring                       | 4   | 7mm x 5mm          |               |  (Optional for heat sink)      |                                      |           | for heat sink mount                   |
| **Adapter**                  |     |                    |               |                                |                                      |           |                                       |
| 15V Adapter                  | 1   | 15V Adapter        |               | GST60A15-P1J                   | 709-GSM36B15-P1J **or** 709-GST60A15-P1J | -         | MEANWELL 15V DC Adapter               |

IC1: isolated dc-dc regulated converter (choose one) :  MEANWELL SKMW06F-15 (support -12V 400mA) or MEANWELL SKMW30F-15 (support -12V 1500mA)

Heat sink (choose one): 40x40x6mm Customized heat sink with 32x32mm hole spacing or 42x25x25mm Standard heat sinks

15V DC Adapter (choose one): MEANWELL GSM36B15-P1J (15V 36W) for 12V 400mA or MEANWELL GST60A15-P1J (15V 60W) for -12V 1500mA

**It is recommended to use the adapter model I have tested.**

## Mechanical assembly

**use regular heat sink:**

![use_regulated_heat_sink](https://github.com/KevinKeWang/tiny_rack/blob/c01cd60983afbae05b4fed6ef6f4171f4c9550ec/images/pcb-a.jpg)

**use customized heat sinks:**

![use_custom_heat_sink](https://github.com/KevinKeWang/tiny_rack/blob/c01cd60983afbae05b4fed6ef6f4171f4c9550ec/images/pcb-b.jpg)

**mounting guide:**

![mount_pic_1](https://github.com/KevinKeWang/tiny_rack/blob/007ceb8c4b0aa8a4d65c0e45a3b01d15e0115c3a/images/mount-a.jpg)

![mount_pic_2](https://github.com/KevinKeWang/tiny_rack/blob/007ceb8c4b0aa8a4d65c0e45a3b01d15e0115c3a/images/mount-b.jpg)

**short circuit protection:**

![mount_pic_3](https://github.com/KevinKeWang/tiny_rack/blob/007ceb8c4b0aa8a4d65c0e45a3b01d15e0115c3a/images/short-circuit-protection.jpg)

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

Test result (use SKMW06F-15 and GSM36B15-P1J) [full test file](https://github.com/KevinKeWang/tiny_rack/blob/bff1faffcf42d668e23ff30304d923c977059271/test%20report/TestReport_SKMW06F-15_and_GSM36B15-P1J.csv):

| Output      | Maximum load          | Maximum ripple    |
|-------------|-----------------------|-------------------|
| +12V        | 1500mA                | 60mV              |
| -12V        | 400mA                 | 50mV              |
| +5V         | -                     | untested          |
| +3.3V       | -                     | untested          |

Test result (use SKMW06F-15 and **Mi 50w Power Bank 20000mAh**) [full test file](https://github.com/KevinKeWang/tiny_rack/blob/bff1faffcf42d668e23ff30304d923c977059271/test%20report/TestReport_SKMW06F-15_and_Mi_50w_Power_Bank_20000mAh.csv):

| Output      | Maximum load          | Maximum ripple    |
|-------------|-----------------------|-------------------|
| +12V        | 1500mA                | 80mV              |
| -12V        | 400mA                 | 50mV              |
| +5V         | -                     | untested          |
| +3.3V       | -                     | untested          |

Test result (use SKMW30F-15 and GST60A15-P1J):

| Output      | Maximum load          | Maximum ripple    |
|-------------|-----------------------|-------------------|
| +12V        | 1500mA                | ?                 |
| -12V        | 1500mA                | ?                 |
| +5V         | 6500mA                | untested          |
| +3.3V       | 500mA                 | untested          |

## License
This 3D model and PCB layout is made available under a cc-by-sa-3.0 license.

## Links
Official website:  https://biti.tech/

Thingiverse: https://www.thingiverse.com/thing:6279851

Youtube: https://www.youtube.com/@KEVIN_KE

Bilibili: https://space.bilibili.com/319608785
