---
date: 2022-08-05
categories:
  - Upcycling
  - Integrated Circuits
authors:
  - Timothé
---
# Salvaged Electronic ICs

List of salvaged integrated circuits and their associated datasheets + functionalities.

<!-- more -->
## Part Meanings :

[Thorough explanation on 74LS TTL components](http://homepage.divms.uiowa.edu/~jones/logicsim/man/node5.html) : 

**SN** : [Semiconductor Network](https://www.industrialalchemy.org/articleview.php?item=741) trademark of TexasInstruments, wich first got the idea of combining multiple solid state devices into a single package. (in 1961) So the prefix SN indicates that the chip was made by Texas Instruments; other manufacturers have their own prefix codes, but if the remainder of the chip name matches, the chips should perform exactly the same function.

Additional one letter codes may be added as prefixes or suffixes to this code, for example, RSN indicates radiation hardened chips made by Texas Instruments, and SNM indicates the use of quality control procedures specified by the military specification MIL-STD-883

**74** : [7400, a TI integrated circuits range with TTL logic](https://en.wikipedia.org/wiki/7400-series_integrated_circuits) able to operate from 0 up to 70°C. 54 range stands for millitary or industrial grade 55 to 125°C.

Terminal **N** : plastic package (J for ceramic)

**TTL** : stands for *Transistor Transistor Logic*, which signifies that two transistors are used to drive each output of each chip, one for pulling the output down to a low level, and one for pulling the output up to a high level.

The TTL family has at least 6 subfamilies which offer different speed/power tradeoffs.

| family                      |      | delay (ns) | power (mW) |
| --------------------------- | ---- | ---------- | ---------- |
| basic                       |      | 10         | 10         |
| low-power                   | L    | 35         | 1          |
| Schottky                    | S    | 3          | 18         |
| low-power Schottky          | LS   | 9          | 2          |
| advanced Schottky           | AS   | 1.5        | 10         |
| advanced low-power Schottky | ALS  | 4          | 1          |

**LS** stands for low-power Schottky subfamily

**RTL** (*Resistor Transistor Logic*) and **DTL** (*Diode Transistor Logic*) : older than TTL and slower.

**MOS** : (*Metal Oxide Semiconductor*) : smaller and consume less than TTL logic components

## References : 

### Texas Instrument 
TTL range ICs : 

|  Reference  |                                                            Description                                                             | Doc                                                                                            |
| :---------: | :--------------------------------------------------------------------------------------------------------------------------------: | ---------------------------------------------------------------------------------------------- |
|  SN74LS00N  |                                                         quad 2-input NAND                                                          |                                                                                                |
|  SN74LS03N  |                                           quad 2-input NAND with open collector outputs                                            |                                                                                                |
|  SN74LS04N  |                                                              hex NOT                                                               |                                                                                                |
|   SN7406N   |                                                                                                                                    |                                                                                                |
|   SN7407N   |                                                                                                                                    |                                                                                                |
|   SN7420N   |                                                                                                                                    |                                                                                                |
|  SN7490AN   |                                                    decade (0-9) ripple counter                                                     |                                                                                                |
|  SN74LS93N  |                                                    4-bit (0-15) ripple counter                                                     |                                                                                                |
| SN74LS123N  |                                                                                                                                    |                                                                                                |
| SN74LS132N  | quad 2-input [NAND](https://en.wikipedia.org/wiki/NAND_gate) with [schmitt trigger](https://en.wikipedia.org/wiki/Schmitt_trigger) | [AllDatasheet](https://pdf1.alldatasheet.com/datasheet-pdf/view/5651/MOTOROLA/SN74LS132N.html) |
| SN74LS138N  |                                                                                                                                    |                                                                                                |
| SN74LS139AN |                                                                                                                                    |                                                                                                |
| SN74LS147N  |                        8 line to 3 line [priority encoder](https://en.wikipedia.org/wiki/Priority_encoder)                         | [AllDatasheet](https://pdf1.alldatasheet.com/datasheet-pdf/view/5657/MOTOROLA/SN74LS147N.html) |
| SN74LS148N  |                                                                                                                                    |                                                                                                |
| SN74LS153N  |                                                                                                                                    |                                                                                                |
| SN74LS159N  |                                                                                                                                    |                                                                                                |
| SN74LS240N  |                                                                                                                                    |                                                                                                |
| SN74LS245N  |                                                                                                                                    |                                                                                                |

### Motorola

| Reference   | Description | Doc  |
| ----------- | ----------- | ---- |
| MC1741CP1   |             |      |
| MC14011B    |             |      |
| MC14023BCP  |             |      |
| MC14027BCP  |             |      |
| MC14049UBCP |             |      |
| MC14490P    |             |      |
| MC14572UBCP |             |      |

### Resistor arrays

| Reference    | Description                       | Doc                                                          |
| ------------ | --------------------------------- | ------------------------------------------------------------ |
| 4116-001-681 | 680 Ohm 8 isolated resistor array | [Mouser](https://www.mouser.fr/datasheet/2/54/4100R-776985.pdf) |
|              |                                   |                                                              |
|              |                                   |                                                              |

### Other

| Reference    | Description                                                  | Doc                                                          |
| ------------ | ------------------------------------------------------------ | ------------------------------------------------------------ |
| TIL111       | 6-Pin Phototransistor Optocouplers                           | [Mouser](https://www.mouser.fr/datasheet/2/308/1/fairchild_semiconductor_til111m-1191727.pdf) |
| TMS4116-15NL |                                                              |                                                              |
| CA3140E      | BiMOS Operational Amplifier with MOSFET Input/Bipolar Output | [Renesas](https://www.renesas.com/us/en/document/dst/ca3140-ca3140a-datasheet) |

