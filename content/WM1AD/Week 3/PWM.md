---
title: PWM
tags: [WM1AD, week-3]
---
## The idea
A MOSFET is either fully on or fully off. To give a motor *some* of the power, switch it on for part of each cycle, thousands of times a second. The motor is far too slow to notice the flicker, so it responds to the **average voltage**. This is **pulse width modulation (PWM)**.

## The definitions
| Symbol | Meaning |
|---|---|
| $T$ | Period: the time for one on-plus-off cycle, $T = t_{on} + t_{off}$ |
| $F$ | Frequency: cycles per second, $F = 1/T$ |
| $D$ | Duty cycle: fraction of the time it's on, $D = t_{on}/T$, from 0 to 1 |

$$\boxed{V_{avg} = D \times V_{DD}}$$

Why: for a fraction $D$ of the time the motor sees $V_{DD}$, and for the rest it sees 0 V. The average is $D \times V_{DD} + (1-D)\times 0$.

## Worked example
A 24 V battery drives a motor with PWM at 20 kHz and 30% duty. Find $T$, $t_{on}$ and the average voltage.

> [!example]- Answer
> $T = 1/20\,000 = 50$ µs. $t_{on} = 0.3 \times 50 = 15$ µs, so $t_{off} = 35$ µs.
> $V_{avg} = 0.3 \times 24 = 7.2$ V.

## Why the frequency matters
- **Too low** (under ~1 kHz) and you can hear the motor whine, and the current ripples a lot.
- **Higher** frequencies give smoother current and smaller [[DC-DC converters|converter]] parts, but every switch costs energy, so [[MOSFET power loss|switching loss]] rises with frequency.

## Check yourself
> [!question]- 1. What duty cycle gives 9 V from a 12 V supply?
> $D = 9/12 = 0.75$, so 75%.
