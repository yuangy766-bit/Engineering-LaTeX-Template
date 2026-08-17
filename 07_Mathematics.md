# Mathematics and Engineering Diagrams

This chapter introduces mathematical typesetting and engineering diagram generation in LaTeX.

The examples in this chapter are based on equations, derivations, RF calculations, microwave engineering problems, transmission-line analysis, S-parameters, matching networks, and circuit diagrams that I have used in my own engineering coursework.

The main goal is not only to show LaTeX syntax, but also to demonstrate a clean and consistent way to present engineering calculations.

---

# Table of Contents

- Required Packages
- Inline Mathematics
- Display Equations
- Equation Numbering
- Unnumbered Equations
- Multi-line Derivations
- Aligning Equations
- Final Answers
- Fractions
- Square Roots
- Powers and Subscripts
- Brackets
- Greek Symbols
- Complex Numbers
- Polar Form
- Matrices
- Piecewise Functions
- Mathematical Operators
- Scientific Notation
- Engineering Units
- Equation Cross References
- Custom Commands
- TikZ
- CircuitTikZ
- Engineering Diagram Examples
- Best Practice

---

# 1. Required Packages

For most engineering mathematics, I use

```latex
\usepackage{amsmath}
\usepackage{amssymb}
\usepackage{mathtools}
```

For engineering units

```latex
\usepackage{siunitx}
```

For diagrams

```latex
\usepackage{tikz}
\usepackage{circuitikz}
```

A useful `siunitx` configuration is

```latex
\sisetup{
    per-mode=symbol,
    separate-uncertainty=true,
    exponent-product=\cdot
}
```

---

# 2. Inline Mathematics

Inline mathematics is used when an equation appears inside a sentence.

```latex
The electrical length is \(\theta=\beta l\).
```

or

```latex
The characteristic impedance is \(Z_0=\SI{50}{\ohm}\).
```

Inline equations should be used for short expressions that do not need their own line.

---

# 3. Display Equations

For important equations, use the `equation` environment.

```latex
\begin{equation}
Z_{\mathrm{in}}
=
Z_0
\frac{Z_L+jZ_0\tan(\beta l)}
{Z_0+jZ_L\tan(\beta l)}
\end{equation}
```

This automatically centers and numbers the equation.

---

# 4. Unnumbered Equations

If numbering is not needed, use

```latex
\[
Z_0=\SI{50}{\ohm}
\]
```

or

```latex
\begin{equation*}
Z_0=\SI{50}{\ohm}
\end{equation*}
```

This is useful for short intermediate expressions.

---

# 5. Multi-line Derivations

For engineering calculations, the `align` environment is one of the most useful tools.

Example

```latex
\begin{align}
\theta
&=
\beta l
\\
&=
\left(\SI{4}{\radian\per\metre}\right)
\left(\SI{1.5}{\metre}\right)
\\
&=
\SI{6}{\radian}
\end{align}
```

The `&` symbol aligns all equations at the same position.

I usually place it immediately before the equals sign.

---

# 6. Aligning Equations

A common engineering derivation may look like

```latex
\begin{align}
\lambda_g
&=
\frac{c}
{f_0\sqrt{\varepsilon_{\mathrm{eff}}}}
\\
&=
\frac{3.0\times10^8}
{(3.0\times10^9)\sqrt{6.216}}
\\
&=
\SI{40.11}{\milli\metre}
\end{align}
```

This format makes every calculation step easy to follow.

---

# 7. Final Answers

For engineering assignments, I normally highlight the final result using `\boxed{}`.

```latex
\begin{equation}
\boxed{
Z_{0T}=\SI{70.71}{\ohm}
}
\end{equation}
```

or

```latex
\[
\boxed{f_0=\SI{84.05}{\mega\hertz}}
\]
```

This makes the final answer easy to identify during marking or review.

---

# 8. Fractions

Use

```latex
\frac{a}{b}
```

Example

```latex
\Gamma_L
=
\frac{Z_L-Z_0}
{Z_L+Z_0}
```

For complex engineering equations, split the numerator and denominator across lines if necessary.

---

# 9. Square Roots

Basic square root

```latex
\sqrt{x}
```

Example

```latex
\sqrt{83^2+(-25)^2}
```

Nested example

```latex
\sqrt{\frac{1+k}{1-k}}
```

---

# 10. Powers and Subscripts

Superscript

```latex
x^2
```

Subscript

```latex
Z_0
```

Multiple characters should use braces

