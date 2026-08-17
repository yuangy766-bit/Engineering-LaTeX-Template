# Tables

This chapter introduces how to create professional tables in LaTeX for engineering reports. The examples in this chapter are extracted from my own reports, including assignments, laboratory reports, capstone projects, and research papers.

---

# Table of Contents

- Required Packages
- Standard Table
- IEEE Style Table
- Fixed Width Columns
- Automatic Line Wrapping
- Wide Tables
- Merging Rows and Columns
- Caption and Label
- Cross Reference
- Handling Oversized Tables
- Best Practice

---

# 1. Required Packages

The following packages are commonly used for tables.

```latex
\usepackage{booktabs}
\usepackage{array}
\usepackage{tabularx}
\usepackage{multirow}
\usepackage{adjustbox}
\usepackage{makecell}
\usepackage{pdflscape}
```

---

# 2. Standard Table

A standard table is suitable for most engineering reports.

```latex
\begin{table}[H]

\centering

\caption{Summary Statistics}

\label{tab:summary}

\begin{tabular}{lcc}

\hline

Statistic & Temperature & Power \\

\hline

Mean & 54.13 & 3.80 \\

Standard Deviation & 12.15 & 0.71 \\

Maximum & 71 & 4.90 \\

Minimum & 35 & 2.80 \\

\hline

\end{tabular}

\end{table}
```

---

# 3. IEEE Style Table

For IEEE papers and professional reports, I recommend using **Booktabs** instead of multiple `\hline`s.

```latex
\begin{table}[H]

\centering

\caption{Comparison of Numerical Methods}

\label{tab:comparison}

\begin{tabular}{cccc}

\toprule

Method & Root & Iterations & Error \\

\midrule

Bisection & 1.4812 & 12 & $10^{-4}$ \\

Newton--Raphson & 1.4812 & 5 & $10^{-6}$ \\

\bottomrule

\end{tabular}

\end{table}
```

Booktabs provides cleaner and more professional tables, especially for journal papers.

---

# 4. Fixed Width Columns

Sometimes a column contains long text.

Instead of using

```latex
\begin{tabular}{cc}
```

use

```latex
\begin{tabular}{p{5cm}p{6cm}}
```

If the text should be centered,

```latex
>{\centering\arraybackslash}p{5cm}
```

Example

```latex
\begin{tabular}{
|>{\centering\arraybackslash}p{9em}
|>{\centering\arraybackslash}p{12em}|
}
```

This is exactly the format used in the XMUM assignment cover page.

---

# 5. Automatic Line Wrapping

Long text can automatically wrap inside a fixed-width column.

```latex
\begin{tabular}{|p{5cm}|p{8cm}|}
```

or use `tabularx`.

```latex
\begin{tabularx}{\textwidth}{lX}
```

The `X` column automatically adjusts its width according to the page.

This is recommended when writing descriptions, project schedules, or comparison tables.

---

# 6. Wide Tables

When a table is wider than the page, resize it automatically.

Using `adjustbox`

```latex
\begin{adjustbox}{width=\textwidth}

\begin{tabular}{......}

...

\end{tabular}

\end{adjustbox}
```

or

```latex
\resizebox{\textwidth}{!}{

...

}
```

This keeps the entire table inside the page.

---

# 7. Merging Rows and Columns

Merge columns

```latex
\multicolumn{2}{c}{Simulation Results}
```

Merge rows

```latex
\multirow{2}{*}{Experiment}
```

These commands are useful when creating comparison tables.

---

# 8. Caption and Label

Every table should include

```latex
\caption{}

\label{}
```

Example

```latex
\caption{Simulation Results}

\label{tab:simulation}
```

Always place the label immediately after the caption.

---

# 9. Cross Reference

Instead of typing

```
Table 4
```

use

```latex
Table~\ref{tab:simulation}
```

Example

```latex
The simulation results are summarised in Table~\ref{tab:simulation}.
```

LaTeX updates the table number automatically.

---

# 10. Handling Oversized Tables

If a table exceeds the page width, I usually solve it in the following order.

## Method 1 — Automatic Line Wrapping

```latex
p{5cm}
```

or

```latex
tabularx
```

---

## Method 2 — Resize the Table

```latex
\begin{adjustbox}{width=\textwidth}
```

or

```latex
\resizebox{\textwidth}{!}
```

---

## Method 3 — Reduce Column Spacing

```latex
\setlength{\tabcolsep}{4pt}
```

The default value is approximately 6pt.

---

## Method 4 — Reduce Row Height

```latex
\renewcommand{\arraystretch}{0.9}
```

Default

```latex
\arraystretch = 1
```

---

## Method 5 — Reduce Font Size

```latex
\small
```

or

```latex
\footnotesize
```

or

```latex
\scriptsize
```

---

## Method 6 — Landscape Page

For very wide tables

```latex
\begin{landscape}

...

\end{landscape}
```

---

## Method 7 — Split the Table

If none of the above works, divide the table into two smaller tables.

---

# Best Practice

After writing many engineering reports, these are the conventions I usually follow.

✔ Use **Booktabs** for reports and papers.

✔ Avoid excessive vertical lines.

✔ Place captions above the table.

✔ Place labels immediately after captions.

✔ Use `Table~\ref{}` instead of manually typing table numbers.

✔ Keep decimal places consistent.

✔ Use `tabularx` when the table contains long descriptions.

✔ Use `adjustbox` before reducing the font size.

✔ Use landscape pages only when absolutely necessary.

✔ Keep tables centered on the page.
