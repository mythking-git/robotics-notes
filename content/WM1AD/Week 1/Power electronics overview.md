---
title: Power electronics overview
tags: [WM1AD, week-1]
---
## The idea
A robot's energy almost never arrives in the form its motors need. **Power electronics** converts it: AC to DC, one DC voltage to another, DC to AC for motors. This page is the map; the [[WM1AD/index|Week 3 guides]] fill in each piece.

## The four conversions
| Conversion | Circuit | Example in a robot |
|---|---|---|
| AC → DC | **Rectifier** | The charger plugged into the wall ([[Bridge rectifiers]]) |
| DC → DC | **Buck** (down) or **boost** (up) converter | 48 V battery to 5 V logic ([[DC-DC converters]]) |
| DC → AC | **Inverter** | Driving a brushless motor ([[Motor drives]]) |
| AC → AC | Frequency converter | Rare in robotics |

## The components
| Component | What it does |
|---|---|
| Resistor | Limits current, turns energy into heat |
| Capacitor | Stores energy in an electric field; smooths voltage |
| Inductor | Stores energy in a magnetic field; smooths current |
| Transformer | Steps AC voltage up or down, and isolates |
| Diode | One-way valve for current |
| BJT, MOSFET, IGBT | Electronic switches ([[Power switches]]) |

## A MOSFET as a low-side switch
The most common way a microcontroller switches a motor on and off:

```
 +V ──── motor ──── Drain
                   MOSFET   Gate ──R_G── microcontroller pin
 0 V ─────────────  Source      └─R_PD── 0 V
```

- **Main loop:** battery + → motor → drain → source → ground. The switch is on the ground side, so it's a **low-side** switch.
- **Gate resistor $R_G$:** limits the current spike that charges the gate.
- **Pull-down $R_{PD}$:** holds the gate low so the motor stays **off** if the control pin floats, at power-up or if a wire comes loose.
- **Common ground:** the controller's ground must connect to the power ground, because the MOSFET responds to gate voltage *relative to its source*.
- **Flyback diode** across the motor: when the switch turns off, the motor's inductance tries to keep current flowing. The diode gives it a path, instead of a voltage spike that would kill the MOSFET.

## Check yourself
> [!question]- 1. Why does a motor need a flyback diode but a heater doesn't?
> A motor winding is an inductor, which resists sudden changes in current and creates a voltage spike when switched off. A heater is (almost) pure resistance.
