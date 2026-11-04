---
title: WM1AC practice questions
tags: [WM1AC, practice]
---
Test-style questions covering Weeks 1–4, with my own numbers. Try each one before opening the answer. Use radians unless the question says otherwise.

> [!tip] Before you start
> Decide first: differentiate, integrate, or constant-acceleration equations? (See the table in [[Calculus for kinematics]].)

## Maths
**1.** $\mathbf a = 3\mathbf i - 2\mathbf j + \mathbf k$ and $\mathbf b = \mathbf i + 4\mathbf j - 2\mathbf k$. Find $\mathbf a \cdot \mathbf b$, the angle between them, and $\mathbf a \times \mathbf b$.
> [!example]- Answer
> $\mathbf a \cdot \mathbf b = 3 - 8 - 2 = -7$ · $\cos\theta = -7/(\sqrt{14}\sqrt{21})$ → $\theta = 114°$
> $\mathbf a \times \mathbf b = (4 - 4)\mathbf i - (-6 - 1)\mathbf j + (12 + 2)\mathbf k = 7\mathbf j + 14\mathbf k$

**2.** A 40 N force acts along +z at the point $(0.2, 0.1, 0)$ m. Find its moment about the origin.
> [!example]- Answer
> $\mathbf M = \mathbf r \times \mathbf F = (0.1 \times 40)\mathbf i - (0.2 \times 40)\mathbf j = 4\mathbf i - 8\mathbf j$ N m

## Particles
**3.** A slider's position is $s = 4t^3 - 6t^2 + 1$ m. Find its velocity and acceleration at $t = 2$ s, and when it's momentarily at rest.
> [!example]- Answer
> $v = 12t^2 - 12t$ → $v(2) = 24$ m/s · $a = 24t - 12$ → $a(2) = 36$ m/s²
> $v = 12t(t - 1) = 0$ at **t = 0 and t = 1 s**

**4.** A cart speeds up uniformly from 2 m/s to 8 m/s over 15 m. Find its acceleration and how long it takes.
> [!example]- Answer
> $64 = 4 + 2a(15)$ → $a = 2$ m/s² · $t = (8 - 2)/2 = 3$ s

**5.** A particle has $a = 2t$ m/s², starting at $v = 1$ m/s and $s = 0$. Find $v$ and $s$ at $t = 3$ s.
> [!example]- Answer
> $v = 1 + t^2 = 10$ m/s · $s = t + t^3/3 = 3 + 9 = 12$ m

**6.** A wheel of radius 0.15 m starts from rest with $\alpha = 4$ rad/s². After 2 s, find the speed and total acceleration of a point on its rim.
> [!example]- Answer
> $\omega = 8$ rad/s · $v = 1.2$ m/s · $a_t = 0.6$, $a_n = 64 \times 0.15 = 9.6$ m/s² · $a = 9.62$ m/s²

## Rigid bodies and mechanisms
**7.** A motor at 1200 rpm brakes uniformly to rest in 5 s. Find α and the number of revolutions it makes while stopping.
> [!example]- Answer
> $\omega_0 = 125.7$ rad/s · $\alpha = -25.1$ rad/s² · $\theta = \tfrac12 \times 125.7 \times 5 = 314$ rad $= 50$ rev

**8.** A motor at 3000 rpm has a 12 mm (radius) pinion driving a 60 mm gear. A 40 mm pulley on the same shaft drives a 100 mm pulley by belt. Find the output speed.
> [!example]- Answer
> Gear: $3000 \times 12/60 = 600$ rpm · Belt: $600 \times 40/100 = $ **240 rpm**

**9.** A hydraulic cylinder forms the third side of a triangle whose other two sides are fixed at 1.2 m and 0.8 m. The angle between them is 60° and opening at 0.5 rad/s. Find the cylinder's length and how fast it's extending.
> [!example]- Answer
> $s^2 = 1.44 + 0.64 - 1.92\cos60° = 1.12$ → $s = 1.06$ m
> $2s\dot s = 2(1.2)(0.8)\sin\theta\,\dot\theta$ → $\dot s = \dfrac{0.96 \times 0.866 \times 0.5}{1.06} = 0.393$ m/s

