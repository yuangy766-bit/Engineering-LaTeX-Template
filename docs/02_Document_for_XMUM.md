# Document for XMUM

This section contains LaTeX code and resources commonly used for academic reports and assignments at Xiamen University Malaysia.

The examples below are based on formats I have used during my undergraduate studies.

> Note: Always check the latest requirements provided by your lecturer or faculty before submission.

---
## Table of Contents

- [1. Title Page](#1-title-page)

- [2. Assignment Cover Page](#2-assignment-cover-page)

- [3. Student Information](#3-student-information)

- [4. Date Received](#4-date-received)

- [5. Lecturer Feedback Box](#5-lecturer-feedback-box)

- [6. Own Work Declaration](#6-own-work-declaration)

- [7. Signature](#7-signature)

- [8. Date](#8-date)

## 1. Report Title Page

A simple title page can be created using the `titlepage` environment.

```latex
\begin{titlepage}
    \centering

    \includegraphics[width=0.8\textwidth]{22.png}

    \vfill

    {\Huge\bfseries
    Type here your report name
    \par}

    \vspace{0.3cm}

    \vfill

    {\large
    Programme: Your Major
    \par}

    \vspace{0.35cm}

    {\large
    Academic Session: 202604
    \par}

\end{titlepage}
```

### Main elements

```latex
\begin{titlepage}
...
\end{titlepage}
```

Creates an independent title page.

```latex
\centering
```

Centers the content.

```latex
\includegraphics[width=0.8\textwidth]{22.png}
```

Adds a cover image or university-related graphic.

```latex
\vfill
```

Automatically distributes vertical space between different parts of the title page.

```latex
{\Huge\bfseries Title\par}
```

Creates a large bold title.

---

## 2. XMUM Assignment Cover Page

The following code reproduces the commonly used XMUM assignment cover page structure.

### Required Packages

```latex
\usepackage{graphicx}
\usepackage{array}
\usepackage{tikz}
\usepackage{float}
```

### University Logo

```latex
\vspace{-5em}

\begin{figure}[H]
    \centering
    \includegraphics[width=0.3\linewidth]{xmum-logo.jpg}
\end{figure}
```

---

### Course Information

```latex
\begin{tabular}{ll}

Course Code
& : \underline{EEE401 \hspace{8.5cm}} \\

Course Name
& : \underline{Statistical and Numerical Techniques \hspace{5cm}} \\

Lecturer
& : \underline{Ir. Ts. Dr. XXXXX \hspace{8cm}} \\

Academic Session
& : \underline{202604 \hspace{9cm}} \\

Assessment Title
& : \underline{Assignment \hspace{8cm}} \\

Submission Due Date
& : \underline{10/7/2026 \hspace{8cm}} \\

Prepared by
& :

\end{tabular}
```

You only need to replace the information according to your own course.

---

## 3. Student Information Table

For individual or group assignments, student information can be included using a table.

```latex
\vspace{-2.5em}

\begin{table}[H]

    \hspace{13em}

    \begin{tabular}{
        |>{\centering\arraybackslash}p{9em}
        |>{\centering\arraybackslash}p{12.5em}|
    }

        \hline

        \textbf{Student ID}
        &
        \textbf{Student Name}
        \\

        \hline

        EEE2300000
        &
        STUDENT NAME
        \\

        \hline

        EEE2300001
        &
        STUDENT NAME
        \\

        \hline

        &
        \\

        \hline

    \end{tabular}

\end{table}
```

Additional rows can be added depending on the number of group members.

---

## 4. Date Received

```latex
\begin{tabular}{ll}

Data Received
& : \underline{\hspace{27em}}

\end{tabular}
```

---

## 5. Lecturer Feedback and Mark Box

The feedback area can be recreated using TikZ.

```latex
\begin{center}

\begin{tikzpicture}

    \draw[thick] (-1,0) rectangle (12.5,5);

    \node at (1,4.75)
    {Feedback from Lecturer:};

    \draw[thick]
    (10.5,0) rectangle (12.5,2);

    \node at (11.5,1.5)
    {Mark:};

\end{tikzpicture}

\end{center}
```

This creates:

- a large lecturer feedback area;
- a separate mark box.

---

# 6. Own Work Declaration

An Own Work Declaration page can be placed after the assignment cover page.

```latex
\newpage

\vspace{5em}

\begin{center}
    {\Huge\bfseries Own Work Declaration}
\end{center}

\vspace{2em}
```

The declaration text can then be placed inside a `flushleft` environment.

```latex
\begin{flushleft}

I/We hereby understand my/our work would be checked for
plagiarism or other misconduct, and the softcopy would be
saved for future comparison(s).

\vspace{1em}

I/We hereby confirm that all the references or sources of
citations have been correctly listed or presented and I/we
clearly understand the serious consequence caused by any
intentional or unintentional misconduct.

\vspace{1em}

This work is not made on any work of other students
(past or present), and it has not been submitted to any
other courses or institutions before.

\end{flushleft}
```

---

## 7. Signature

A scanned or digital signature can be inserted as an image.

### Single Signature

```latex
\vspace{3em}

Signature

\begin{figure}[H]
    \centering
    \includegraphics[width=0.2\textwidth]{signature.png}
\end{figure}
```

### Multiple Signatures

For group assignments:

```latex
\begin{figure}[H]
    \centering

    \includegraphics[width=0.2\textwidth]{signature1.png}
    \hspace{0.05\textwidth}

    \includegraphics[width=0.2\textwidth]{signature2.png}
    \hspace{0.05\textwidth}

    \includegraphics[width=0.2\textwidth]{signature3.png}

\end{figure}
```

---

## 8. Date

```latex
Date: 30 / 6 / 2026
```

or automatically:

```latex
Date: \today
```

---


## Notes

The university logo and other official university assets remain the property of Xiamen University Malaysia / Xiamen University.

Two kinds of logos are used in the document for XMUM, I have also updated the photos of them which named as 22.png and 厦大校徽.jpg. 

The LaTeX code in this repository is provided as a practical implementation for academic use and is not an official university template unless explicitly stated otherwise.
