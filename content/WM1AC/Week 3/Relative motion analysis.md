---
title: Relative motion analysis
tags: [WM1AC, week-3]
---
## The idea
For a body in **general plane motion** (like a connecting rod), the motion of any point B equals the motion of another point A **plus** the motion caused by the body rotating about A. You don't need a position equation; you work directly with vectors at the instant you care about.

## The equations
$$\mathbf v_B = \mathbf v_A + \boldsymbol\omega \times \mathbf r_{B/A}$$
$$\mathbf a_B = \mathbf a_A + \boldsymbol\alpha \times \mathbf r_{B/A} - \omega^2\,\mathbf r_{B/A}$$

- $\mathbf r_{B/A}$ is the vector **from A to B**.
- For flat motion, $\boldsymbol\omega = \omega\mathbf k$ and $\boldsymbol\alpha = \alpha\mathbf k$ (anticlockwise positive).
- Handy: $\mathbf k \times \mathbf i = \mathbf j$ and $\mathbf k \times \mathbf j = -\mathbf i$.
- The $-\omega^2\mathbf r_{B/A}$ term is the normal (centripetal) part; $\boldsymbol\alpha \times \mathbf r_{B/A}$ is the tangential part.

## The method
1. Pick A as a point whose motion you know (e.g. a pin on a crank, or a slider).
2. Write $\mathbf r_{B/A}$ in components.
3. Write what you know about $\mathbf v_B$'s **direction** (e.g. a slider can only move along its guide).
4. Expand, then match the $\mathbf i$ and $\mathbf j$ components: two equations, two unknowns.
5. Repeat for acceleration, using the ω you just found.

## Worked example
A 0.5 m rod AB has end A sliding along the floor to the right at 2 m/s (constant) and end B sliding down a vertical wall. The rod is at 60° to the floor. Find the rod's ω and α, and B's velocity and acceleration.

> [!example]- Answer
> $\mathbf r_{B/A} = -0.5\cos60°\,\mathbf i + 0.5\sin60°\,\mathbf j = -0.25\mathbf i + 0.433\mathbf j$
> **Velocity:** $v_B\mathbf j = 2\mathbf i + \omega\mathbf k \times(-0.25\mathbf i + 0.433\mathbf j) = 2\mathbf i - 0.433\omega\,\mathbf i - 0.25\omega\,\mathbf j$
> $\mathbf i$: $0 = 2 - 0.433\omega$ → $\omega = 4.62$ rad/s (anticlockwise)
> $\mathbf j$: $v_B = -0.25 \times 4.62 = -1.15$ m/s (moving down)
> **Acceleration** ($\mathbf a_A = 0$, $\omega^2 = 21.3$):
> $a_B\mathbf j = \alpha\mathbf k \times \mathbf r_{B/A} - 21.3(-0.25\mathbf i + 0.433\mathbf j)$
> $\mathbf i$: $0 = -0.433\alpha + 5.33$ → $\alpha = 12.3$ rad/s²
> $\mathbf j$: $a_B = -0.25 \times 12.3 - 21.3 \times 0.433 = -12.3$ m/s²
> Check with [[Implicit differentiation]]: $x^2 + y^2 = 0.25$ gives $\dot y = -x\dot x/y = -0.25 \times 2/0.433 = -1.15$ m/s ✓

## Common mistakes
- Using $\mathbf r_{A/B}$ instead of $\mathbf r_{B/A}$, which flips every sign.
- Getting the cross products wrong: $\mathbf k \times \mathbf j = -\mathbf i$.
- Forgetting the $-\omega^2\mathbf r$ term in the acceleration.

## Check yourself
> [!question]- 1. In the example, why is B's acceleration non-zero even though A moves at constant speed?
> The rod's angle keeps changing, so ω changes (α ≠ 0) and there's a centripetal term. B's motion is constrained to the wall, so it speeds up as it falls.

## Next
Put it all together in the [[Slider-crank worked example]]: a test-style question with a speeding-up crank and a horizontal slider.
