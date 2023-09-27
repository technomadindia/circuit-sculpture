# Christmas Star

Decorative Christmas ornament built using red/green LEDs and an IC 555 timer based alternating blinker circuit.

## Video
https://youtu.be/6iKLjG4pp_g

## Schematic
Created using KiCad 7.x (https://www.kicad.org/)

![Christmas Star](/christmas-star/christmas-star.png)

## Circuit Logic
The circuit is an Astable Multivibrator designed around the IC 555 timer (kindly refer to NE555/LM555/SE555 datasheet) with square wave output at pin 3.

In the default configuration the duty cycle (ratio of output HIGH time vs LOW time) is unequal. This is due to the fact that the capacitor C2 charges via resistors R3 and R4, but discharges only via R4. To balance that out we implement a minor tweak by adding the Diode D13, which largely bypasses R4 while charging. In the resulting circuit the HIGH time tH = 0.8R3C2, and LOW time tL = 0.7R4C2. Therefore with an appropriate ratio of R3 and R4, we can get an improved performance with close to 50% duty cycle.

We use six Red LEDs as D1 thru D6, and six Green LEDs as D7 thru D12. When the output at pin 3 is HIGH, the Green LEDs light up, and when it's LOW, the Red ones do. Note that we are directly driving the LEDs from the pin 3 of IC 555. This is possible because the maximum rated current source/sink is at 200mA. With limiting resistors R1/R2 of 22 Ohms, each LED draws approximately 25mA making the total maximum current draw at any given time at 150mA.
The circuit is powered by a 5V DC source via a barrel jack connector.

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
