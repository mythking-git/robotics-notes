---
title: Scientific calculator
tags: [tools]
---
## Which calculator?
The computer-based tests only allow **non-programmable scientific calculators**. The Casio ClassWiz range is the usual choice. Check your module's rules, but the **fx-991** models are the ones worth having, because they do matrices, simultaneous equations and complex numbers. The cheaper fx-83 and fx-85 don't.

There are two generations, with different menus (exact key names can vary slightly between versions, so check against your own):
- **fx-991EX** (older): press **MENU**, then a number or letter for each mode.
- **fx-991CW** (newer): press **HOME** and pick an app with the arrow keys.

## Determinants and matrix maths
Used in [[Matrices and Cramer's rule]] and [[Mesh analysis]].

| Step | fx-991EX | fx-991CW |
|---|---|---|
| Open | MENU → 4 (Matrix) | HOME → Matrix |
| Define a matrix | Choose MatA, set rows and columns, type the values (= after each) | TOOLS → define MatA, set size, type the values |
| Back to calculate | AC | AC |
| Determinant | OPTN → Determinant → OPTN → MatA → ) → = | CATALOG → Matrix → Matrix Calculation → Det → MatA → ) → EXE |
| Inverse | MatA then x⁻¹ | MatA then x⁻¹ |

## Simultaneous equations
The fastest way to solve a 3×3 mesh matrix (show working separately if the question asks for it).

| Step | fx-991EX | fx-991CW |
|---|---|---|
| Open | MENU → A (Equation/Func) → 1 (Simul Equation) → 3 unknowns | HOME → Equation → Simul Equation → 3 unknowns |
| Enter | Type each row's coefficients, then the constant | Same |
| Solve | = and step through $x$, $y$, $z$ | EXE and step through |

**Check:** for the system in the [[Mesh analysis]] worked example, you should get 4.457, 3.429 and 3.943.

## Complex numbers
Needed later for AC impedance ($Z_L = j\omega L$).
- fx-991EX: MENU → 2 (Complex). The imaginary unit $i$ is **ENG**. Convert to polar with OPTN → ▶r∠θ.
- fx-991CW: HOME → Complex. Same idea through the TOOLS or OPTN menu.

Engineers write $j$ for $\sqrt{-1}$; the calculator writes $i$. They're the same.

## Repeating a calculation with different values
For tables like RC charging at 0.1τ, 0.5τ, 1τ…: type the full expression once, press =, then use the **left arrow** to go back into it, change only the $t$ value, and press = again. Or use the **Table** mode with $f(x)$ set to your formula.

## Solving any one equation (SOLVE)
Type the equation using the variable $X$ (ALPHA then the X key), e.g. `5(1-e^(-X/0.47))=4`, then **SHIFT → SOLVE** (fx-991EX) or the equivalent in the Calculate app's TOOLS menu on the CW. It finds $X$ numerically, which is handy when you can't rearrange easily.

## Habits that save marks
- Check **degrees or radians** (shown at the top of the screen) before any trig. Kinematics usually needs radians.
- Use the **×10ˣ** key for engineering powers: `470×10^-6` for 470 µF.
- Store intermediate answers (STO → A) instead of retyping rounded numbers.
- Keep at least 4 significant figures until the final answer.
