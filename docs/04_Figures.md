# Figures

This chapter introduces how to insert, arrange, caption, and reference figures in LaTeX. The examples are based on engineering reports, laboratory reports, capstone projects, and research papers that I have completed during my undergraduate studies.

---

# Table of Contents

- Required Packages
- Basic Figure
- Figure Size
- Figure Placement
- Figure Caption
- Figure Label
- Cross Reference
- Multiple Figures
- Full Width Figures
- Recommended Figure Width
- Figure Alignment
- Image Formats
- Organizing Images
- Best Practice
- Complete Example

---

# 1. Required Packages

To insert images into LaTeX, load the following packages.

```latex
\usepackage{graphicx}
\usepackage{float}
```

If multiple images are placed in one figure.

```latex
\usepackage{subcaption}
```

---

# 2. Basic Figure

The most common way to insert a figure.

```latex
\begin{figure}[H]

    \centering

    \includegraphics[width=0.7\linewidth]{figure.png}

    \caption{Simulation Result}

    \label{fig:simulation}

\end{figure}
```

---

# 3. Figure Size

## Relative to line width

```latex
\includegraphics[width=0.6\linewidth]{figure.png}
```

---

## Relative to text width

```latex
\includegraphics[width=0.8\textwidth]{figure.png}
```

---

## Fixed width

```latex
\includegraphics[width=12cm]{figure.png}
```

---

## Fixed height

```latex
\includegraphics[height=8cm]{figure.png}
```

---

## Width and Height

```latex
\includegraphics[
    width=12cm,
    height=8cm
]{figure.png}
```

---

# 4. Figure Placement

The optional parameter controls where LaTeX places the figure.

```latex
\begin{figure}[h]
```

| Option | Meaning |
|---------|----------|
| h | Here |
| t | Top |
| b | Bottom |
| p | Float page |
| H | Exactly here |

For engineering reports, I almost always use

```latex
\begin{figure}[H]
```

because figures stay close to the related paragraph.

---

# 5. Figure Caption

Every figure should have a caption.

```latex
\caption{LTspice Simulation Result}
```

Output

```
Figure 1
LTspice Simulation Result
```

---

# 6. Figure Label

Always add a label after the caption.

```latex
\label{fig:ltspice}
```

Recommended naming style

```text
fig:circuit

fig:simulation

fig:blockdiagram

fig:pcb

fig:comsol

fig:result
```

---

# 7. Cross Reference

Instead of typing

```
Figure 5
```

use

```latex
Figure~\ref{fig:ltspice}
```

Example

```latex
As shown in Figure~\ref{fig:ltspice}, the output voltage is stable.
```

LaTeX automatically updates figure numbers.

---

# 8. Multiple Figures

Load package

```latex
\usepackage{subcaption}
```

Example

```latex
\begin{figure}[H]

\centering

\begin{subfigure}{0.45\textwidth}

\includegraphics[width=\linewidth]{bright.png}

\caption{Bright}

\end{subfigure}

\hfill

\begin{subfigure}{0.45\textwidth}

\includegraphics[width=\linewidth]{dark.png}

\caption{Dark}

\end{subfigure}

\caption{Comparison Between Bright and Dark Conditions}

\label{fig:comparison}

\end{figure}
```

---

# 9. Full Width Figures

Some engineering figures should occupy almost the entire page width.

Example

```latex
\includegraphics[width=\linewidth]{pcb.png}
```

or

```latex
\includegraphics[width=1\linewidth]{pcb.png}
```

Typical examples

- PCB Layout
- Block Diagram
- COMSOL Simulation
- Large MATLAB Figure

---

# 10. Recommended Figure Width

These are the widths I usually use.

| Figure | Width |
|---------|--------|
| Circuit Diagram | `0.7\linewidth` |
| LTspice Waveform | `0.7\linewidth` |
| MATLAB Plot | `0.75\linewidth` |
| COMSOL Result | `0.8\linewidth` |
| PCB Layout | `1.0\linewidth` |
| Block Diagram | `0.9\linewidth` |
| Flow Chart | `0.8\linewidth` |
| Small Icons | `0.3\linewidth` |
| University Logo | `0.3\linewidth` |

---

# 11. Figure Alignment

Center

```latex
\centering
```

Left

```latex
\raggedright
```

Right

```latex
\raggedleft
```

For almost every engineering report, centered figures are recommended.

---

# 12. Image Formats

Recommended image formats.

| Format | Recommendation |
|----------|---------------|
| PNG | ⭐⭐⭐⭐⭐ |
| PDF | ⭐⭐⭐⭐⭐ |
| JPG | ⭐⭐⭐ |
| SVG | Need conversion |

PNG is recommended for screenshots.

PDF is recommended for vector graphics.

---

# 13. Organizing Images

For small projects

```text
Project

main.tex

figure1.png

figure2.png
```

For large projects

```text
Project

main.tex

figures/

├── chapter1/

├── chapter2/

├── matlab/

├── pcb/

└── comsol/
```

Insert images using

```latex
\includegraphics{figures/chapter1/figure1.png}
```

---

# 14. Best Practice

For engineering reports, I recommend

✔ Every figure has a caption

✔ Every figure has a label

✔ Use `Figure~\ref{}` instead of typing numbers manually

✔ Center all figures

✔ Keep figures close to the paragraph that explains them

✔ Use high-resolution images

✔ Keep all images inside a dedicated `figures/` folder

✔ Use consistent figure widths throughout the report

---

# 15. Complete Example

```latex
\begin{figure}[H]

    \centering

    \includegraphics[
        width=0.75\linewidth
    ]{simulation.png}

    \caption{LTspice Simulation Result}

    \label{fig:simulation}

\end{figure}

As shown in Figure~\ref{fig:simulation}, the simulated output agrees well with the theoretical analysis.
```

---

# Summary

| Command | Description |
|----------|-------------|
| `\includegraphics{}` | Insert image |
| `width=` | Set width |
| `height=` | Set height |
| `\caption{}` | Figure caption |
| `\label{}` | Figure label |
| `\ref{}` | Reference figure |
| `\centering` | Center figure |
| `[H]` | Place figure exactly here |
| `subcaption` | Multiple figures |
| `\linewidth` | Relative width |
| `\textwidth` | Relative page width |

---

# My Recommendations

After writing dozens of engineering reports, I usually follow these conventions:

- Use `0.7–0.8\linewidth` for most figures.
- Use `1.0\linewidth` only for wide figures such as PCB layouts, COMSOL results, and system block diagrams.
- Always place `\caption{}` before `\label{}`.
- Use descriptive labels such as `fig:pcb_top`, `fig:ltspice_output`, or `fig:comsol_temperature`.
- Keep all images in a dedicated `figures/` directory to make the project easier to manage.