```latex
Z_{\mathrm{in}}
```

```latex
\varepsilon_{\mathrm{eff}}
```

```latex
P_{\mathrm{out}}
```

---

# 11. Brackets

For automatically sized brackets, use

```latex
\left(
...
\right)
```

Example

```latex
\left(
1+\frac{12h}{w}
\right)^{-1/2}
```

Other bracket types include

```latex
\left[
...
\right]
```

```latex
\left\{
...
\right\}
```

---

# 12. Greek Symbols

Greek symbols are used extensively in engineering.

| Code | Symbol |
|---|---|
| `\alpha` | $begin:math:text$\\alpha$end:math:text$ |
| `\beta` | $begin:math:text$\\beta$end:math:text$ |
| `\gamma` | $begin:math:text$\\gamma$end:math:text$ |
| `\theta` | $begin:math:text$\\theta$end:math:text$ |
| `\phi` | $begin:math:text$\\phi$end:math:text$ |
| `\omega` | $begin:math:text$\\omega$end:math:text$ |
| `\lambda` | $begin:math:text$\\lambda$end:math:text$ |
| `\Gamma` | $begin:math:text$\\Gamma$end:math:text$ |
| `\Delta` | $begin:math:text$\\Delta$end:math:text$ |
| `\varepsilon` | $begin:math:text$\\varepsilon$end:math:text$ |

Example

```latex
\Gamma_L
```

```latex
\lambda_g
```

```latex
\varepsilon_{\mathrm{eff}}
```

---

# 13. Complex Numbers

In electrical and electronic engineering, the imaginary unit is normally written as an upright $begin:math:text$j$end:math:text$, not an italic variable.

I define

```latex
\newcommand{\jmathunit}{\mathrm{j}}
```

Then write

```latex
83-\jmathunit25
```

instead of

```latex
83-j25
```

Example

```latex
Z_L=83-\jmathunit25~\si{\ohm}
```

---

# 14. Polar Form

For RF and microwave engineering, polar notation is used constantly.

I define

```latex
\newcommand{\polar}[2]{#1\angle #2^{\circ}}
```

Then

```latex
\polar{0.3059}{-26.50}
```

produces

$begin:math:display$
0\.3059\\angle \-26\.50\^\\circ
$end:math:display$

Example

```latex
\Gamma_L
=
\polar{0.3059}{-26.50}
```

---

# 15. Degree Symbol

A convenient custom command is

```latex
\newcommand{\degree}{^{\circ}}
```

Example

```latex
343.77\degree
```

---

# 16. Matrices

Matrices are very useful for S-parameters, state-space models, and linear algebra.

Example

```latex
\begin{equation}
[S]
=
\begin{bmatrix}
0 & -\jmathunit0.9487 & 0 & 0.3162\\
-\jmathunit0.9487 & 0 & 0.3162 & 0\\
0 & 0.3162 & 0 & -\jmathunit0.9487\\
0.3162 & 0 & -\jmathunit0.9487 & 0
\end{bmatrix}
\end{equation}
```

Common matrix environments include

```latex
bmatrix
```

Square brackets

```latex
pmatrix
```

Round brackets

```latex
vmatrix
```

Determinant-style vertical bars

---

# 17. Piecewise Functions

For piecewise functions, use

```latex
\begin{cases}
...
\end{cases}
```

Example

```latex
\[
f(x)=
\begin{cases}
x^2, & x\geq0\\
-x, & x<0
\end{cases}
\]
```

---

# 18. Mathematical Operators

Always use LaTeX mathematical operators instead of plain text.

Correct

```latex
\sin
\cos
\tan
\cot
\ln
\log
```

Example

```latex
Z_{\mathrm{in}}
=
\jmathunit Z_0\tan(\beta l)
```

Another example

```latex
RL
=
-20\log_{10}\lvert\Gamma_L\rvert
```

---

# 19. Absolute Value

For magnitude or absolute value, use

```latex
\lvert x\rvert
```

Example

```latex
\lvert\Gamma_L\rvert
```

For impedance magnitude

```latex
\lvert Z_L\rvert
=
\sqrt{R^2+X^2}
```

---

# 20. Scientific Notation

Basic notation

```latex
3.0\times10^8
```

Example

```latex
3.0\times10^8~\si{\metre\per\second}
```

For very large or small engineering values, `siunitx` can also be used.

```latex
\SI{2.7e8}{\metre\per\second}
```

---

# 21. Engineering Units with siunitx

