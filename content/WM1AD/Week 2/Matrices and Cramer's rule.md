---
title: Matrices and Cramer's rule
tags: [WM1AD, WM1AC, week-2, maths]
---
## The idea
A circuit with three loops gives you three simultaneous equations. Writing them as a **matrix** keeps them tidy, and the **determinant** gives a mechanical way to solve them. You'll use this in [[Mesh analysis]], and it also turns up in WM1AC for vectors and robot kinematics.

## Matrices
An $m \times n$ matrix has $m$ rows and $n$ columns; $a_{ij}$ is the element in row $i$, column $j$.

- **Add or subtract:** same size only, element by element.
- **Multiply** $AB$: the columns of $A$ must equal the rows of $B$. $(m\times n)(n\times p) \to (m\times p)$. Each element is a row of $A$ dotted with a column of $B$.
  $$\begin{bmatrix} 2 & 3 \\ 1 & 4 \end{bmatrix}\begin{bmatrix} 5 & 1 \\ 0 & 2 \end{bmatrix} = \begin{bmatrix} 10 & 8 \\ 5 & 9 \end{bmatrix}$$
- **Order matters:** in general $AB \neq BA$.
- **There's no division.** "$A \div B$" means $AB^{-1}$, which only exists if $\det B \neq 0$.

## Determinants
A single number from a **square** matrix. If it's **zero**, the matrix has no inverse and the equations have no unique solution (the rows aren't independent).

**2×2:**
$$\begin{vmatrix} a & b \\ c & d \end{vmatrix} = ad - bc$$

**3×3:** expand along any row or column. Each element times its **minor** (the 2×2 left when you cover its row and column), with signs from the chequerboard:
$$\begin{matrix} + & - & + \\ - & + & - \\ + & - & + \end{matrix}$$
Choose the row or column with the most zeros to save work.

**2×2 inverse:** swap the main diagonal, negate the other two, divide by the determinant:
$$\begin{bmatrix} a & b \\ c & d \end{bmatrix}^{-1} = \frac{1}{ad - bc}\begin{bmatrix} d & -b \\ -c & a \end{bmatrix}$$

## Cramer's rule
For equations $A\mathbf{x} = \mathbf{b}$:
1. Find $\Delta = \det A$.
2. For each unknown, **replace its column** of $A$ with $\mathbf b$ and take that determinant, $\Delta_k$.
3. $x_k = \Delta_k / \Delta$.
4. **Substitute back** to check.

## Worked example
Find $\det\begin{bmatrix} 3 & 1 & 2 \\ 0 & 4 & 1 \\ 2 & -1 & 3 \end{bmatrix}$, then solve $2x + 3y = 13$, $x - y = -1$ with Cramer's rule.

> [!example]- Answer
> Expand along column 1 (it has a zero): $3\begin{vmatrix} 4 & 1 \\ -1 & 3 \end{vmatrix} - 0 + 2\begin{vmatrix} 1 & 2 \\ 4 & 1 \end{vmatrix} = 3(13) + 2(1 - 8) = 39 - 14 = $ **25**
> $\Delta = \begin{vmatrix} 2 & 3 \\ 1 & -1 \end{vmatrix} = -2 - 3 = -5$
> $\Delta_x = \begin{vmatrix} 13 & 3 \\ -1 & -1 \end{vmatrix} = -13 + 3 = -10$ → $x = 2$
> $\Delta_y = \begin{vmatrix} 2 & 13 \\ 1 & -1 \end{vmatrix} = -2 - 13 = -15$ → $y = 3$
> Check: $2(2) + 3(3) = 13$ ✓, $2 - 3 = -1$ ✓

## On the calculator and in MATLAB
- Scientific calculators (e.g. Casio fx-991) have a **Matrix** mode for determinants and an **Equation / Simul** mode that solves 3×3 systems directly. Use Cramer when you need to show working.
- MATLAB: `A = [2, 3; 1, -1]` (commas separate columns, semicolons rows), `det(A)`, and `x = A\b` with `b = [13; -1]`. **b must be a column**, so use `;`.

## Common mistakes
- Forgetting the minus sign in the middle of the $+ - +$ pattern.
- Multiplying matrices element by element.
- Putting the constants in the wrong column for $\Delta_k$.

## Check yourself
> [!question]- 1. Inverse of $\begin{bmatrix} 4 & 2 \\ 3 & 5 \end{bmatrix}$?
> $\Delta = 20 - 6 = 14$, so $\dfrac{1}{14}\begin{bmatrix} 5 & -2 \\ -3 & 4 \end{bmatrix}$.

> [!question]- 2. Why does $\begin{bmatrix} 1 & 2 \\ 2 & 4 \end{bmatrix}$ have no inverse?
> Its determinant is $4 - 4 = 0$: the second row is just twice the first.
