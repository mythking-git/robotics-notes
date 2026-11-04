---
title: DC motor performance and selection
tags: [WM1AD, week-4]
---
## The idea
There are two kinds of DC motor question. They use exactly the same equations, run in opposite directions:

| | **Performance analysis** | **Selection (verification)** |
|---|---|---|
| The question | "What does *this* motor actually do?" | "Does *this datasheet motor* meet the robot's needs?" |
| You're given | Measured V, I, $R_a$, $K_t$, the gearbox and wheel | The requirement (e.g. 20 km/h) and the datasheet (e.g. $P_{rated}$) |
| You find | Torque, speed, power, efficiency, robot speed | Whether $P_{out} \le P_{rated}$, and by how much |
| Used for | An existing robot: testing, benchmarking, fault-finding | A new design: choosing parts |

## The calculation chain
Start from the steady-state model in [[Electric motors and DC motor types]] and work along:

$$V_R = I_aR_a \;\to\; E_b = V - V_R \;\to\; \omega = \frac{E_b}{K_e} \;\to\; n = \frac{60\,\omega}{2\pi} \;\to\; T = K_tI_a$$

$$P_{out} = T\omega \qquad P_{in} = VI_a \qquad P_{Cu} = I_a^2R_a \qquad \eta = \frac{P_{out}}{P_{in}} \times 100\%$$

**Check:** in this model copper is the only loss, so $P_{in} - P_{out} - P_{Cu} = 0$. If it isn't, there's a slip somewhere.

**Then the robot side**, through a gearbox of ratio G:1 and a wheel of radius r:

$$n_{wheel} = \frac{n}{G} \;\to\; \omega_{wheel} = \frac{2\pi\,n_{wheel}}{60} \;\to\; v = \omega_{wheel}\,r \;\to\; v_{km/h} = 3.6\,v \qquad T_{wheel} = T\,G$$

($T_{wheel} = TG$ assumes an ideal gearbox; a real one gives $TG\eta_g$.)

## Worked example: performance analysis
A robot's PMDC drive motor is measured on the bench: 36 V supply, $R_a = 0.8$ Ω, $I_a = 6$ A, $K_t = 0.12$ N·m/A. It drives a 0.09 m radius wheel through a 4:1 gearbox. How fast does the robot go, and how much torque reaches the wheel?

> [!example]- Answer
> $V_R = 6 \times 0.8 = 4.8$ V → $E_b = 36 - 4.8 = 31.2$ V
> $\omega = 31.2/0.12 = 260$ rad/s → $n = 260 \times 60/2\pi = 2483$ rpm
> $T = 0.12 \times 6 = 0.72$ N·m
> $P_{out} = 0.72 \times 260 = 187.2$ W · $P_{in} = 36 \times 6 = 216$ W · $P_{Cu} = 6^2 \times 0.8 = 28.8$ W
> $\eta = 187.2/216 = $ **86.7%** · check: $216 - 187.2 - 28.8 = 0$ ✓
> Wheel: $2483/4 = 620.7$ rpm → $\omega_w = 65.0$ rad/s → $v = 65.0 \times 0.09 = 5.85$ m/s = **21.1 km/h**
> **Wheel torque $= 0.72 \times 4 = 2.88$ N·m**

## Worked example: selection
A datasheet motor is rated at **250 W**, with 48 V, $R_a = 0.6$ Ω, $I_a = 5$ A and $K_t = 0.12$. It drives a 0.1 m wheel through a 6:1 gearbox. The robot must reach **20 km/h**. Is the motor suitable?

> [!example]- Answer
> $E_b = 48 - 5 \times 0.6 = 45$ V → $\omega = 45/0.12 = 375$ rad/s → $n = 3581$ rpm
> $T = 0.12 \times 5 = 0.6$ N·m → $P_{out} = 0.6 \times 375 = 225$ W · $P_{in} = 240$ W → $\eta = 93.8\%$
> **Power utilisation** $= 225/250 = 90\%$ · **power reserve** $= 250 - 225 = 25$ W
> Wheel: $3581/6 = 597$ rpm → $v = 6.25$ m/s = **22.5 km/h ✓** (meets 20 km/h)
> **Verdict:** it meets the speed, but at 90% utilisation there's only 25 W of headroom. A slope, an extra payload or a hot day would push it past its rating. Suitable on paper; a cautious designer would pick the next size up.

