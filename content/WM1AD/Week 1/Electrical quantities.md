---
title: Electrical quantities
tags: [WM1AD, week-1]
---
## The idea
Everything in this module is built from a handful of quantities. Think of a circuit like water in pipes: **charge** is the water, **current** is how fast it flows, **voltage** is the pressure pushing it, and **resistance** is how narrow the pipe is.

| Quantity | Symbol | Unit | Meaning |
|---|---|---|---|
| Charge | $Q$ | coulomb (C) | Amount of electricity |
| Current | $I$ | ampere (A) | Charge per second: $I = Q/t$ |
| Voltage | $V$ | volt (V) | Energy per unit charge, the "push" |
| Resistance | $R$ | ohm (Ω) | Opposition to current |
| Power | $P$ | watt (W) | Energy per second |
| Energy | $E$ | joule (J) or kWh | Power × time |

## Ohm's law and resistance
$$V = IR$$

The resistance of a wire depends on what it's made of and its shape:

$$R = \rho\,\frac{L}{A}$$

where $\rho$ is the material's **resistivity** (Ω m), $L$ the length and $A$ the cross-sectional area. Longer or thinner means more resistance. Resistors are specified by resistance, **power rating** (how much heat they can take) and **tolerance** (e.g. ±1%).

## Power and energy
Combine $P = VI$ with Ohm's law and you get three forms. Use whichever matches what you know:

$$P = VI = I^2R = \frac{V^2}{R} \qquad E = Pt$$

- 1 J = 1 W for 1 s. Electricity bills use **kWh**: 1 kW for 1 hour = 3.6 MJ.
- Cost = energy in kWh × price per kWh. Watch the units: W × h gives Wh, so divide by 1000.

## Efficiency
No real machine converts all its input power to useful output. The rest becomes heat.

$$\eta = \frac{P_{out}}{P_{in}} \times 100\% \qquad P_{loss} = P_{in} - P_{out}$$

**Stages in series multiply:** a supply (95%) feeding a drive (97%) feeding a motor (92%) gives $0.95 \times 0.97 \times 0.92 = 84.8\%$. The overall efficiency is always lower than the worst stage.

Small efficiency gains are worth a lot over time. A machine running 16 h a day, 300 days a year, at 3 kW output, wastes about £640 a year at 85% efficiency but only about £310 at 92% (at £0.25/kWh).

## Fuses
A fuse is a wire designed to melt above a set current, opening the circuit before anything overheats. **Choose the smallest standard rating above the normal operating current.** A 1 kW charger on 240 V draws 4.2 A, so it gets a 5 A fuse.

## Worked example
A robot's 24 V battery supplies a drive motor drawing **4 A for 30 minutes**. The motor's mechanical output is 80 W. Find the power drawn, the charge and energy used, the motor's resistance as seen from the supply, its efficiency, and a suitable fuse.

> [!example]- Answer
> $P = VI = 24 \times 4 = 96$ W
> $Q = It = 4 \times 1800 = 7200$ C
> $E = Pt = 96 \times 0.5\ \text{h} = 48$ Wh $= 0.048$ kWh $= 172.8$ kJ
> $R = V/I = 24/4 = 6\ \Omega$
> $\eta = 80/96 = 83.3\%$, so 16 W is lost as heat.
> Normal current 4 A → **5 A fuse**.

## Common mistakes
- Mixing up W and Wh. Power is a rate; energy is power × time.
- Forgetting to convert minutes to hours (for kWh) or to seconds (for J).
- Writing $R = I/V$ instead of $V/I$. Check the units: Ω = V/A.
- Giving a voltage in Ω or a current in C. Units are marked.

## Check yourself
> [!question]- 1. What's the resistance of 10 m of copper wire with a 0.5 mm² cross-section? ($\rho_{Cu} = 1.72\times10^{-8}$ Ω m)
> $R = 1.72\times10^{-8} \times 10 / (0.5\times10^{-6}) = 0.344\ \Omega$. Remember mm² = $10^{-6}$ m².

> [!question]- 2. A 2 Ω winding carries 5 A. How much power does it waste?
> $P = I^2R = 25 \times 2 = 50$ W.

> [!question]- 3. Three stages at 90%, 95% and 85%. Overall efficiency?
> $0.9 \times 0.95 \times 0.85 = 72.7\%$.
