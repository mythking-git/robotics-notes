---
title: Voltage node method
tags: [WM1AD, week-1]
---
## The idea
When a circuit has more than one source, simple series–parallel reduction stops working. The **node method** picks one unknown, the voltage at the main junction, and writes **KCL there** with every current expressed as $\Delta V / R$. One equation, one unknown.

## The method
1. Mark the nodes and choose a **reference node** (ground, 0 V). Every node voltage is measured from it.
2. Draw an assumed direction for each branch current.
3. At the principal node N, write **KCL** with each current as (voltage at one end − voltage at the other) ÷ R.
4. Solve for $V_N$.
5. Work out every current, voltage drop and power, then **check the power balance**.

## Worked example
Two sources share a load. $V_A = 24$ V connects to node N through $R_1 = 6\ \Omega$. $V_B = 12$ V connects through $R_3 = 4\ \Omega$. A load $R_2 = 12\ \Omega$ goes from N to ground. Find $V_N$ and every current.

> [!example]- Answer
> KCL at N (currents from the sources in = current to ground out):
> $$\frac{24 - V_N}{6} + \frac{12 - V_N}{4} = \frac{V_N}{12}$$
> Multiply by 12: $2(24 - V_N) + 3(12 - V_N) = V_N$ → $84 = 6V_N$ → $V_N = 14$ V.
> $I_1 = (24 - 14)/6 = 1.67$ A · $I_3 = (12 - 14)/4 = -0.5$ A · $I_2 = 14/12 = 1.17$ A
> $I_3$ is **negative**: current flows *into* the 12 V source, which is being **charged**. KCL check: $1.67 - 0.5 = 1.17$ ✓
> Power: resistors $16.7 + 1.0 + 16.3 = 34$ W. Sources: $24 \times 1.67 - 12 \times 0.5 = 40 - 6 = 34$ W ✓

A source with **negative power** is absorbing energy, like a robot's battery being charged by the main supply.

## Common mistakes
- Mixing directions: if every current is written as "flowing out of N", then $\sum = 0$. If some are in and some out, then in = out. Pick one style and stick with it.
- Forgetting to multiply through by a common denominator before rearranging.

## Check yourself
> [!question]- 1. In the example, what would $V_N$ be if the 12 V source were removed (its branch disconnected)?
> Now it's a plain divider: $24 \times \dfrac{12}{6 + 12} = 16$ V.