For engineering reports, I strongly recommend using `siunitx`.

Examples

```latex
\SI{50}{\ohm}
```

```latex
\SI{3}{\giga\hertz}
```

```latex
\SI{70}{\nano\henry}
```

```latex
\SI{60}{\pico\farad}
```

```latex
\SI{1.5}{\metre}
```

```latex
\SI{10}{\decibel}
```

```latex
\SI{25}{\volt}
```

This automatically produces consistent spacing and unit formatting.

---

# 22. Compound Units

Example

```latex
\SI{4}{\radian\per\metre}
```

```latex
\SI{2.7e8}{\metre\per\second}
```

```latex
\SI{10}{\milli\ampere}
```

---

# 23. Units Inside Equations

Example

```latex
\begin{equation}
Z_0=\SI{50}{\ohm}
\end{equation}
```

or

```latex
Z_L=83-\jmathunit25~\si{\ohm}
```

I recommend avoiding manually typing units such as

```text
50 ohm
```

because the formatting will not be consistent.

---

# 24. Equation Cross References

Important equations should be labeled.

```latex
\begin{equation}
\Gamma_L
=
\frac{Z_L-Z_0}
{Z_L+Z_0}
\label{eq:reflection}
\end{equation}
```

Reference later using

```latex
Equation~\ref{eq:reflection}
```

This prevents incorrect equation numbering after editing the report.

---

# 25. Custom Commands

If the same notation appears many times, define it once.

Example

```latex
\newcommand{\jmathunit}{\mathrm{j}}
```

```latex
\newcommand{\degree}{^{\circ}}
```

```latex
\newcommand{\polar}[2]{#1\angle #2^{\circ}}
```

Then use

```latex
\polar{0.4390}{-160.19}
```

Custom commands keep notation consistent throughout long reports.

---

# 26. Complete Engineering Calculation Example

```latex
\begin{align}
MAG
&=
\left|
\frac{S_{21}}{S_{12}}
\right|
\left(
K-\sqrt{K^2-1}
\right)
\\
&=
\frac{4.9}{0.02}
\left(
3.639-\sqrt{3.639^2-1}
\right)
\\
&=
34.33
\end{align}

\begin{equation}
\boxed{
MAG_{\mathrm{dB}}
=
\SI{15.36}{\decibel}
}
\end{equation}
```

This is the style I normally use for derivations:

1. Define the equation.
2. Substitute values.
3. Simplify.
4. Box the final result.

---

# 27. TikZ

TikZ allows diagrams to be generated directly in LaTeX instead of inserting screenshots.

Required package

```latex
\usepackage{tikz}
```

Basic structure

```latex
\begin{tikzpicture}

...

\end{tikzpicture}
```

---

# 28. Drawing Lines

Basic line

```latex
\draw (0,0) -- (5,0);
```

Thick line

```latex
\draw[thick] (0,0) -- (5,0);
```

Very thick line

```latex
\draw[very thick] (0,0) -- (5,0);
```

Dashed line

```latex
\draw[dashed] (0,0) -- (5,0);
```

---

# 29. Arrows

```latex
\draw[->] (0,0) -- (3,0);
```

Bidirectional arrow

```latex
\draw[<->] (0,0) -- (3,0);
```

Useful for

- Signal direction
- Current direction
- Distance
- Dimensions
- Data flow

---

# 30. Nodes and Labels

Basic node

```latex
\node at (2,1) {Text};
```

Boxed node

```latex
\node[
    draw,
    minimum width=2cm,
    minimum height=1cm
]
at (2,1)
{Block};
```

---

# 31. Directional Coupler Example

A simple directional-coupler layout can be drawn as

```latex
\begin{figure}[H]
\centering

\begin{tikzpicture}[scale=1.0]

    \draw[rounded corners, thick]
    (0.4,-0.45)
    rectangle
    (6.6,1.65);

    \node at (3.5,1.38)
    {Ideal directional-coupler region};

    \draw[very thick]
    (-0.8,1.0)
    --
    (7.8,1.0);

    \draw[very thick]
    (-0.8,0.0)
    --
    (7.8,0.0);

    \node[left] at (-0.8,1.0) {Port 1};
    \node[right] at (7.8,1.0) {Port 2};

    \node[left] at (-0.8,0.0) {Port 3};
    \node[right] at (7.8,0.0) {Port 4};

    \draw[->,dashed]
    (3.5,0.90)
    --
    (3.5,0.12);

    \node[right]
    at (3.55,0.50)
    {coupling};

\end{tikzpicture}

\caption{Ideal directional coupler.}

\label{fig:coupler}

\end{figure}
```

