---
title: MATLAB basics
tags: [tools]
---
## Getting it
Students can usually use MATLAB through the university licence, either installed or in the browser (**MATLAB Online**). Check the IT services pages for the current way to sign in. **MATLAB Onramp**, MathWorks' free two-hour course, is worth doing first.

## The essentials
```matlab
x = 5;                 % semicolon hides the output
v = [1, 2, 3];         % row vector (commas or spaces)
c = [1; 2; 3];         % column vector (semicolons)
A = [2, 1, -1; 1, 3, 2; 2, -1, 4];   % 3x3 matrix: commas split columns, semicolons split rows
A(2,3)                 % row 2, column 3 -> 2
A'                     % transpose
det(A)                 % determinant
inv(A)                 % inverse
```

**Element-wise vs matrix operations:** `A*B` is matrix multiplication; `A.*B` multiplies element by element. The same goes for `.^` and `./`. You need the dot when applying a formula to a whole vector of values, like `t.^2`.

## Solving a circuit
The [[Mesh analysis]] worked example in three lines:
```matlab
R = [10, -6, 0; -6, 17, -8; 0, -8, 10];
V = [24; 0; 12];        % must be a column
I = R \ V               % backslash solves R*I = V
```
Use `\`, not `inv(R)*V`. It's faster and more accurate. A common error is writing `V = [24, 0, 12]` (a row), which gives a dimension error.

## Plotting an RC transient
```matlab
R = 47e3;  C = 100e-6;  V = 12;
tau = R*C;
t = linspace(0, 5*tau, 500);      % 500 points from 0 to 5 tau
u = V*(1 - exp(-t/tau));          % note: exp works element-wise
i = (V/R)*exp(-t/tau);

yyaxis left;  plot(t, u); ylabel('u_C (V)');
yyaxis right; plot(t, i*1e3); ylabel('i (mA)');
xlabel('t (s)'); title('RC charging'); grid on
```

## Printing results neatly
```matlab
fprintf('tau = %.2f s\n', tau);
fprintf('I1 = %.3f A, I2 = %.3f A, I3 = %.3f A\n', I);
```

## Scripts and functions
- A **script** (`.m` file) is a list of commands. Put `clear; clc;` at the top so old variables don't interfere.
- A **function** goes in its own file named after it:
```matlab
function P = mosfet_loss(Rds, I, V, ton, toff, f)
    P = Rds*I^2 + (V*I/2)*(ton + toff)*f;
end
```
Call it with `mosfet_loss(0.075, 10, 24, 57e-9, 74e-9, 13e3)` and you get 7.70 W, matching [[MOSFET power loss]].

## Common errors
| Message | Usual cause |
|---|---|
| `Dimensions of arrays being concatenated are not consistent` | Rows of different lengths in a matrix |
| `Incorrect dimensions for matrix multiplication` | Used `*` where you needed `.*` |
| `Undefined function or variable` | Typo, or the script ran before the variable was set |
| `Matrix is singular` | Determinant is zero: check your equations |
