# Glowing Sunflower

Decorative piece built using a slow ramp-up ramp-down circuit designed around IC 555 timer.

## Video
https://youtu.be/tPpAlSBtsEk

## Schematic
Created using KiCad 7.x (https://www.kicad.org/)

![Sunflower](/glowing-sunflower/glowing-sunflower.png)

## Circuit Logic
The default behavior of IC 555 in Astable Multivibrator mode (kindly refer to NE555/LM555/SE555 datasheet) is a square wave output at pin 3. But since we want a glow effect (slowly increasing/decreasing intensity cycle), we will implement a variant here. 

Instead of using the VCC as charging source, and pin 7 as discharge source, we use pin 3 for both. When output is HIGH, the capacitor C2 will charge via R9. Upon reaching the 2/3 VCC threshold, the output will switch to LOW and C2 will begin discharging via the same R9 until 1/3 VCC is reached whereupon the output turns HIGH again. The cycle repeats itself at close to 50% duty cycle with time period of T = 2 * ln(2) * R9C2. In this circuit we have used R9 = 750 Ohm and C2 = 1000 microfarad, hence our time period would be approximately 1 sec.

For driving the LEDs with intensity proportional to the charge across the capacitor, we use pin 2 to drive the LEDs via a NPN BJT 2N2222A. Each Orange LED has a 100 Ohm current limiting resistor connected in series with it.

The circuit is powered by a 5V DC source via a barrel jack connector.

## Bill of Materials

| Item | Qty | Reference(s)                   | Value       | LibPart                | Footprint                       |
| ---- | --- | ------------------------------ | ----------- | ---------------------- | ------------------------------- |
| 1    | 1   | C1                             | 0.01uF      | Device:C_Small         |                                 |
| 2    | 1   | C2                             | 1000uF      | Device:C_Polarized_US  |                                 |
| 3    | 8   | D1, D2, D3, D4, D5, D6, D7, D8 | Orange LED  | Device:LED             |                                 |
| 4    | 1   | J1                             | Barrel_Jack | Connector:Barrel_Jack  |                                 |
| 5    | 1   | Q1                             | PN2222A     | Transistor_BJT:PN2222A | Package_TO_SOT_THT:TO-92_Inline |
| 6    | 8   | R1, R2, R3, R4, R5, R6, R7, R8 | 100E        | Device:R_US            |                                 |
| 7    | 1   | R9                             | 750E        | Device:R_US            |                                 |
| 8    | 1   | U1                             | NE555P      | Timer:NE555P           | Package_DIP:DIP-8_W7.62mm       |
|      |     |                                |             |                        |                                 |

## Blog Post
https://technomad.in/decorative-glowing-sunflower/