# Getting Started

This chapter introduces the basic configuration of a LaTeX document. Before writing any content, it is recommended to configure the document structure, page layout, fonts, spacing, and page style.

---

# 1. Document Class

The document class defines the overall type of the document.

```latex
\documentclass[a4paper,12pt]{article}
```

### Explanation

| Option | Description |
|----------|-------------|
| article | Article document class |
| a4paper | A4 paper size |
| 12pt | Main font size |

For most engineering reports at XMUM, I recommend using:

```latex
\documentclass[a4paper,12pt]{article}
```

---

# 2. Page Layout

The `geometry` package controls page margins.

```latex
\usepackage[
    top=2.5cm,
    bottom=2.5cm,
    left=2.5cm,
    right=2.5cm
]{geometry}
```

or simply

```latex
\usepackage[a4paper,margin=2.5cm]{geometry}
```

### Recommended

```
Top    : 2.5 cm
Bottom : 2.5 cm
Left   : 2.5 cm
Right  : 2.5 cm
```

---

# 3. Font

For engineering reports, Times New Roman style fonts are commonly required.

```latex
\usepackage{newtxtext}
\usepackage{newtxmath}
```

These packages apply a Times-style font to both text and mathematical equations.

---

# 4. Line Spacing

Load the package

```latex
\usepackage{setspace}
```

Common options:

```latex
\singlespacing
```

Single spacing

```latex
\onehalfspacing
```

1.5 line spacing

```latex
\doublespacing
```

Double spacing

For most reports, I recommend

```latex
\onehalfspacing
```

---

# 5. Page Number

Display Arabic page numbers

```latex
\pagenumbering{arabic}
```

Display Roman page numbers

```latex
\pagenumbering{roman}
```

Hide page number for a single page

```latex
\thispagestyle{empty}
```

Hide page numbers for the whole document

```latex
\pagestyle{empty}
```

---

# 6. Header and Footer

Load the package

```latex
\usepackage{fancyhdr}
```

Enable custom page style

```latex
\pagestyle{fancy}
```

Clear the default header and footer

```latex
\fancyhf{}
```

Header example

```latex
\fancyhead[C]{XIAMEN UNIVERSITY MALAYSIA}
```

Footer example

```latex
\fancyfoot[C]{\thepage}
```

Remove the horizontal line

```latex
\renewcommand{\headrulewidth}{0pt}
```

Complete example

```latex
\usepackage{fancyhdr}

\pagestyle{fancy}

\fancyhf{}

\fancyhead[C]{XIAMEN UNIVERSITY MALAYSIA}

\fancyfoot[C]{\thepage}

\renewcommand{\headrulewidth}{0pt}
```

---

# 7. Paragraph

Indent the first paragraph after each section

```latex
\usepackage{indentfirst}
```

Set paragraph indentation

```latex
\setlength{\parindent}{2em}
```

Remove indentation

```latex
\setlength{\parindent}{0pt}
```

Paragraph spacing

```latex
\setlength{\parskip}{0.5em}
```

---

# 8. Section Formatting

Center all section titles

```latex
\usepackage{sectsty}

\sectionfont{\centering}
```

Example

```latex
\section{Introduction}
```

---

# 9. New Page

Start a new page

```latex
\newpage
```

Flush all floating figures/tables before starting a new page

```latex
\clearpage
```

---

# 10. Vertical and Horizontal Spacing

Vertical spacing

```latex
\vspace{1cm}
```

Negative spacing

```latex
\vspace{-1cm}
```

Horizontal spacing

```latex
\hspace{1cm}
```

Automatically push content to the bottom

```latex
\vfill
```

---

# 11. Title Page

A simple title page can be created using

```latex
\begin{titlepage}
\centering

\includegraphics[width=0.8\textwidth]{cover.png}

\vfill

{\Huge\bfseries
Title
\par}

\vfill

{\Large
Author
\par}

\end{titlepage}
```

---

# 12. Recommended Starter Template

```latex
\documentclass[a4paper,12pt]{article}

% Page Layout
\usepackage[a4paper,margin=2.5cm]{geometry}

% Font
\usepackage{newtxtext}
\usepackage{newtxmath}

% Line Spacing
\usepackage{setspace}
\onehalfspacing

% Paragraph
\usepackage{indentfirst}
\setlength{\parindent}{2em}

% Graphics
\usepackage{graphicx}

% Header and Footer
\usepackage{fancyhdr}

\pagestyle{fancy}
\fancyhf{}

\fancyhead[C]{XIAMEN UNIVERSITY MALAYSIA}
\fancyfoot[C]{\thepage}

\renewcommand{\headrulewidth}{0pt}

\begin{document}

\section{Introduction}

Hello LaTeX!

\end{document}
```

---
