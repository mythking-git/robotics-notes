---
title: Calculus for kinematics
tags: [WM1AC, week-1, maths]
---
## The idea
Kinematics is calculus with physical meaning. **Differentiating** position gives velocity, and velocity gives acceleration. **Integrating** goes the other way. Most of the module is choosing which direction to go.

$$v = \frac{ds}{dt} \qquad a = \frac{dv}{dt} = \frac{d^2s}{dt^2} \qquad \text{(a dot means } \tfrac{d}{dt}\text{: } \dot s = v,\ \ddot s = a\text{)}$$

## Differentiation rules
| Rule | Formula | Example |
|---|---|---|
| Power | $\dfrac{d}{dx}x^n = nx^{n-1}$ | $\dfrac{d}{dt}(4t^3) = 12t^2$ |
| Product | $(uv)' = u'v + uv'$ | $\dfrac{d}{dx}(x^2\cos x) = 2x\cos x - x^2\sin x$ |
| Quotient | $\left(\dfrac{u}{v}\right)' = \dfrac{u'v - uv'}{v^2}$ | |
| Chain | $\dfrac{dy}{dx} = \dfrac{dy}{du}\cdot\dfrac{du}{dx}$ | $\dfrac{d}{dx}e^{2x} = 2e^{2x}$ |

## Integration
The reverse of differentiation, and the **area under a curve**.
- **Indefinite** (no limits): always add $+\,c$, then find $c$ from a known condition, like the starting velocity.
- **Definite** (limits): no $c$. $\int_0^2 2x\,dx = [x^2]_0^2 = 4$.

**Separating the differential** is how every kinematics formula is built:
$$v = \frac{ds}{dt} \;\Rightarrow\; ds = v\,dt \;\Rightarrow\; \int_{s_0}^{s} ds = \int_0^t v\,dt$$

Techniques you'll meet: **substitution** ($\int\cos 3x\,dx = \tfrac13\sin 3x + c$), **by parts** ($\int u\,dv = uv - \int v\,du$) and **partial fractions**.

## Worked example
A robot arm joint has angular acceleration $\alpha = 6t$ rad/s², starting at $\omega_0 = 2$ rad/s and $\theta_0 = 0$. Find $\omega$ and $\theta$ at $t = 2$ s.

> [!example]- Answer
> $\omega = \omega_0 + \int_0^t 6t\,dt = 2 + 3t^2$ → $\omega(2) = 14$ rad/s
> $\theta = \int_0^t (2 + 3t^2)\,dt = 2t + t^3$ → $\theta(2) = 12$ rad
> The starting values become the lower limits, so no $+\,c$ is needed.

## Which way to go?
| You're given | Do |
|---|---|
| $s(t)$ or $\theta(t)$ | Differentiate for $v$ and $a$ |
| $a(t)$ or $\alpha(t)$ | Integrate, using the starting values |
| $a$ as a function of position | Use $v\,dv = a\,ds$ (or $\omega\,d\omega = \alpha\,d\theta$) |
| Constant $a$ | Use the constant-acceleration equations ([[Rectilinear motion]]) |

## Check yourself
> [!question]- 1. $s = 5t^2 - 2t$. What's $a$?
> $v = 10t - 2$, so $a = 10$ m/s², constant.

> [!question]- 2. $v = 3t^2$ m/s and $s(0) = 1$ m. Find $s(2)$.
> $s = 1 + t^3$, so $s(2) = 9$ m.
