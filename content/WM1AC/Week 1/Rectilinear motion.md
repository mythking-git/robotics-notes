---
title: Rectilinear motion
tags: [WM1AC, week-1]
---
## The idea
The simplest motion: a particle moving along a straight line. Everything is one-dimensional, so position, velocity and acceleration are just numbers with signs. It's the template for everything that follows, from curves to rotating bodies.

## The definitions
| Quantity | Definition | Note |
|---|---|---|
| Position $s$ | Distance from a fixed origin, with a sign | |
| Displacement $\Delta s$ | Change in position | Not the same as distance travelled |
| Velocity $v$ | $v = \dfrac{ds}{dt}$ | Its sign shows direction |
| Acceleration $a$ | $a = \dfrac{dv}{dt}$ | Negative $a$ isn't always "slowing down": it depends on the sign of $v$ |

**Distance vs displacement:** if something goes forward 5 m and back 1 m, the displacement is 4 m but the distance travelled is 6 m. Find where $v = 0$ (where it turns round) and add up each leg.

## Constant acceleration
Only when $a$ is **constant**:

$$v = v_0 + at \qquad s = s_0 + v_0t + \tfrac12at^2 \qquad v^2 = v_0^2 + 2a(s - s_0)$$

If $a$ changes with time, integrate instead (see [[Calculus for kinematics]]).

## Worked examples
**1.** A delivery robot speeds up from 0.5 m/s at a constant 0.8 m/s² for 3 s. Final speed and distance?

> [!example]- Answer
> $v = 0.5 + 0.8 \times 3 = 2.9$ m/s
> $s = 0.5 \times 3 + \tfrac12 \times 0.8 \times 3^2 = 1.5 + 3.6 = 5.1$ m
> Check: $v^2 = 0.25 + 2 \times 0.8 \times 5.1 = 8.41$ → $v = 2.9$ ✓

**2.** A slider's position is $s = 2t^3 - 9t^2 + 12t$ m. When does it stop, and how far does it travel in the first 3 s?

> [!example]- Answer
> $v = 6t^2 - 18t + 12 = 6(t - 1)(t - 2)$, so it stops at **t = 1 s and t = 2 s**.
> $a = 12t - 18$, which is zero at 1.5 s.
> $s(0) = 0$, $s(1) = 5$, $s(2) = 4$, $s(3) = 9$ m.
> Distance $= 5 + 1 + 5 = $ **11 m**, but the displacement is only 9 m.

## Common mistakes
- Using the constant-acceleration equations when $a$ depends on $t$.
- Giving displacement when the question asks for distance.
- Dropping signs: pick a positive direction and stick to it.

## Check yourself
> [!question]- 1. A cart moving at 3 m/s brakes at a constant 1.5 m/s². Stopping distance?
> $0 = 9 - 2(1.5)s$ → $s = 3$ m.
