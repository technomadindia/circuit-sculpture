# Christmas Star

Decorative ornament built using red/green LEDs and an IC 555 timer based alternating blinker circuit.

## Video

## Schematic
Created using KiCad 7.x (https://www.kicad.org/)

![Christmas Star](/christmas-star/christmas-star.png)

## Circuit Logic

## Bill of Materials

| Item | Qty | Reference(s)                                      | Value       | LibPart               | Footprint                                   |
| ---- | --- | ------------------------------------------------- | ----------- | --------------------- | ------------------------------------------- |
| 1    | 1   | C1                                                | 0.01uF      | Device:C_Small        |                                             |
| 2    | 1   | C2                                                | 1uF         | Device:C_Polarized_US |                                             |
| 3    | 12  | D1, D2, D3, D4, D5, D6, D7, D8, D9, D10, D11, D12 | LED         | Device:LED            |                                             |
| 4    | 1   | D13                                               | 1N4001      | Diode:1N4001          | Diode_THT:D_DO-41_SOD81_P10.16mm_Horizontal |
| 5    | 1   | J1                                                | Barrel_Jack | Connector:Barrel_Jack |                                             |
| 6    | 2   | R1, R2                                            | 22E         | Device:R_US           |                                             |
| 7    | 1   | R3                                                | 680K        | Device:R_US           |                                             |
| 8    | 1   | R4                                                | 820K        | Device:R_US           |                                             |
| 9    | 1   | U1                                                | NE555P      | Timer:NE555P          | Package_DIP:DIP-8_W7.62mm                   |
|      |     |                                                   |             |                       |                                             |

## Blog Post
https://technomad.in/christmas-star-ornament/
