---
title: Implicit differentiation
tags: [WM1AC, week-2, maths]
---
## The idea
In a mechanism, the geometry ties positions together, e.g. "these two sides and this angle make a triangle". You often can't rearrange that into $y = f(x)$, and you don't need to. **Differentiate both sides as they stand**, using the chain rule on anything that depends on time. That turns a position equation into a velocity equation in one step.

## The rule
Anything that changes with time gets the chain rule:
$$\frac{d}{dt}\big(x^2\big) = 2x\,\dot x \qquad \frac{d}{dt}\big(\cos\theta\big) = -\sin\theta\,\dot\theta \qquad \frac{d}{dt}\big(s^2\big) = 2s\,\dot s$$
Constants (fixed link lengths) differentiate to zero. Products need the **product rule**, which you'll need again on the second differentiation:
$$\frac{d}{dt}\big(s\,\dot s\big) = \dot s^2 + s\,\ddot s$$

## The recipe for mechanisms
1. Write the **geometry**: Pythagoras, trig, or the cosine rule $c^2 = a^2 + b^2 - 2ab\cos C$.
2. Differentiate with respect to time → **velocities** ($\dot s$, $\dot\theta = \omega$).
3. Differentiate again → **accelerations** ($\ddot s$, $\ddot\theta = \alpha$).
4. Put in the numbers at the instant you care about. Watch the signs: a length that's getting shorter has negative $\dot s$.

## Worked example
A 5 m ladder leans against a wall. Its foot slides away from the wall at 0.5 m/s. How fast is the top sliding down when the foot is 3 m out?

> [!example]- Answer
> Geometry: $x^2 + y^2 = 25$. When $x = 3$, $y = 4$.
> Differentiate: $2x\dot x + 2y\dot y = 0$ → $\dot y = -\dfrac{x\dot x}{y} = -\dfrac{3 \times 0.5}{4} = -0.375$ m/s
> The top slides **down** at 0.375 m/s.

This is exactly the same maths as a robot's linear actuator pushing a link, or the A2 slider-crank.

## Common mistakes
- Forgetting the $\dot x$ (the chain rule part) on each term.
- Substituting numbers *before* differentiating. Differentiate the general equation first.
- Using $\dot s = 0$ when the rate is constant. It's $\ddot s$ that's zero.

## Check yourself
> [!question]- 1. Differentiate $y = 0.2\cos\theta$ with respect to time, twice.
> $\dot y = -0.2\sin\theta\,\dot\theta$, $\ddot y = -0.2\cos\theta\,\dot\theta^2 - 0.2\sin\theta\,\ddot\theta$.
