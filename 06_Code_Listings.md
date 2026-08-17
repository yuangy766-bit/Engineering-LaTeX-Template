# Code Listings

This chapter introduces how to display source code in LaTeX using the **listings** package. The examples are based on MATLAB programs used in engineering reports, assignments, capstone projects, and research papers.

---

# Table of Contents

- Required Packages
- Basic Code Listing
- MATLAB Style
- Line Numbers
- Syntax Highlighting
- Long Code
- Code Caption
- Code Label
- Cross Reference
- Appendix Source Code
- Best Practice

---

# 1. Required Packages

To display source code, load the **listings** package.

```latex
\usepackage{listings}
\usepackage{xcolor}
```

---

# 2. Basic Code Listing

The simplest way to display source code.

```latex
\begin{lstlisting}

clear;
clc;

disp("Hello World");

\end{lstlisting}
```

---

# 3. MATLAB Style

This repository uses a customized MATLAB style.

```latex
\lstdefinestyle{matlabstyle}{
    language=Matlab,
    basicstyle=\ttfamily\footnotesize,
    numbers=left,
    numberstyle=\tiny,
    stepnumber=1,
    numbersep=5pt,
    backgroundcolor=\color{white},
    showspaces=false,
    showstringspaces=false,
    showtabs=false,
    frame=single,
    tabsize=2,
    captionpos=b,
    breaklines=true,
    breakatwhitespace=false,
    keywordstyle=\color{blue},
    commentstyle=\color{gray},
    stringstyle=\color{red}
}
```

This style is used throughout my engineering reports.

---

# 4. Global Settings

Instead of configuring every code block individually, define global settings.

```latex
\lstset{
    basicstyle=\ttfamily\small,
    breaklines=true,
    frame=single,
    numbers=left,
    numberstyle=\tiny,
    keywordstyle=\bfseries,
    commentstyle=\itshape,
    showstringspaces=false
}
```

All following code listings will automatically use these settings.

---

# 5. MATLAB Program

Use the predefined style.

```latex
\begin{lstlisting}[style=matlabstyle]

clear;
clc;

x = linspace(0,10,100);
y = sin(x);

plot(x,y);

\end{lstlisting}
```

---

# 6. Line Numbers

Display line numbers.

```latex
numbers=left
```

Hide line numbers.

```latex
numbers=none
```

---

# 7. Syntax Highlighting

Customize different parts of the code.

Keywords

```latex
keywordstyle=\color{blue}
```

Comments

```latex
commentstyle=\color{gray}
```

Strings

```latex
stringstyle=\color{red}
```

---

# 8. Long Code

Enable automatic line wrapping.

```latex
breaklines=true
```

Do not break only at spaces.

```latex
breakatwhitespace=false
```

---

# 9. Code Caption

Every source code listing should include a caption.

Example

```latex
\begin{lstlisting}

...

\caption{MATLAB Program}

\end{lstlisting}
```

or

```latex
\begin{lstlisting}[

caption={MATLAB Program}

]

...

\end{lstlisting}
```

---

# 10. Code Label

Assign a label for cross-referencing.

```latex
\begin{lstlisting}[

caption={MATLAB Program},

label={lst:matlab}

]

...

\end{lstlisting}
```

Recommended naming style

```text
lst:matlab

lst:bisection

lst:newton

lst:simulation
```

---

# 11. Cross Reference

Reference source code using

```latex
Listing~\ref{lst:matlab}
```

Example

```latex
The MATLAB implementation is shown in Listing~\ref{lst:matlab}.
```

---

# 12. Appendix Source Code

For engineering reports, I usually place all MATLAB programs in the appendix.

Example

```latex
\appendix

\section{MATLAB Scripts}
```

Then

```latex
\begin{lstlisting}[

style=matlabstyle,

caption={Composite Simpson's Rule},

label={lst:simpson}

]

...

\end{lstlisting}
```

This keeps the main report concise while preserving the complete implementation.

---

# 13. Best Practice

After writing many engineering reports, these are the conventions I usually follow.

✔ Put long programs in the Appendix.

✔ Give every program a caption.

✔ Give every program a label.

✔ Use `Listing~\ref{}` instead of manually typing listing numbers.

✔ Enable line numbers.

✔ Enable automatic line wrapping.

✔ Use a monospace font.

✔ Use a consistent MATLAB style throughout the report.

✔ Keep one program focused on one task.

---

# Summary

| Command | Description |
|----------|-------------|
| `listings` | Display source code |
| `\lstset{}` | Global settings |
| `\lstdefinestyle{}` | Define custom style |
| `language=Matlab` | MATLAB syntax highlighting |
| `numbers=left` | Show line numbers |
| `frame=single` | Add a border |
| `breaklines=true` | Automatic line wrapping |
| `caption={}` | Code caption |
| `label={}` | Code label |
| `Listing~\ref{}` | Cross-reference a code listing |

---

# My Recommendations

For engineering reports, I recommend placing all MATLAB source code in the appendix instead of the main report. The main chapters should focus on explaining the methodology, equations, and results, while the appendix provides the complete implementation for reproducibility.

Using a consistent code style with line numbers, captions, and labels makes the report easier to read and gives it a more professional appearance.