## The ideas behind the numbers
**$K_t = K_e$ in SI units.** It's one number describing the same magnetic coupling from both sides: torque per amp, and volts generated per rad/s. If a datasheet gives $K_e$ in V/krpm, convert it to V/(rad/s) first.

**The $K_t$ trade-off:**
- **Higher $K_t$:** more torque per amp, but a lower top speed, because the back-EMF reaches the supply voltage sooner.
- **Lower $K_t$:** faster, but weaker.

| Application | Typical $K_t$ (N·m/A) |
|---|---|
| Mini line-follower | 0.01–0.03 |
| Educational robot | 0.03–0.06 |
| Mobile robot (20–100 W) | 0.05–0.12 |
| AGV (100–500 W) | 0.10–0.30 |
| Robot arm joint | 0.20–0.80 |
| Collaborative robot joint | 0.30–1.50 |

**The gearbox trades speed for torque.** A G:1 reduction divides speed by G and multiplies torque by G, so a fast, weak motor becomes a slow, strong wheel. That's why nearly every robot drive is geared. **But a gearbox can't create power**: $P = T\omega$ is the same on both sides (minus the gearbox's losses).

**Utilisation is not efficiency.**
- **Efficiency** is how much of the input becomes useful output. It decides **battery life**.
- **Utilisation** is how close the motor runs to its **rated limit**. It decides **how much margin** you have. Somewhere around 70–85% leaves room for slopes, payload and temperature.

### Worked example: when gearing can't save you
The customer now wants the selection motor above to deliver **5 N·m at the wheel** *and* still reach 20 km/h. Can a different gear ratio, or more current, do it?

> [!example]- Answer
> **Change the gearing:** $G = 5/0.6 = 8.33$. The torque is there, but the speed drops to $22.5 \times 6/8.33 = 16.2$ km/h. **Fails the speed.**
> **Push more current at G = 6:** $I = 5/(0.12 \times 6) = 6.94$ A → $E_b = 43.8$ V → $\omega = 365$ rad/s → $T = 0.833$ N·m → $P_{out} = 304$ W, which is **122% of rating**. **Overloads the motor.**
> **Why neither works:** 5 N·m at 20 km/h on a 0.1 m wheel needs $5 \times (5.56/0.1) = 278$ W at the wheel, which is more than the motor's 250 W. The answer is a **bigger motor**, plus a margin.

## Common mistakes
- **Forgetting the $I_aR_a$ drop** and using $\omega = V/K_e$ (that's only the no-load speed).
- **Comparing $P_{in}$ with the rating** instead of $P_{out}$.
- **rpm and rad/s:** $P = T\omega$ needs rad/s. **m/s and km/h:** × 3.6.
- **Dividing torque by G** instead of multiplying. A reduction gearbox *increases* torque.

## Check yourself
> [!question]- 1. A 12 V motor has $R_a = 2$ Ω and $K_t = K_e = 0.02$. At 1 A, find its speed in rpm, its output power and its efficiency.
> $E_b = 12 - 2 = 10$ V → $\omega = 500$ rad/s = **4775 rpm** · $T = 0.02$ N·m → $P_{out} = $ **10 W** · $P_{in} = 12$ W → $\eta = $ **83%**.

> [!question]- 2. Two motors both meet a speed target. One runs at 95% utilisation, the other at 70%. Which do you choose?
> The **70%** one: it has margin for extra load, slopes and heat. The 95% one is at its limit and would overheat with any extra demand. (The only argument for it is size, weight or cost.)

> [!question]- 3. Why is a robot drive almost always geared?
> Small DC motors are most efficient at high speed and low torque, but wheels need low speed and high torque. A reduction gearbox converts one into the other, at the same power.

Next: motors that move in exact steps, in [[Stepper motors]].
