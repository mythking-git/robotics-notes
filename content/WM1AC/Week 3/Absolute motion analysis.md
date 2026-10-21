---
title: Absolute motion analysis
tags: [WM1AC, week-3]
---
## The idea
For a mechanism like a slider-crank, write **one equation for the position** of the part you care about in terms of the input angle. Then [[Implicit differentiation|differentiate it with respect to time]] once for velocity and again for acceleration. It's called "absolute" because every position is measured from a fixed origin.

## The method
1. **Geometry:** write the position (e.g. the slider's $x$) in terms of the crank angle $\theta$, using trig or the cosine rule.
2. **Differentiate** with respect to time → velocity. Every $\theta$ term picks up a $\dot\theta = \omega$.
3. **Differentiate again** (product rule) → acceleration, with $\ddot\theta = \alpha$.
4. **Substitute** the values at the instant asked for, and check the signs make sense physically.

## Worked example: a Scotch yoke
A crank of radius $r = 0.1$ m drives a slotted yoke, whose position is $x = r\cos\theta$. The crank turns at a constant 20 rad/s. Find the yoke's velocity and acceleration at $\theta = 30°$.

> [!example]- Answer
> $x = 0.1\cos\theta$
> $\dot x = -0.1\sin\theta\,\dot\theta$ → at 30°: $-0.1 \times 0.5 \times 20 = $ **−1.0 m/s** (moving towards −x)
> $\ddot x = -0.1\cos\theta\,\dot\theta^2 - 0.1\sin\theta\,\ddot\theta$. Constant ω means $\ddot\theta = 0$:
> $\ddot x = -0.1 \times 0.866 \times 400 = $ **−34.6 m/s²**

The yoke moves in **simple harmonic motion**, which is why this mechanism is used in some pumps and shakers.

## When the geometry is a triangle
For a hydraulic cylinder pushing a link, the cylinder length $s$ and the link angle are tied by the cosine rule:
$$s^2 = a^2 + b^2 - 2ab\cos\theta \;\Rightarrow\; 2s\dot s = 2ab\sin\theta\,\dot\theta$$
Given the cylinder's extension rate $\dot s$, solve for $\dot\theta$. Differentiate again for $\ddot\theta$, remembering that a constant rate means $\ddot s = 0$, not $\dot s = 0$.

## Common mistakes
- Plugging in numbers before differentiating.
- Losing the second term of the product rule on the second derivative.
- Sign of the velocity: decide which way is positive and check your answer agrees with the picture.

## Check yourself
> [!question]- 1. Same Scotch yoke, but at θ = 90°. Velocity and acceleration?
> $\dot x = -0.1 \times 1 \times 20 = -2$ m/s (its fastest), $\ddot x = 0$ (cos 90° = 0).