This is useful when the diagram is mainly conceptual and does not require a complete circuit schematic.

---

# 32. Block Diagrams

TikZ is also suitable for system-level block diagrams.

Example

```latex
\begin{tikzpicture}

\node[
    draw,
    minimum width=2cm,
    minimum height=1cm
]
(input)
at (0,0)
{Input};

\node[
    draw,
    minimum width=2cm,
    minimum height=1cm
]
(processor)
at (4,0)
{Processor};

\node[
    draw,
    minimum width=2cm,
    minimum height=1cm
]
(output)
at (8,0)
{Output};

\draw[->,thick]
(input.east)
--
(processor.west);

\draw[->,thick]
(processor.east)
--
(output.west);

\end{tikzpicture}
```

---

# 33. Matching Network Example

A microwave amplifier matching structure can be drawn using simple blocks.

```latex
\begin{tikzpicture}[x=1cm,y=1cm]

\node[
    draw,
    minimum width=1.7cm,
    minimum height=1cm
]
(source)
at (0,0)
{\(\SI{50}{\ohm}\) Source};

\node[
    draw,
    minimum width=2.4cm,
    minimum height=1.2cm
]
(imn)
at (3,0)
{Input Matching};

\node[
    draw,
    minimum width=2.3cm,
    minimum height=1.4cm
]
(device)
at (6.5,0)
{Transistor};

\node[
    draw,
    minimum width=2.4cm,
    minimum height=1.2cm
]
(omn)
at (10,0)
{Output Matching};

\node[
    draw,
    minimum width=1.7cm,
    minimum height=1cm
]
(load)
at (13,0)
{\(\SI{50}{\ohm}\) Load};

\draw[->,thick]
(source.east)
--
(imn.west);

\draw[->,thick]
(imn.east)
--
(device.west);

\draw[->,thick]
(device.east)
--
(omn.west);

\draw[->,thick]
(omn.east)
--
(load.west);

\end{tikzpicture}
```

---

# 34. CircuitTikZ

For actual circuit schematics, I recommend **CircuitTikZ**.

Required package

```latex
\usepackage{circuitikz}
```

Basic structure

```latex
\begin{circuitikz}

...

\end{circuitikz}
```

---

# 35. Common Circuit Components

Resistor

```latex
to[R]
```

Capacitor

```latex
to[C]
```

Inductor

```latex
to[L]
```

Voltage source

```latex
to[V]
```

Current source

```latex
to[I]
```

Ground

```latex
node[ground]{}
```

---

# 36. Component Labels

Example resistor

```latex
to[R,l=\(R_B\)]
```

Capacitor

```latex
to[C,l=\(C_F\)]
```

Inductor

```latex
to[L,l_=\(L\)]
```

The underscore version

```latex
l_=
```

places the label on the opposite side.

---

# 37. Parallel Resonant Circuit Example

```latex
\begin{circuitikz}[american]

    \draw
    (0,3)
    --
    (6,3);

    \node[left]
    at (0,3)
    {RF tank node};

    \draw
    (1,3)
    to[L,l_=\(L\)]
    (1,0)
    node[ground]{};

    \draw
    (3,3)
    to[C,l=\(C_F\)]
    (3,0)
    node[ground]{};

\end{circuitikz}
```

---

# 38. Varactor Tuning Example

```latex
\begin{figure}[H]
\centering

\begin{circuitikz}[american]

    \draw
    (0,3)
    --
    (6,3);

    \node[left]
    at (0,3)
    {RF tank node};

    \draw
    (1,3)
    to[L,l_=\(L\)]
    (1,0)
    node[ground]{};

    \draw
    (3,3)
    to[C,l=\(C_F\)]
    (3,0)
    node[ground]{};

    \draw
    (5,3)
    to[C,l=\(C_S\)]
    (5,1.55)
    to[C,l_=\(C_V(V_R)\)]
    (5,0)
    node[ground]{};

    \draw
    (5,1.55)
    to[R,l=\(R_B\)]
    (7.5,1.55);

    \node[right]
    at (7.5,1.55)
    {\(V_{\mathrm{tune}}\)};

    \draw
    (7.0,1.55)
    to[C,l_=\(C_B\)]
    (7.0,0)
    node[ground]{};

    \fill
    (5,1.55)
    circle
    (1.8pt);

    \fill
    (7.0,1.55)
    circle
    (1.8pt);

\end{circuitikz}

\caption{Electronically controlled varactor tuning network.}

\label{fig:varactor}

\end{figure}
```

