---
title: WM1AD practice questions
tags: [WM1AD, practice]
---
Test-style questions covering Weeks 1–4, with my own numbers. Try each one on paper with a calculator before opening the answer. Answers are rounded to 3 significant figures.

> [!tip] How to use this page
> Time yourself: test questions are usually 5–10 minutes each. Write units on every line, and finish circuit questions with a power balance.

## Week 1
**1.** A 48 V robot drive motor is rated at 360 W. Find the current, the winding resistance as seen from the supply, and the energy used in 15 minutes in kWh.
> [!example]- Answer
> $I = P/V = 360/48 = 7.5$ A · $R = V/I = 48/7.5 = 6.4\ \Omega$ · $E = 0.36\ \text{kW} \times 0.25\ \text{h} = 0.09$ kWh

**2.** A battery feeds a DC-DC converter (94%), a motor drive (96%) and a motor (88%). The motor delivers 200 W. What power does the battery supply, and how much is lost?
> [!example]- Answer
> $\eta = 0.94 \times 0.96 \times 0.88 = 0.794$ · $P_{in} = 200/0.794 = 252$ W · losses $= 51.9$ W

**3.** A 24 V supply feeds $R_1 = 3\ \Omega$, then $12\ \Omega$ and $6\ \Omega$ in parallel, then $R_4 = 5\ \Omega$, all in series. Find every current and check the power balance.
> [!example]- Answer
> Parallel pair: $12 \times 6/18 = 4\ \Omega$ · $R_T = 3 + 4 + 5 = 12\ \Omega$ · $I = 2$ A
> Parallel voltage $= 2 \times 4 = 8$ V → $I_{12} = 0.667$ A, $I_6 = 1.33$ A (sum 2 ✓)
> Powers: $12 + 5.33 + 10.7 + 20 = 48$ W $= 24 \times 2$ ✓

**4.** A Wheatstone bridge has $R_1 = 470\ \Omega$, $R_2 = 1$ kΩ and $R_3 = 2.2$ kΩ. What value of $R_4$ balances it?
> [!example]- Answer
> $R_4 = R_2R_3/R_1 = 1000 \times 2200/470 = 4.68$ kΩ

**5.** A 10 kΩ NTC thermistor has $B = 3435$ K. What's its resistance at 60 °C?
> [!example]- Answer
> $T = 333.15$ K · $R = 10\,000\exp[3435(1/333.15 - 1/298.15)] = 2.98$ kΩ

## Week 2
**6.** Find $\det\begin{bmatrix} 2 & -1 & 3 \\ 1 & 4 & 0 \\ -2 & 5 & 1 \end{bmatrix}$.
> [!example]- Answer
> Along row 1: $2(4 - 0) + 1(1 - 0) + 3(5 + 8) = 8 + 1 + 39 = $ **48**

**7.** A three-mesh circuit (like the one in [[Mesh analysis]]) has $V_1 = 30$ V, $V_2 = 10$ V, $R_1 = 2$, $R_2 = 5$, $R_3 = 4$, $R_4 = 6$, $R_5 = 3\ \Omega$. Write the matrix, find the mesh currents and the current in each shared branch, and check the power balance.
> [!example]- Answer
> $\begin{bmatrix} 7 & -5 & 0 \\ -5 & 15 & -6 \\ 0 & -6 & 9 \end{bmatrix}\begin{bmatrix} I_1 \\ I_2 \\ I_3 \end{bmatrix} = \begin{bmatrix} 30 \\ 0 \\ 10 \end{bmatrix}$, $\Delta = 468$
> $I_1 = 6.99$ A, $I_2 = 3.78$ A, $I_3 = 3.63$ A · $I_{R2} = 3.21$ A, $I_{R4} = 0.150$ A
> Power: $\sum I^2R = 246$ W $= 30 \times 6.99 + 10 \times 3.63$ ✓

**8.** A 5 V supply charges a 470 µF capacitor through 1 kΩ. Find τ, the time to reach 4 V, and the energy stored when it's full.
> [!example]- Answer
> $\tau = 0.47$ s · $4 = 5(1 - e^{-t/0.47})$ → $t = 0.47\ln 5 = 0.756$ s · $E = \tfrac12 \times 470\times10^{-6} \times 25 = 5.88$ mJ

## Week 3
**9.** A bridge rectifier ($V_F = 0.95$ V) on 230 V mains carries 3 A RMS into a 6800 µF capacitor. Find the bridge loss, the capacitor's peak voltage and the ripple.
> [!example]- Answer
> $P = 1.8 \times 0.95 \times 3 = 5.13$ W · $V_{C,max} = 325.3 - 1.9 = 323$ V · $\Delta V = 3/(100 \times 0.0068) = 4.41$ V

**10.** An IRFP250 ($R_{DS(on)} = 0.075\ \Omega$; 14 + 43 ns on, 41 + 33 ns off) switches 36 V at 15 A, 50 kHz. Total loss?
> [!example]- Answer
> $P_{cond} = 0.075 \times 225 = 16.9$ W · $E_{ON} = 270 \times 57\times10^{-9} = 15.4\ \mu$J · $E_{OFF} = 270 \times 74\times10^{-9} = 20.0\ \mu$J
> $P_{SW} = 35.4\times10^{-6} \times 50\,000 = 1.77$ W · **$P_{MOSFET} = 18.6$ W**

