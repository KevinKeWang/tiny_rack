# tiny_rack
tiny_rack is a eurorack rack project for DIYer with just starting DIY eurorack modular synthesizers. 

![tiny_rack](https://github.com/KevinKeWang/tiny_rack/blob/0b2d38c4e54fa3bad7a3f4de5a57aabbf00c15f2/images/main.jpg)

## Main features:

* One-piece 3D printed enclosure, no splicing, no need for any other accessories.
* Maximum supported current: +12V 1500mA, -12V 1500mA, +5V 6500mA.
* Optional +3.3V 500mA for easy project prototyping.
* Fully load tested.
* The +12V and -12V output ripple is less than 100mV under all load conditions.
* Exposed M3 screw terminals for direct connection to the test power supply. Clamps can be 
*  directly.

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


## Build instructions
The main reason I started this project was the difficulty in finding a simple power bank solution when I was just starting out with DIY modules. Most of the solutions required specialized rails. needed to control the precision otherwise the modules would be difficult to install. there were many power board solutions but I couldn't be sure about the quality of their output. Some switching power supplies cause digital modulars to fail to boot.

I spent a lot of time looking for a balance between easy to build and quality. This series contains the complete series of racks. and a power board with a decent quality of output. The racks is built entirely using 3D printing. one piece (including the rails) and simple to print. the screw holes are not threaded and need to be force screwed in using M3 screws to create the threads. this sacrifices the strength of the racks somewhat. but again makes the build very simple and ready to use straight after printing. All sizes of the racks are covered in 4CM x 4CM screw holes on the bottom and are compatible with all the PCBs in the project. so there is no need to change the power supply board if you need to change case sizes.

For the power supply. I tested several DC-DC isolation regulators and chose the model with the better output. the +12V rail provides 1500mA current output; the -12V rail can provide 1500mA or 400mA depending on the component selection. 5V rail is optional and can provide 3500mA or 6000A power output. which is perfectly adequate for the Raspberry Pi as well. Finally I have designed an optional 3.3V output pin. which is useful for DIY. if you have some project prototypes that need to use 3.3V this will give you some convenience.

The power supply uses the original 7812/7912 LDO scheme. which is simple and reliable. and I've tested the ripple on the +/-12V rails to under 100mV under all load conditions. You can check the separate test report. it's not a perfect solution at the moment. but you can know exactly what kind of standards it can achieve.
Regarding the heatsink. I designed two options. One is a standard component with soldering and the other is a custom heatsink with a hole spacing of 32mm x 32mm. heat sinks provide lower height to allow the box to accommodate deeper modules.

## Schematics and PCB
[All the PCB design files here](https://github.com/KevinKeWang/tiny_rack/tree/93aa4f3181c854528b71964095c1c5eb0407a9e2/power%20pcb "PCB Files")
![pcb](https://github.com/KevinKeWang/tiny_rack/blob/a701374cc4902f302682367b0e058243ed0a212c/power%20pcb/tiny-psu-main/smt.jpg)

## Bill of materials
| Designator                 | Value              | Footprint     | Description       | Ref. Mouser                          | Ref. LCSC | References                                                                                                                                                                  |
|----------------------------|--------------------|---------------|-------------------|--------------------------------------|-----------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| SMT parts                  |                    |               |                   |                                      |           |                                                                                                                                                                             |
| "LED1, LED2, LED3, LED4"   | LED                | 0805          | LED               | 638-1215UYCS530A28                   | C2987021  | EVERLIGHT 17-215/GHC-YP1Q2B16Y/3T                                                                                                                                           |
| R3                         | 1.2k               | 0805          | Resistor          | 667-ERJ-6ENF1201V                    | C17379    | UNI-ROYAL 0805W8F1201T5E                                                                                                                                                    |
| "R1, R2, R5, R6"           | 2.4k               | 0805          | Resistor          | 667-ERJ-6ENF2401V                    | C17526    | UNI-ROYAL 0805W8F2401T5E                                                                                                                                                    |
| R4                         | 2.4k               | 0805          | Resistor          | 667-ERJ-6ENF2401V                    | C17526    | UNI-ROYAL 0805W8F2401T5E                                                                                                                                                    |
| "R7, R8"                   | 510R               | 0805          | Resistor(**Optional**)          | 667-ERJ-6ENF5100V                    | C17734    | UNI-ROYAL 0805W8F5100T5E                                                                                                                                                    |
| C15                        | 100nF              | 0402          | Ceramic           | 187-CL05B104KB54PNC                  | C307331   | SAMSUNG CL05B104KB54PNC                                                                                                                                                     |
| "C3, C17, C19"             | 22uF               | 1206          | Ceramic           | 187-CL31A226KAHNNNE                  | C12891    | SAMSUNG CL31A226KAHNNNE                                                                                                                                                     |
| C9                         | 100nF              | CASE-A-3216   | tantalum          | 581-TAJA104K035                      | C7173     | Kyocera AVX TAJA104K035RNJ                                                                                                                                                  |
| C8                         | 330nF              | CASE-A-3216   | tantalum          | 581-TAJA334K035                      | C8014     | Kyocera AVX TAJA334K035RNJ                                                                                                                                                  |
| C11                        | 1uF                | CASE-A-3216   | tantalum          | 581-TAJA105K035R                     | C7176     | Kyocera AVX TAJA105K035RNJ                                                                                                                                                  |
| C10                        | 2.2uF              | CASE-B-3528   | tantalum          | 581-TAJB225K035                      | C19276    | Kyocera AVX TAJB225K035RNJ                                                                                                                                                  |
| "D1, D2"                   | DIODE              | SMA(DO-214AC) | DIODE             | 621-B360A-F                          | C94193    | DIODES B360A-13-F                                                                                                                                                           |
| L3                         | 33uH               | 0805          | Inductor          | 810-MLZ2012M330WT000                 | C383405   | TDK MLZ2012M330WT000                                                                                                                                                        |
| PTH parts                  |                    |               |                   |                                      |           |                                                                                                                                                                             |
| "C2, C6"                   | 22uF               | D6.3xL7mm     | Electrolytic      | 647-UKL1V220KEDANA                   | C433313   | Nichicon USV1V220MFD                                                                                                                                                        |
| C1                         | 120uF              | D8xL7mm       | Electrolytic      | 667-50SEK120M                        | C3010233  | PANASONIC 50SEK120M                                                                                                                                                         |
| IC3                        | 7812               | TO-220        | LDO               | 511-L7812CV-DG                       | C2914     | ST L7812CV-DG                                                                                                                                                               |
| IC4                        | 7912               | TO-220        | LDO               | 511-L7912CV-DG                       | C3797     | ST L7912CV-DG                                                                                                                                                               |
| IC1                        | dc-dc converter    |               |                   | 709-SKMW06F-15 **or** 709-SKMW30F-15     |           | isolated dc-dc regulated converter (choose one) :  MEANWELL SKMW06F-15 (support -12V 400mA) / MEANWELL SKMW30F-15 (support -12V 1500mA)                                     |
| IC2                        | dc-dc converter    |               |                   | 709-NID35-5 **or** 709-NID65-5           |           | dc-dc regulated converter (choose one): MEANWELL NID35-5 (support +5V 3500mA) / MEANWELL NID65-5 (support +5V 6500mA)                                                       |
| "KK1, KK2, KK3, KK4"       | Heat sink          |               |                   | 532-529702B25G                       | C286227   | Heat sink (choose one): 40x40x6mm Customized heat sink with 32x32mm hole spacing / 42x25x25mm Standard heat sinks                                                           |
| IC5                        | 3.3V converter     |               | DC/DC converter   | 919-ROF78E3.3-.5SMDR                 | -         | RECOM Power ROF-78E3.3-0.5SMD-R                                                                                                                                             |
| J7                         | DC Power Connector |               | "2.1 mm, 5.5 mm"  | 710-694106301002                     | C136744   | Wurth Elektronik 694106301002                                                                                                                                               |
| J5                         | USB Connector      |               | USB2.0 TYPE-A     | 710-614004190021                     | C2880666  | Wurth Elektronik 614004190021                                                                                                                                               |
| "J2, J6, J8, J9, J10, J11" | M3 screw terminal  |               | M3 screw terminal | 534-7770                             | C481448   | Keystone 7770                                                                                                                                                               |
| J3                         | 2x3 header         |               | 2x3 header        | 710-61300621121                      | C358692   | "2x3 male header, 2.54mm pitch"                                                                                                                                             |
| "X1, X7"                   | 2x8 header         |               | 2x8 header        | 710-61201621621                      | C429960   | "2x8 male header, 2.54mm pitch"                                                                                                                                             |
| Adapter                    |                    |               |                   |                                      |           |                                                                                                                                                                             |
| 15V Adapter                | 15V Adapter        |               | GST60A15-P1J      | 709-GSM36B15-P1J **or** 709-GST60A15-P1J | -         | "15V DC Adapter (choose one): MEANWELL GSM36B15-P1J (15V 36W) for +12V 1500mA,-12V 400mA or MEANWELL GST60A15-P1J (15V 60W) for +12V 1500mA,-12V 1500mA, +5V 3500mA/6500mA" |


## Links
editing...

## Mechanical assembly


## Test Report
testing...

## License
This 3D model and PCB layout is made available under a cc-by-sa-3.0 license.
