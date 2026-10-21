---
title: Writing a problem statement
tags: [WM199, week-1]
---
## The idea
Engineers are tempted to jump straight to a solution. A good **problem statement** stops that: it describes **who** has the problem, **what** it is, **why** it matters, and the **constraints**, without saying anything about the answer. If your statement mentions sensors or a robot, it's describing a solution, and you've closed off other options too early.

## Interrogating a brief
Take a vague brief like *"The university wants a robot to move equipment between labs."* Before designing anything, ask:

| Question | Why it matters |
|---|---|
| **Who** sends, receives, uses, shares the space, pays, and fixes it? | Defines the users, and who could be harmed |
| **What** is being moved: weight, size, fragile, hazardous? | Sets the capability and safety needs |
| **When**: working hours or out of hours, scheduled or on demand? | Capacity, and whether help is nearby when things go wrong |
| **Where**: doors, lifts, ramps, outdoor paths, security? | Physical constraints and hazards |
| **How much** to build, run and maintain? | What's realistic |
| **Why bother?** What happens now when things are lost or delayed? | Proves the problem exists and sets a baseline |

## A good problem statement
- Says **who** is affected, including people who aren't users (pedestrians, wheelchair users, cleaners).
- States the **need** and what **success** looks like.
- Names the **constraints**: safety, budget, privacy, responsibility for faults.
- Contains **no solution**.

**Template:** *[Who] need a way to [do what], so that [outcome], without [harm] to [whom], within [constraints].*

> Lab staff need a reliable way to move equipment between campus labs at any time, so that items arrive safely, on time and traceably, without harm to people sharing the routes or to anyone's privacy, within an affordable budget and with clear responsibility for faults.

Problem statements also hide **ethical choices**: "faster deliveries" says nothing about the wheelchair user on the same pavement. See [[Engineering ethics and duty of care]].

## Check yourself
> [!question]- 1. What's wrong with "Design a lidar-equipped robot to deliver parcels quickly"?
> It names a solution (a robot, lidar) and only one measure of success (speed). It says nothing about who's affected, safety or cost.
