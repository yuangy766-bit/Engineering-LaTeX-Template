# References and Bibliography

## Overview

A bibliography is used to manage references automatically in LaTeX. Instead of typing every reference manually, LaTeX reads all references from a `.bib` file and generates the bibliography according to the selected citation style.

Advantages of using BibTeX include:

- Automatic reference numbering
- Automatic sorting
- Consistent citation format
- Easy to switch between different citation styles
- Suitable for large reports, dissertations, and journal papers

---

# 1. What is BibTeX?

BibTeX is a bibliography management tool used together with LaTeX.

Normally, a project contains two files:

```
main.tex
reference.bib
```

- `main.tex` contains the report.
- `reference.bib` stores all reference information.

---

# 2. Creating a BibTeX File

A BibTeX entry usually looks like this.

```bibtex
@article{smith2023,

  author  = {John Smith},

  title   = {Deep Learning for Defect Detection},

  journal = {IEEE Access},

  volume  = {11},

  number  = {5},

  pages   = {1234--1245},

  year    = {2023},

  doi     = {10.1109/XXXX.2023.1234567}

}
```

---

# 3. Common BibTeX Entry Types

| Type | Description |
|------|-------------|
| article | Journal paper |
| inproceedings | Conference paper |
| book | Book |
| misc | Website |
| thesis | Master's or PhD thesis |
| manual | User manual |
| techreport | Technical report |

---

# 4. Common Fields

| Field | Meaning |
|--------|---------|
| author | Author name |
| title | Paper title |
| journal | Journal name |
| booktitle | Conference name |
| year | Publication year |
| volume | Journal volume |
| number | Issue number |
| pages | Page numbers |
| publisher | Publisher |
| doi | DOI number |
| url | Website |

---

# 5. Citation

Use the `\cite{}` command to cite a reference.

Example:

```latex
According to \cite{smith2023}, deep learning has become widely used in defect detection.
```

Multiple citations:

```latex
\cite{paper1,paper2,paper3}
```

The output depends on the selected bibliography style.

Example (IEEE):

```
According to [1], ...
```

---

# 6. Creating the Bibliography

At the end of the document, add

```latex
\bibliographystyle{IEEEtran}
\bibliography{reference}
```

where

- `IEEEtran` specifies the bibliography style.
- `reference` is the BibTeX filename without `.bib`.

---

# 7. IEEE Citation Style

IEEE is the most commonly used citation style in Electrical and Electronic Engineering.

```latex
\bibliographystyle{IEEEtran}
\bibliography{reference}
```

Citation example

```latex
According to \cite{smith2023}, ...
```

Output

```
According to [1], ...
```

Reference list

```
[1] J. Smith, ...
```

Suitable for

- Electrical Engineering
- Electronics
- Computer Engineering
- IEEE journals
- XMUM EEE reports

---

# 8. APA Citation Style

APA is widely used in social sciences and business.

```latex
\bibliographystyle{apalike}
\bibliography{reference}
```

Citation

```latex
According to \cite{smith2023}, ...
```

Output

```
According to (Smith, 2023)
```

Reference

```
Smith, J. (2023) ...
```

Suitable for

- Psychology
- Education
- Business
- Social Science

---

# 9. Switching Citation Styles

Only one line needs to be changed.

IEEE

```latex
\bibliographystyle{IEEEtran}
```

APA

```latex
\bibliographystyle{apalike}
```

Other common styles

```latex
plain
unsrt
alpha
abbrv
IEEEtran
apalike
```

---

# 10. Obtaining BibTeX References

Most publishers provide BibTeX entries.

Common sources include:

- Google Scholar
- IEEE Xplore
- ScienceDirect
- Springer
- ACM Digital Library

Simply copy the BibTeX entry into `reference.bib`.

---

# 11. Complete Example

Project structure

```
Project/

├── main.tex

├── reference.bib
```

main.tex

```latex
According to \cite{smith2023}, ...

...

\bibliographystyle{IEEEtran}

\bibliography{reference}
```

reference.bib

```bibtex
@article{smith2023,
  ...
}
```

Compile sequence

```
LaTeX

↓

BibTeX

↓

LaTeX

↓

LaTeX
```

The bibliography will then be generated automatically.