**10.** A slider-crank has crank $OA = 0.15$ m turning at 10 rad/s anticlockwise and rod $AB = 0.4$ m, with slider B on the horizontal line through O. At the instant the crank is vertical (A directly above O), find the rod's angular velocity and B's velocity.
> [!example]- Answer
> $\mathbf v_A = \boldsymbol\omega \times \mathbf r_{A/O} = 10\mathbf k \times 0.15\mathbf j = -1.5\mathbf i$ m/s
> $\mathbf r_{B/A} = 0.371\mathbf i - 0.15\mathbf j$ · $v_B\mathbf i = -1.5\mathbf i + \omega_{AB}(0.15\mathbf i + 0.371\mathbf j)$
> $\mathbf j$: $0 = 0.371\,\omega_{AB}$ → $\omega_{AB} = 0$ · $\mathbf i$: $v_B = -1.5$ m/s
> At this instant the rod is only translating, so B moves at A's speed, 1.5 m/s to the left.

## Short written answers
**11.** Give one example each of translation, fixed-axis rotation and general plane motion in a slider-crank.
> [!example]- Answer
> Slider: translation · crank: fixed-axis rotation · connecting rod: general plane motion.

**12.** Why do two meshing gears share a tangential velocity but not an angular velocity?
> [!example]- Answer
> Their teeth move together at the contact point, so the rim speeds $r\omega$ are equal. Different radii then need different ω.

## Week 4: statics and kinetics
**13.** A 60 N force acts at the end of a 0.5 m horizontal bar pinned at O, pointing up and away from O at 25° above the horizontal. Find its moment about O.
> [!example]- Answer
> Only the vertical component has a moment arm (the horizontal one acts along the bar, through O).
> $M_O = 60\sin25° \times 0.5 = 25.4 \times 0.5 = $ **12.7 N·m anticlockwise**

**14.** A 3 m beam is pinned at A (its left end) and rests on a roller at B, 2.5 m from A. It carries 400 N at 1 m from A and 200 N at the free end (3 m from A). Find the reactions.
> [!example]- Answer
> $\sum M_A = 0$: $B(2.5) = 400(1) + 200(3) = 1000$ → **$B = 400$ N ↑**
> $\sum F_y = 0$: $A_y = 600 - 400 = $ **200 N ↑** · $A_x = 0$
> See [[Static equilibrium and free body diagrams]].

**15.** An 8 kg box sits on a 30° ramp with $\mu_s = 0.65$. Does it slide? What friction force acts?
> [!example]- Answer
> $\tan30° = 0.577 < 0.65$, so **it stays put**.
> Friction is only as big as needed: $F = mg\sin30° = $ **39.2 N** (below the limit $\mu_sN = 0.65 \times 68.0 = 44.2$ N).

**16.** A 25 kg robot must accelerate at 1.5 m/s² on a flat floor with $C_{rr} = 0.02$. What total driving force do its wheels need?
> [!example]- Answer
> $F = ma + C_{rr}mg = 37.5 + 4.9 = $ **42.4 N**

**17.** A 6 kg block on a table ($\mu_k = 0.2$) is pulled by a rope over a smooth pulley by a hanging 5 kg mass. Find the acceleration and the tension.
> [!example]- Answer
> Hanging: $5g - T = 5a$ · block: $T - 0.2(6g) = 6a$. Adding: $5g - 1.2g = 11a$ → **$a = 3.39$ m/s²**
> $T = 5(9.81 - 3.39) = $ **32.1 N**

**18.** A T-shaped section has a 120 × 20 mm flange on top of a 20 × 80 mm web (total height 100 mm), centred. Find $\bar y$ from the bottom.
> [!example]- Answer
> Flange: 2400 mm² at y = 90 · web: 1600 mm² at y = 40
> $\bar y = (2400 \times 90 + 1600 \times 40)/4000 = $ **70 mm** (and $\bar x$ is on the centreline by symmetry)

**19.** What's a two-force member, and why does it make an equilibrium problem easier?
> [!example]- Answer
> A link pinned at both ends with no load in between. It can only carry force along its length (tension or compression), so its unknown force has a known direction: one unknown instead of two.

**20.** Why does a slider-crank need more torque to start than to keep running?
> [!example]- Answer
> Static friction exceeds kinetic friction; the motor must accelerate all the moving masses from rest ($\sum F = ma$, $\sum M = I\alpha$); and near dead centre the crank has very little leverage on the rod.

