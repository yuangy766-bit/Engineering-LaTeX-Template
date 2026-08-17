# Report Structure

This chapter introduces how to organize an engineering report using LaTeX. The examples presented in this chapter are based on the report structure that I have used throughout my undergraduate studies at Xiamen University Malaysia.

---

# Table of Contents

- Line Spacing
- New Page
- Table of Contents
- Section
- Subsection
- Subsubsection
- Center Section Titles
- Unnumbered Sections
- Add Entries to the Table of Contents
- Appendix
- Typical Engineering Report Structure

---

# 1. Line Spacing

Engineering reports are commonly formatted using **1.5 line spacing**, which improves readability while satisfying most university formatting requirements.

### Example

```latex
\onehalfspacing
```

### Other options

Single spacing

```latex
\singlespacing
```

Double spacing

```latex
\doublespacing
```

---

# 2. New Page

Use `\newpage` whenever a new section should begin on a separate page.

Typical examples include

- Title Page
- Assignment Cover Page
- Own Work Declaration
- Table of Contents
- Appendix

### Example

```latex
\newpage
```

---

# 3. Table of Contents

LaTeX can automatically generate a table of contents according to all section titles.

### Example

```latex
\tableofcontents

\newpage
```

The table of contents will update automatically after compilation.

> **Note**
>
> If the table of contents does not appear correctly, compile the document twice.

---

# 4. Section

Use `\section{}` to create a main section.

### Example

```latex
\section{Introduction}
```

Output

```
1 Introduction
```

Section numbers are generated automatically.

---

# 5. Subsection

Use `\subsection{}` to divide a section into smaller parts.

### Example

```latex
\subsection{Background}
```

Output

```
1.1 Background
```

---

# 6. Subsubsection

Use `\subsubsection{}` for more detailed organization.

### Example

```latex
\subsubsection{Pearson Correlation Coefficient}
```

Output

```
1.1.1 Pearson Correlation Coefficient
```

---

# 7. Center Section Titles

By default, LaTeX aligns section titles to the left.

This template centers all main section titles using the **sectsty** package.

### Required package

```latex
\usepackage{sectsty}
```

### Example

```latex
\sectionfont{\centering}
```

Without this command

```
Introduction
```

With this command

```
            Introduction
```

Only the **main section titles** are centered.

---

# 8. Unnumbered Sections

Some pages, such as References or Appendix, normally do not require numbering.

Use

```latex
\section*{References}
```

instead of

```latex
\section{References}
```

This removes the section number while keeping the same title style.

---

# 9. Add Unnumbered Sections to the Table of Contents

The command

```latex
\section*{}
```

does **not** automatically appear in the table of contents.

To add it manually,

```latex
\addcontentsline{toc}{section}{References}
```

### Complete example

```latex
\section*{References}

\addcontentsline{toc}{section}{References}
```

This allows the title to appear in the table of contents even though it has no section number.

---

# 10. Appendix

Appendices are usually placed after the references.

### Example

```latex
\appendix

\section{MATLAB Scripts}
```

LaTeX automatically changes the numbering style.

Output

```
Appendix A

MATLAB Scripts
```

The following appendix becomes

```
Appendix B
```

---

# 11. Typical Engineering Report Structure

The report template in this repository follows the structure below.

```text
Title Page

↓

Assignment Cover Page

↓

Own Work Declaration

↓

Table of Contents

↓

Introduction

↓

Methodology

↓

Results

↓

Discussion

↓

Conclusion

↓

References

↓

Appendix
```

This structure is suitable for most engineering laboratory reports, assignments, final year projects, and research reports. But how you can struct your paper still needs to follow the guidance of your supervisor and relative documents.

---

# Summary

| Command | Description |
|----------|-------------|
| `\onehalfspacing` | Set 1.5 line spacing |
| `\newpage` | Start a new page |
| `\tableofcontents` | Generate table of contents |
| `\section{}` | Main section |
| `\subsection{}` | Subsection |
| `\subsubsection{}` | Third-level section |
| `\section*{}` | Unnumbered section |
| `\addcontentsline{}` | Add manual entry to TOC |
| `\sectionfont{\centering}` | Center all section titles |
| `\appendix` | Start appendix |