---

# 39. When to Use TikZ and CircuitTikZ

I normally use **TikZ** for

- Block diagrams
- Directional coupler layouts
- Wilkinson divider layouts
- Matching-network diagrams
- Signal-flow diagrams
- Simple geometry
- Conceptual RF diagrams

I normally use **CircuitTikZ** for

- RLC circuits
- Bias networks
- Filters
- Resonant circuits
- Power supplies
- Transistor circuits
- Sensor interfaces

---

# 40. Figure Caption and Reference

TikZ and CircuitTikZ drawings can be placed inside a normal figure environment.

```latex
\begin{figure}[H]

\centering

\begin{tikzpicture}

...

\end{tikzpicture}

\caption{System Block Diagram}

\label{fig:block}

\end{figure}
```

Then reference it using

```latex
Figure~\ref{fig:block}
```

---

# 41. Advantages of Drawing Directly in LaTeX

Compared with screenshots, TikZ and CircuitTikZ provide

- Vector graphics
- Sharp output at any zoom level
- Consistent fonts
- Consistent mathematical notation
- Easy editing
- Better integration with captions and labels
- Better appearance in research papers

For technical diagrams that are not extremely complicated, I usually prefer LaTeX-generated diagrams.

---

# 42. Best Practice

After writing engineering reports with many equations and diagrams, these are the conventions I normally follow.

### Mathematics

- Use `equation` for important single equations.
- Use `align` for multi-step derivations.
- Align calculations at the equals sign.
- Use `\boxed{}` for final answers.
- Use `siunitx` for physical units.
- Use upright `\mathrm{j}` for the imaginary unit.
- Define reusable notation using custom commands.
- Use equation labels instead of manual numbering.
- Keep notation consistent throughout the entire report.

### Engineering Units

- Use `\SI{}{}` whenever possible.
- Keep numbers and units separated correctly.
- Avoid manually typing units in italic math mode.
- Use standard SI prefixes such as `\nano`, `\micro`, `\milli`, `\mega`, and `\giga`.

### TikZ

- Use TikZ for conceptual diagrams and block diagrams.
- Keep diagrams simple and readable.
- Use consistent line thickness.
- Use arrows to indicate direction clearly.
- Place labels close to the corresponding component.

### CircuitTikZ

- Use CircuitTikZ for actual circuit schematics.
- Label important components directly in the diagram.
- Use proper ground symbols.
- Keep circuit diagrams electrically readable instead of making them decorative.

---

# 43. Recommended Engineering Mathematics Workflow

For most calculation-based engineering reports, I use the following structure:

```text
Define the governing equation

↓

Substitute known values

↓

Perform the derivation step by step

↓

Include units

↓

Calculate the numerical result

↓

Box the final answer

↓

Explain the engineering meaning
```

Example

```latex
\begin{equation}
Z_{0T}
=
\sqrt{Z_0Z_L}
\end{equation}

\begin{align}
Z_{0T}
&=
\sqrt{(50)(100)}
\\
&=
\SI{70.71}{\ohm}
\end{align}

\begin{equation}
\boxed{
Z_{0T}=\SI{70.71}{\ohm}
}
\end{equation}
```

This format keeps mathematical work easy to verify and makes long engineering solutions much easier to read.

---

# Summary

| Command / Package | Purpose |
|---|---|
| `amsmath` | Advanced mathematics |
| `amssymb` | Mathematical symbols |
| `mathtools` | Extended math tools |
| `equation` | Numbered equation |
| `align` | Multi-line derivation |
| `\boxed{}` | Highlight final result |
| `\frac{}{}` | Fraction |
| `\sqrt{}` | Square root |
| `bmatrix` | Matrix |
| `\lvert\rvert` | Magnitude / absolute value |
| `siunitx` | Engineering units |
| `\SI{}{}` | Number with SI unit |
| `\si{}` | Unit only |
| `\newcommand` | Custom notation |
| `tikz` | Engineering diagrams |
| `circuitikz` | Circuit schematics |
| `\draw` | Draw lines and shapes |
| `\node` | Add labels or blocks |
| `to[R]` | Resistor |
| `to[C]` | Capacitor |
| `to[L]` | Inductor |
| `node[ground]{}` | Ground symbol |