**11.** The MOSFET in Q10 sits on a 3 °C/W heatsink ($R_{th1} = 0.7$, $R_{th2} = 0.24$ °C/W) at 35 °C ambient. Find $T_J$ and the safety margin. What heatsink would hold it at 100 °C?
> [!example]- Answer
> $T_J = 35 + 18.6 \times (0.7 + 0.24 + 3) = 108$ °C · margin $= 100 - 108/175 \times 100 = 38\%$ ✓
> For 100 °C: $R_{th3} = 65/18.6 - 0.94 = 2.55$ °C/W

**12.** A buck converter steps 36 V down to 12 V at 3 A, switching at 200 kHz, with 20% current and voltage ripple. Find D, L and C.
> [!example]- Answer
> $D = 1/3$ · $\Delta I = 0.6$ A, $\Delta V = 2.4$ V
> $L = 12 \times (2/3)/(200\,000 \times 0.6) = 66.7\ \mu$H · $C \ge 0.6/(8 \times 200\,000 \times 2.4) = 0.156\ \mu$F

**13.** A 12 V motor runs from a 24 V battery using PWM. What duty cycle gives it its rated average voltage?
> [!example]- Answer
> $D = 12/24 = 50\%$

## Short written answers
**14.** Why would you choose a MOSFET over an IGBT for a 48 V robot drive? (2–3 sentences)
> [!example]- Answer
> At 48 V a MOSFET has low on-resistance and switches much faster than an IGBT, so it has lower total loss and allows higher PWM frequencies with smaller filter parts. IGBTs only make sense above roughly 700–1000 V.

**15.** Explain why switching loss becomes important in DC-DC converters.
> [!example]- Answer
> Switching loss is proportional to frequency. Converters run at 100+ kHz to keep the inductor and capacitor small, so energy lost in each transition happens hundreds of thousands of times a second, and it can match or exceed conduction loss.

## Week 4: motors
**16.** A 24 V PMDC motor has $R_a = 1$ Ω and $K_t = K_e = 0.05$. At 3 A, find its speed, torque, output power and efficiency.
> [!example]- Answer
> $E_b = 24 - 3 = 21$ V → $\omega = 21/0.05 = 420$ rad/s = **4010 rpm**
> $T = 0.05 \times 3 = $ **0.15 N·m** · $P_{out} = 0.15 \times 420 = $ **63 W** · $P_{in} = 72$ W → **$\eta = 87.5\%$**

**17.** The same motor jams. What current flows, and how much heat is generated in the winding?
> [!example]- Answer
> No back-EMF: $I = 24/1 = $ **24 A** (8× the running current) · $P = 24^2 \times 1 = $ **576 W**, all heat. The driver must limit current or cut out.

**18.** A motor runs at 3000 rpm through an 8:1 gearbox to a 0.06 m radius wheel. How fast does the robot travel?
> [!example]- Answer
> Wheel $= 375$ rpm → $\omega_w = 39.3$ rad/s → $v = 39.3 \times 0.06 = 2.36$ m/s = **8.48 km/h**

**19.** A motor rated at 100 W delivers 85 W in operation. Find its power utilisation and reserve. Is that a good choice?
> [!example]- Answer
> Utilisation **85%**, reserve **15 W**. It works, with a modest margin for slopes and payload; any more than about 90% would leave very little headroom.

**20.** A 1.8° stepper with 1/8 microstepping runs at 300 rpm through a 3:1 gearbox, with $T_h = 0.4$ N·m. Find $f_{step}$, $f_{\mu step}$, the output speed and the output torque.
> [!example]- Answer
> $f_{step} = 200 \times 300/60 = $ **1000 Hz** · $f_{\mu step} = $ **8 kHz** · $n_{out} = $ **100 rpm** · $T_{out} = 0.4 \times 3 = $ **1.2 N·m**

**21.** A 15 kg robot on a flat floor must accelerate at 1 m/s² ($C_{rr} = 0.02$). It has two driven 0.05 m wheels, a 5:1 gearbox at 90% efficiency, and a safety factor of 1.5. What rated torque does each motor need?
> [!example]- Answer
> $F = 15 + 2.94 = 17.9$ N → $T_w = 17.9 \times 0.05/2 = 0.449$ N·m → $T_m = 0.449/(5 \times 0.9) = 0.0997$ N·m → rated **0.15 N·m**. See [[Sizing a drive motor]].

**22.** Why is a series-wound DC motor unsuitable for a mobile robot's wheels?
> [!example]- Answer
> Its speed depends strongly on load, and if the load is lost (a wheel lifts) the weakened field makes it run away to dangerous speeds. A PMDC motor's fixed field gives predictable speed control.

**23.** Give two advantages and two disadvantages of a stepper motor for positioning.
> [!example]- Answer
> **For:** open-loop positioning with no sensor; high holding torque (also: simple step/direction control, no brushes).
> **Against:** missed steps go undetected under overload; torque falls with speed (also: resonance, current drawn even when stationary).

