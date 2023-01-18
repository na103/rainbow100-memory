
# Rainbow 100B memory extension
this is a remake of RAM expansion board for [Digital Rainbow 100](https://en.wikipedia.org/wiki/Rainbow_100) rev B<br>

![alt text](https://github.com/na103/rainbow100-memory/blob/main/img/memory.jpg "memory extension")

This expansion board it can reach up to 896Kb of RAM. differently to 8088 XT PCs, Rainbow 100 architecture is not limited at 640Kb of memory.<br>
Kicad schematics is derived from [Tony Duell's notes](https://github.com/na103/rainbow100-memory/blob/main/docs/Duell_ram_expansion.pdf) and at the end verified with [original DEC schematics](https://github.com/na103/rainbow100-memory/tree/main/docs/Dec).<br>
95% of the components and traces have been rebuilt respecting the original position; only the bipolar Prom E7 whos entrusted control logic for the memory banks switch has been replaced with a extra large GAL22V10.

## Bill of materials
| Qt. |    Description     |             Designator          |    Mouser Part     |             Note              |
|:---:|--------------------|---------------------------------|--------------------|-------------------------------|
|27   |Cap. 220 nF 50V     |C1 -C27                          |C430C224Z5U5TA      |                               |
|1    |Cap. 10uF 35V       |C33                              |MAL213831109E3      |                               |
|5    |Cap. 47nF 50V       |C28 - C32                        |C410C473Z5U5TA      |                               |
|2    |Cap. 10nF 50V       |C34 C35                          |C410C103Z5U5TA      |                               |
|1    |Bead Ferrite        |FB1                              |2743002112          |                               |
|1    |Rnet 9x470Ω 10 pin  |RN4                              |4610X-101-471LF     |                               |
|2    |Rnet 9x1kΩ 10 pin   |RN3 RN2                          |4610X-101-102LF     |                               |
|1    |Rnet 9x4.7kΩ 10 pin |RN1                              |4610X-AP1-472LF     |                               |
|9    |R 39Ω               |R18                              |CFR-25JB-52-39R     |                               |
|1    |R 100Ω              |U21,U26,U29                      |CFR-25JT-52-100R    |                               |
|9    |R 47Ω               |R1 - R9                          |CFR-25JB-52-47R     |                               |
|1    |Switch DIP 4POS     |SW1                              |78RB04ST            |                               |
|1    |025X025 REC 2X30P   |J1                               |5-102766-4          |                               |
|27   |16P DIP SKT         |E1-E5 E9-E13 E17-E21 E25-E28     |1-2199298-4         |                               |
|     |                    |E33-E36 E41-E44                  |                    |                               |
|1    |24P DIP SKT         |E7                               |1-2199298-8         | optional, useful for testing  |
|1    |GAL 22V10           |E7                               |ATF22V10C-15PU      | need programmer like TL866    |
|3    |74S03N              |E8 E14 E15                       |SN74LS03N           |                               |
|1    |74LS00N             |E16                              |SN74LS00N           |                               |
|2    |74S258N             |E23 E24                          |SN74LS258N          |                               |
|1    |74LS27N             |E32                              |SN74LS27N           |                               |
|1    |74LS74AN            |E40                              |SN74LS74AN          |                               |
|2    |74LS04N             |E31 E39                          |SN74LS04N           |                               |
|1    |74S51N              |E6                               |SN74LS51N           |                               |
|1    |74LS125AN           |E22                              |SN74LS125AN         |                               |
|1    |74LS393N            |E30                              |SN74LS393N          |                               |
|1    |74LS244N            |E38                              |SN74LS244N          |                               |
|1    |74S280N             |E29                              |SN74LS280N          |                               |
|1    |74LS245N            |E37                              |SN74LS245N          |                               |
|1    |74S32N              |E45                              |SN74LS32N           |                               |
|27   |DRAM 41256-15 or    |E1-E5 E9-13 E17-E21 E25-E28      |                    | from ebay or [utsource](https://www.utsource.net)|
|     |4164-15 max 150ns   |E33-E36 E41-E44                  |                    |                               |
<br><br>
## Memory dip switch set-up

The DIP switches are to be set according to how many banks are populated and with kind of DRAM chip (256kb or 64kb).

![alt text](https://github.com/na103/rainbow100-memory/blob/main/img/banks-768x576.jpg "banks position")

| Dip 1-2-3-4    |    bank1     |    bank2     |    bank3     |
|:--------------:|--------------|--------------|--------------|
| off off off on |      64K     |              |              |
| off off off on |      64K     |     64K      |              |
| off off off on |      64K     |     64K      |      64K     |
| on  off off on |      256K    | 64K or empty | 64K or empty |
| on  on  off on |      256K    |     256K     | 64K or empty |
| on  on  on  on |      256K    |     256K     |      256K    |

## Building notes

due to the E7 larger size all memory banks are closer to the edge of the board, the two plastic supports need to be filed slightly to get them into their seat
<br>

![alt text](https://github.com/na103/rainbow100-memory/blob/main/img/plastic_stand.jpg "stand support")
<br>
# License

This work is licensed under a Creative Commons Attribution 4.0 International License. See [https://creativecommons.org/licenses/by/4.0/](https://creativecommons.org/licenses/by/4.0/).
