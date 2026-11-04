---
title: WM199 practice questions
tags: [WM199, practice]
---
Short-answer questions on the professional topics. Answer in a few sentences, then compare with the model answer. There's usually more than one good answer.

**1.** Split this into hazard, hazardous situation, hazardous event and harm: *"A cleaner was hit by a delivery robot that reversed out of a lift."*
> [!example]- Answer
> Hazard: a moving robot (its mass and motion) · Situation: the cleaner standing behind it at the lift · Event: the robot reverses without detecting them · Harm: impact injury.

**2.** A risk scores likelihood 2 × severity 5 = 10. What band is it in, and what should happen?
> [!example]- Answer
> High (10–16): act urgently. Start at the top of the hierarchy, e.g. engineer out the reversing hazard (rear sensing, crawl-speed reversing), before relying on signs or training.

**3.** Rewrite as a SMART goal: *"I want to get better at presenting."*
> [!example]- Answer
> "Give a five-minute talk at each of the next three society meetings this term, ask two people for one piece of feedback each time, and record one change I make for the next talk."

**4.** Which UK-SPEC area does each of these provide evidence for? (a) leading a lab group (b) a CPD log (c) explaining a design to a client
> [!example]- Answer
> (a) C, responsibility, management and leadership · (b) E, professional commitment · (c) D, communication

**5.** A manager tells you to ship a robot with a known 1-in-500 failure that could injure someone, and to "patch it later". What do you do, and which principle applies?
> [!example]- Answer
> Raise it in writing with the evidence and the risk in numbers (at 300 uses a day, about one failure every two days), recommend not shipping until it's fixed or controlled, and escalate if overruled. Principles: responsibility to society, honesty and integrity. Whistleblowing is protected by the Public Interest Disclosure Act 1998.

**6.** Give one environmental, one social and one economic question you'd ask about a robot's battery.
> [!example]- Answer
> Environmental: can the cells be recycled at end of life? · Social: were the materials mined under safe, fair conditions? · Economic: what's the lifecycle cost, including replacement packs?

**7.** Is "the robot shall stop quickly when it detects a person" a good safety requirement? Rewrite it.
> [!example]- Answer
> No, "quickly" isn't testable. Better: "The robot shall come to a complete stop within 1.0 m of detecting a person in its path at its maximum speed of 1.5 m/s."

**8.** Why is a light curtain better than a warning sign?
> [!example]- Answer
> A light curtain is an active engineering control that stops the machine without anyone having to notice or obey anything. A sign is procedural and depends on people behaving correctly, so it's the least reliable kind of barrier.

## Week 4: systems
**9.** A delivery robot is late every lunchtime. Give an example at each level of the iceberg model.
> [!example]- Answer
> Event: today's delivery was late · pattern: late every lunchtime · structure: one lift shared with the lunchtime crowd, and requests bunching at 12:00 · mental model: "deliveries should happen whenever someone asks". The structure and mental model are where a lasting fix lies.

**10.** Is this loop balancing or reinforcing? *Queue of requests → robots dispatched → queue shrinks.*
> [!example]- Answer
> Queue → dispatched is **+**, dispatched → queue is **−**. One minus sign, so it's **balancing**: the fleet works to keep the queue short.

**11.** Architecture or design? (a) an independent safety controller that can always stop the robot (b) the choice of lidar supplier (c) whether the robot uses lifts or stays on one floor
> [!example]- Answer
> (a) architecture · (b) design · (c) architecture

**12.** In an allocation audit, "detect a stair edge" has no part allocated to it. Why does that matter, and what would you do?
> [!example]- Answer
> It's a capability gap, and a safety-critical one: the robot could drive off a step. Allocate it to a part (downward-facing cliff sensors), ideally with redundancy (two different sensing methods), and trace it back to a testable safety requirement.

