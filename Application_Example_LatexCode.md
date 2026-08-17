```latex
\documentclass[12pt,a4paper]{article}

\usepackage[margin=1in]{geometry}
\usepackage{amsmath,amssymb,mathtools}
\usepackage{siunitx}
\usepackage{booktabs}
\usepackage{array}
\usepackage{graphicx}
\usepackage{tikz}
\usepackage{circuitikz}
\usepackage{float}
\usepackage{xcolor}
\usepackage{enumitem}
\usepackage{microtype}

\sisetup{
  per-mode=symbol,
  separate-uncertainty=true,
  exponent-product=\cdot
}

\newcommand{\jmathunit}{\mathrm{j}}
\newcommand{\degree}{^{\circ}}
\newcommand{\polar}[2]{#1\angle #2^{\circ}}

\title{\textbf{Revision Questions and Detailed Solutions}}
\author{}
\date{}

\begin{document}

\maketitle
\tableofcontents
\newpage

%===========================================================

\section{Question 1: Transmission Lines}

\subsection*{Original Question}

\begin{quote}
\small
The input impedance \(Z_{\mathrm{in}}\), terminated by a load impedance
\(Z_L\), for a lossless transmission line of length \(l\) is

\begin{equation}
Z_{\mathrm{in}}
=
Z_0
\frac{Z_L+\jmathunit Z_0\tan(\beta l)}
{Z_0+\jmathunit Z_L\tan(\beta l)}.
\end{equation}

\begin{enumerate}[label=\alph*)]
\item Determine the electrical length of a \(\SI{1.5}{\metre}\) lossless
transmission line if the phase constant is
\(\SI{4}{\radian\per\metre}\).

\item Interpret the expression for \(Z_{\mathrm{in}}\) when the load
impedance \(Z_L\) is:
\begin{enumerate}[label=\roman*.]
\item a matched load;
\item a short circuit;
\item an open circuit.
\end{enumerate}

\item If the characteristic impedance and load impedance are
\[
Z_0=\SI{50}{\ohm},
\qquad
Z_L=83-\jmathunit25~\si{\ohm},
\]
calculate:
\begin{enumerate}[label=\roman*.]
\item the absolute load impedance;
\item the load reflection coefficient;
\item the load VSWR;
\item the load return loss.
\end{enumerate}

\item An inductance of \(\SI{88}{\nano\henry}\) is to be created in a
\(\SI{50}{\ohm}\) lossless microstrip line by using a short-circuited stub
at a frequency of \(\SI{1.2}{\giga\hertz}\). If the propagation velocity
is \(2.7\times10^8~\si{\metre\per\second}\), calculate the required stub
length.
\end{enumerate}
\end{quote}

\subsection*{Detailed Solution}


For a lossless transmission line, the input impedance is

\begin{equation}
Z_{\mathrm{in}}
=
Z_0
\frac{Z_L+\jmathunit Z_0\tan(\beta l)}
{Z_0+\jmathunit Z_L\tan(\beta l)}.
\end{equation}

Here, \(Z_0\) is the characteristic impedance, \(Z_L\) is the load
impedance, \(\beta\) is the phase constant, and \(l\) is the physical
length of the transmission line.

%-----------------------------------------------------------
\subsection{Electrical length}

Given

\begin{equation}
l=\SI{1.5}{\metre},
\qquad
\beta=\SI{4}{\radian\per\metre},
\end{equation}

the electrical length is

\begin{equation}
\theta=\beta l.
\end{equation}

Therefore,

\begin{align}
\theta
&=
\left(\SI{4}{\radian\per\metre}\right)
\left(\SI{1.5}{\metre}\right)
\\
&=
\SI{6}{\radian}.
\end{align}

In degrees,

\begin{align}
\theta
&=
6\left(\frac{180\degree}{\pi}\right)
\\
&=
343.77\degree.
\end{align}

Hence,

\begin{equation}
\boxed{\theta=\SI{6}{\radian}=343.77\degree.}
\end{equation}

%-----------------------------------------------------------
\subsection{Special load conditions}

\subsubsection{Matched load}

For a matched load,

\begin{equation}
Z_L=Z_0.
\end{equation}

Substituting into the transmission-line equation,

\begin{align}
Z_{\mathrm{in}}
&=
Z_0
\frac{Z_0+\jmathunit Z_0\tan(\beta l)}
{Z_0+\jmathunit Z_0\tan(\beta l)}
\\
&=
Z_0.
\end{align}

Thus,

\begin{equation}
\boxed{Z_{\mathrm{in}}=Z_0.}
\end{equation}

A matched line has no reflected wave, so the input impedance is independent
of line length.

\subsubsection{Short-circuit load}

For a short circuit,

\begin{equation}
Z_L=0.
\end{equation}

Then

\begin{align}
Z_{\mathrm{in}}
&=
Z_0
\frac{\jmathunit Z_0\tan(\beta l)}
{Z_0}
\\
&=
\jmathunit Z_0\tan(\beta l).
\end{align}

Therefore,

\begin{equation}
\boxed{Z_{\mathrm{in}}=\jmathunit Z_0\tan(\beta l).}
\end{equation}

The input is purely reactive. For a short stub shorter than
\(\lambda/4\), the input behaves inductively.

\subsubsection{Open-circuit load}

For an open circuit,

\begin{equation}
Z_L\rightarrow\infty.
\end{equation}

Dividing the numerator and denominator by \(Z_L\),

\begin{align}
Z_{\mathrm{in}}
&=
Z_0
\frac{1+\jmathunit(Z_0/Z_L)\tan(\beta l)}
{(Z_0/Z_L)+\jmathunit\tan(\beta l)}
\\
&=
\frac{Z_0}{\jmathunit\tan(\beta l)}
\\
&=
-\jmathunit Z_0\cot(\beta l).
\end{align}

Hence,

\begin{equation}
\boxed{Z_{\mathrm{in}}=-\jmathunit Z_0\cot(\beta l).}
\end{equation}

The open-circuit stub is also purely reactive.

%-----------------------------------------------------------
\subsection{Load calculations for \(Z_0=\SI{50}{\ohm}\) and
\(Z_L=83-\jmathunit25~\si{\ohm}\)}

\subsubsection{Absolute load impedance}

\begin{align}
\lvert Z_L\rvert
&=
\sqrt{83^2+(-25)^2}
\\
&=
\sqrt{7514}
\\
&=
\SI{86.68}{\ohm}.
\end{align}

Therefore,

\begin{equation}
\boxed{\lvert Z_L\rvert=\SI{86.68}{\ohm}.}
\end{equation}

The phase of the impedance is

\begin{align}
\angle Z_L
&=
\tan^{-1}\left(\frac{-25}{83}\right)
\\
&=
-16.77\degree,
\end{align}

so

\begin{equation}
Z_L=\polar{86.68}{-16.77}~\si{\ohm}.
\end{equation}

\subsubsection{Load reflection coefficient}

The load reflection coefficient is

\begin{equation}
\Gamma_L
=
\frac{Z_L-Z_0}{Z_L+Z_0}.
\end{equation}

Substituting,

\begin{align}
\Gamma_L
&=
\frac{(83-\jmathunit25)-50}
{(83-\jmathunit25)+50}
\\
&=
\frac{33-\jmathunit25}{133-\jmathunit25}.
\end{align}

Multiplying numerator and denominator by the complex conjugate
\(133+\jmathunit25\),

\begin{align}
\Gamma_L
&=
\frac{(33-\jmathunit25)(133+\jmathunit25)}
{133^2+25^2}
\\
&=
0.2738-\jmathunit0.1365.
\end{align}

Its magnitude is

\begin{align}
\lvert\Gamma_L\rvert
&=
\sqrt{0.2738^2+(-0.1365)^2}
\\
&=
0.3059,
\end{align}

and its phase is

\begin{align}
\angle\Gamma_L
&=
\tan^{-1}\left(\frac{-0.1365}{0.2738}\right)
\\
&=
-26.50\degree.
\end{align}

Therefore,

\begin{equation}
\boxed{
\Gamma_L
=
0.2738-\jmathunit0.1365
=
\polar{0.3059}{-26.50}.
}
\end{equation}

\subsubsection{Voltage standing-wave ratio}

\begin{equation}
\mathrm{VSWR}
=
\frac{1+\lvert\Gamma_L\rvert}
{1-\lvert\Gamma_L\rvert}.
\end{equation}

Thus,

\begin{align}
\mathrm{VSWR}
&=
\frac{1+0.3059}{1-0.3059}
\\
&=
1.8815.
\end{align}

Hence,

\begin{equation}
\boxed{\mathrm{VSWR}\approx1.88:1.}
\end{equation}

\subsubsection{Return loss}

\begin{equation}
RL=-20\log_{10}\lvert\Gamma_L\rvert.
\end{equation}

Therefore,

\begin{align}
RL
&=
-20\log_{10}(0.3059)
\\
&=
\SI{10.29}{\decibel}.
\end{align}

Hence,

\begin{equation}
\boxed{RL=\SI{10.29}{\decibel}.}
\end{equation}

%-----------------------------------------------------------
\subsection{Short-circuited stub used as an inductor}

For a short-circuited lossless stub,

\begin{equation}
Z_{\mathrm{in}}
=
\jmathunit Z_0\tan(\beta l).
\end{equation}

To emulate an inductance \(L\),

\begin{equation}
Z_{\mathrm{in}}=\jmathunit\omega L.
\end{equation}

Equating the two expressions,

\begin{equation}
Z_0\tan(\beta l)=\omega L.
\end{equation}

Hence,

\begin{equation}
\tan(\beta l)=\frac{\omega L}{Z_0}.
\end{equation}

Given

\begin{equation}
L=\SI{88}{\nano\henry},
\quad
Z_0=\SI{50}{\ohm},
\quad
f=\SI{1.2}{\giga\hertz},
\quad
v_p=\SI{2.7e8}{\metre\per\second},
\end{equation}

\begin{align}
\omega
&=
2\pi f
=
2\pi(1.2\times10^9)
\\
&=
7.5398\times10^9~\si{\radian\per\second}.
\end{align}

Then

\begin{align}
\frac{\omega L}{Z_0}
&=
\frac{(7.5398\times10^9)(88\times10^{-9})}{50}
\\
&=
13.2701.
\end{align}

Therefore,

\begin{align}
\beta l
&=
\tan^{-1}(13.2701)
\\
&=
1.4956~\si{\radian}
\\
&=
85.69\degree.
\end{align}

The phase constant is

\begin{align}
\beta
&=
\frac{\omega}{v_p}
=
\frac{2\pi f}{v_p}
\\
&=
\frac{2\pi(1.2\times10^9)}
{2.7\times10^8}
\\
&=
27.9253~\si{\radian\per\metre}.
\end{align}

Hence,

\begin{align}
l
&=
\frac{1.4956}{27.9253}
\\
&=
0.05356~\si{\metre}.
\end{align}

Therefore,

\begin{equation}
\boxed{l=\SI{53.56}{\milli\metre}.}
\end{equation}

The shortest positive solution is used. Other solutions differ by
integer multiples of \(\lambda/2\).

%===========================================================
\newpage
\section{Question 2: Ideal Directional Coupler}

\subsection*{Original Question}

\begin{quote}
\small
Figures 1(a) and 1(b) in the question paper illustrate an ideal
\(\SI{10}{\decibel}\) directional coupler and its equivalent scattering
matrix. The phase is \(\phi=90\degree\), and, for excitation at port 1,

\[
V_1=V,
\qquad
V_2=-\jmathunit\sqrt{1-k^2}\,V,
\qquad
V_3=0,
\qquad
V_4=kV.
\]

Interpret the values of the scattering-matrix elements:

\begin{enumerate}[label=(\roman*)]
\item if all four ports are perfectly matched;
\item if all four ports are symmetrical;
\item if ports 1 and 3, and ports 2 and 4, are isolated from one another;
\item and hence write the full \(S\)-matrix.
\end{enumerate}
\end{quote}

\subsection*{Detailed Solution}


A \SI{10}{\decibel} directional coupler has voltage coupling coefficient

\begin{align}
k
&=
10^{-C_{\mathrm{dB}}/20}
\\
&=
10^{-10/20}
\\
&=
0.3162.
\end{align}

The through coefficient is

\begin{align}
t
&=
\sqrt{1-k^2}
\\
&=
\sqrt{1-0.3162^2}
\\
&=
0.9487.
\end{align}

For excitation at port 1,

\begin{equation}
V_1=V,
\qquad
V_2=-\jmathunit tV,
\qquad
V_3=0,
\qquad
V_4=kV.
\end{equation}

%-----------------------------------------------------------
\subsection{All four ports perfectly matched}

Perfect matching means that no wave is reflected back into the same port.
Therefore,

\begin{equation}
\boxed{
S_{11}=S_{22}=S_{33}=S_{44}=0.
}
\end{equation}

%-----------------------------------------------------------
\subsection{All four ports symmetrical}

For a reciprocal, symmetrical four-port coupler, corresponding transmission
coefficients are equal:

\begin{equation}
S_{12}=S_{21}=S_{34}=S_{43},
\end{equation}

and

\begin{equation}
S_{14}=S_{41}=S_{23}=S_{32}.
\end{equation}

For the stated phase convention,

\begin{equation}
S_{12}=S_{21}=S_{34}=S_{43}=-\jmathunit\sqrt{1-k^2},
\end{equation}

and

\begin{equation}
S_{14}=S_{41}=S_{23}=S_{32}=k.
\end{equation}

%-----------------------------------------------------------
\subsection{Isolated port pairs}

The isolated port pairs are ports \(1\) and \(3\), and ports \(2\) and \(4\).
Thus,

\begin{equation}
\boxed{
S_{13}=S_{31}=S_{24}=S_{42}=0.
}
\end{equation}

%-----------------------------------------------------------
\subsection{Full scattering matrix}

The full ideal scattering matrix is

\begin{equation}
[S]
=
\begin{bmatrix}
0 & -\jmathunit\sqrt{1-k^2} & 0 & k\\
-\jmathunit\sqrt{1-k^2} & 0 & k & 0\\
0 & k & 0 & -\jmathunit\sqrt{1-k^2}\\
k & 0 & -\jmathunit\sqrt{1-k^2} & 0
\end{bmatrix}.
\end{equation}

Using \(k=0.3162\) and \(\sqrt{1-k^2}=0.9487\),

\begin{equation}
\boxed{
[S]
=
\begin{bmatrix}
0 & -\jmathunit0.9487 & 0 & 0.3162\\
-\jmathunit0.9487 & 0 & 0.3162 & 0\\
0 & 0.3162 & 0 & -\jmathunit0.9487\\
0.3162 & 0 & -\jmathunit0.9487 & 0
\end{bmatrix}.
}
\end{equation}

This matrix is matched, reciprocal, lossless, symmetrical, and directional.

%-----------------------------------------------------------
\subsection{Directional-coupler port layout}

Figure~\ref{fig:q2-coupler} shows the port convention consistent with the
given excitation. Port 1 is the input port, port 2 is the through port,
port 3 is the isolated port, and port 4 is the coupled port.

\begin{figure}[H]
\centering
\begin{tikzpicture}[scale=1.0]
    % Coupled-line region
    \draw[rounded corners, thick] (0.4,-0.45) rectangle (6.6,1.65);
    \node at (3.5,1.38) {Ideal directional-coupler region};

    % Main and coupled lines
    \draw[very thick] (-0.8,1.0) -- (7.8,1.0);
    \draw[very thick] (-0.8,0.0) -- (7.8,0.0);

    % Port labels
    \node[left]  at (-0.8,1.0) {Port 1};
    \node[right] at (7.8,1.0) {Port 2};
    \node[left]  at (-0.8,0.0) {Port 3};
    \node[right] at (7.8,0.0) {Port 4};

    % Signal arrows and values
    \draw[->,thick] (-1.9,1.0) -- (-0.9,1.0);
    \node[above] at (-1.4,1.0) {\(V_1=V\)};

    \draw[->,thick] (6.9,1.0) -- (7.7,1.0);
    \node[above] at (7.25,1.0) {\(V_2=-\jmathunit tV\)};

    \node[below] at (-0.8,-0.05) {\(V_3=0\)};
    \draw[->,thick] (6.9,0.0) -- (7.7,0.0);
    \node[below] at (7.25,0.0) {\(V_4=kV\)};

    % Coupling indication
    \draw[->,dashed] (3.5,0.90) -- (3.5,0.12);
    \node[right] at (3.55,0.50) {coupling};
\end{tikzpicture}
\caption{Port layout of the ideal directional coupler used in Question 2.}
\label{fig:q2-coupler}
\end{figure}

%===========================================================
\newpage
\section{Question 3: Directional Coupler and Wilkinson Divider}

\subsection*{Original Question}

\begin{quote}
\small
\textbf{Part A: Coupled-line directional coupler}

A matched \(\SI{12}{\decibel}\) microstrip directional coupler is
fabricated on a substrate with relative permittivity
\(\varepsilon_r=12\) and thickness \(h=\SI{0.19}{\milli\metre}\).
All ports are terminated in \(\SI{50}{\ohm}\). Determine:

\begin{enumerate}[label=(\roman*)]
\item the coupling coefficient \(k\);
\item the even-mode and odd-mode characteristic impedances;
\item the widths of the even-mode and odd-mode microstrip lines.
\end{enumerate}

\medskip
\textbf{Part B: Wilkinson power divider}

A \(\SI{3}{\decibel}\) Wilkinson power splitter is designed to operate at
\(\SI{2.4}{\giga\hertz}\). The substrate has
\(\varepsilon_r=9.8\) and \(h=\SI{1.88}{\milli\metre}\), and all port
impedances are \(\SI{50}{\ohm}\). Determine:

\begin{enumerate}[label=(\roman*)]
\item the impedances of the quarter-wave sections;
\item the widths of the input and output lines;
\item the width of the quarter-wave transformer;
\item the effective dielectric constant of the transformer;
\item the physical length of the quarter-wave transformer.
\end{enumerate}
\end{quote}

\subsection*{Detailed Solution}


\subsection{Part A: \SI{12}{\decibel} coupled-line directional coupler}

Given

\begin{equation}
C=\SI{12}{\decibel},
\qquad
Z_0=\SI{50}{\ohm},
\qquad
\varepsilon_r=12,
\qquad
h=\SI{0.19}{\milli\metre}.
\end{equation}

\subsubsection{Coupling coefficient}

\begin{align}
k
&=
10^{-C/20}
\\
&=
10^{-12/20}
\\
&=
0.2512.
\end{align}

Therefore,

\begin{equation}
\boxed{k=0.2512.}
\end{equation}

\subsubsection{Even-mode and odd-mode impedances}

For a symmetrical coupled-line coupler,

\begin{equation}
Z_{0e}
=
Z_0\sqrt{\frac{1+k}{1-k}},
\end{equation}

and

\begin{equation}
Z_{0o}
=
Z_0\sqrt{\frac{1-k}{1+k}}.
\end{equation}

Thus,

\begin{align}
Z_{0e}
&=
50\sqrt{\frac{1+0.2512}{1-0.2512}}
\\
&=
\SI{64.63}{\ohm},
\end{align}

and

\begin{align}
Z_{0o}
&=
50\sqrt{\frac{1-0.2512}{1+0.2512}}
\\
&=
\SI{38.68}{\ohm}.
\end{align}

Therefore,

\begin{equation}
\boxed{
Z_{0e}=\SI{64.63}{\ohm},
\qquad
Z_{0o}=\SI{38.68}{\ohm}.
}
\end{equation}

A useful check is

\begin{align}
\sqrt{Z_{0e}Z_{0o}}
&=
\sqrt{(64.63)(38.68)}
\\
&\approx
\SI{50}{\ohm}.
\end{align}

\subsubsection{Approximate microstrip widths}

The Hammerstad inversion is used to estimate the microstrip width.
First,

\begin{equation}
A
=
\frac{Z_0}{60}\sqrt{\frac{\varepsilon_r+1}{2}}
+
\frac{\varepsilon_r-1}{\varepsilon_r+1}
\left(
0.23+\frac{0.11}{\varepsilon_r}
\right).
\end{equation}

For \(w/h\leq2\),

\begin{equation}
\frac{w}{h}
=
\frac{8e^A}{e^{2A}-2}.
\end{equation}

For the even-mode impedance,

\begin{equation}
\left(\frac{w}{h}\right)_e
\approx0.4216.
\end{equation}

Therefore,

\begin{align}
w_e
&=
0.4216(0.19)
\\
&=
\SI{0.0801}{\milli\metre}.
\end{align}

For the odd-mode impedance,

\begin{equation}
\left(\frac{w}{h}\right)_o
\approx1.3292.
\end{equation}

Therefore,

\begin{align}
w_o
&=
1.3292(0.19)
\\
&=
\SI{0.2526}{\milli\metre}.
\end{align}

Hence,

\begin{equation}
\boxed{
w_e\approx\SI{0.080}{\milli\metre},
\qquad
w_o\approx\SI{0.253}{\milli\metre}.
}
\end{equation}

These are first-order uncoupled microstrip estimates. A practical
edge-coupled coupler must also determine the line spacing, and an EM
simulator is normally used for final optimisation because even-mode and
odd-mode impedances depend on both \(w/h\) and \(s/h\).

%-----------------------------------------------------------
\subsection{Part B: \SI{3}{\decibel} Wilkinson power divider}

Given

\begin{equation}
f_0=\SI{2.4}{\giga\hertz},
\qquad
Z_0=\SI{50}{\ohm},
\qquad
\varepsilon_r=9.8,
\qquad
h=\SI{1.88}{\milli\metre}.
\end{equation}

\subsubsection{Quarter-wave branch impedances}

For an equal-split Wilkinson divider,

\begin{equation}
Z_{\lambda/4}
=
\sqrt{2}Z_0.
\end{equation}

Thus,

\begin{align}
Z_{\lambda/4}
&=
\sqrt{2}(50)
\\
&=
\SI{70.71}{\ohm}.
\end{align}

The isolation resistor is

\begin{equation}
R=2Z_0=\SI{100}{\ohm}.
\end{equation}

Therefore,

\begin{equation}
\boxed{
Z_{\lambda/4}=\SI{70.71}{\ohm},
\qquad
R=\SI{100}{\ohm}.
}
\end{equation}

\subsubsection{Widths of the input and output lines}

The input and output lines are \(\SI{50}{\ohm}\) lines. Using the
Hammerstad inversion,

\begin{equation}
\frac{w_{50}}{h}\approx0.9752.
\end{equation}

Therefore,

\begin{align}
w_{50}
&=
0.9752(1.88)
\\
&=
\SI{1.833}{\milli\metre}.
\end{align}

Hence,

\begin{equation}
\boxed{w_{\mathrm{in}}=w_{\mathrm{out}}\approx\SI{1.83}{\milli\metre}.}
\end{equation}

\subsubsection{Width of each quarter-wave transformer}

For \(Z_{\lambda/4}=\SI{70.71}{\ohm}\),

\begin{equation}
\frac{w_t}{h}\approx0.4274.
\end{equation}

Thus,

\begin{align}
w_t
&=
0.4274(1.88)
\\
&=
\SI{0.803}{\milli\metre}.
\end{align}

Therefore,

\begin{equation}
\boxed{w_t\approx\SI{0.803}{\milli\metre}.}
\end{equation}

\subsubsection{Effective dielectric constant}

For \(w/h<1\), a common approximation is

\begin{equation}
\varepsilon_{\mathrm{eff}}
=
\frac{\varepsilon_r+1}{2}
+
\frac{\varepsilon_r-1}{2}
\left(
1+\frac{12h}{w}
\right)^{-1/2}.
\end{equation}

Using \(w/h=0.4274\),

\begin{align}
\varepsilon_{\mathrm{eff}}
&=
\frac{9.8+1}{2}
+
\frac{9.8-1}{2}
\left(
1+\frac{12}{0.4274}
\right)^{-1/2}
\\
&=
6.216.
\end{align}

Therefore,

\begin{equation}
\boxed{\varepsilon_{\mathrm{eff}}\approx6.216.}
\end{equation}

\subsubsection{Physical length of the quarter-wave transformer}

The guided wavelength is

\begin{equation}
\lambda_g
=
\frac{c}{f_0\sqrt{\varepsilon_{\mathrm{eff}}}}.
\end{equation}

Thus,

\begin{align}
\lambda_g
&=
\frac{3.0\times10^8}
{(2.4\times10^9)\sqrt{6.216}}
\\
&=
\SI{50.14}{\milli\metre}.
\end{align}

Therefore,

\begin{align}
l_{\lambda/4}
&=
\frac{\lambda_g}{4}
\\
&=
\SI{12.53}{\milli\metre}.
\end{align}

Hence,

\begin{equation}
\boxed{l_{\lambda/4}\approx\SI{12.53}{\milli\metre}.}
\end{equation}

%-----------------------------------------------------------
\subsubsection{Wilkinson power-divider layout}

The calculated dimensions can be arranged as shown in
Figure~\ref{fig:q3-wilkinson}. Each branch is a
\(\SI{70.71}{\ohm}\), quarter-wave microstrip section. The
\(\SI{100}{\ohm}\) resistor connects the two output ports and provides
isolation when the output signals are unequal.

\begin{figure}[H]
\centering
\begin{tikzpicture}[x=1cm,y=1cm]
    % Input line and split
    \draw[very thick] (-1.0,0) -- (1.3,0);
    \fill (1.3,0) circle (2pt);

    % Quarter-wave branches
    \draw[very thick] (1.3,0) -- (3.0,1.35) -- (6.5,1.35);
    \draw[very thick] (1.3,0) -- (3.0,-1.35) -- (6.5,-1.35);

    % Output lines
    \draw[very thick] (6.5,1.35) -- (8.2,1.35);
    \draw[very thick] (6.5,-1.35) -- (8.2,-1.35);

    % Isolation resistor
    \draw[thick] (6.5,1.35) -- (6.5,0.82);
    \node[draw,minimum width=0.78cm,minimum height=1.55cm,align=center]
        at (6.5,0) {\(R\)\\\(\SI{100}{\ohm}\)};
    \draw[thick] (6.5,-0.82) -- (6.5,-1.35);

    % Port labels
    \node[left] at (-1.0,0) {Port 1};
    \node[right] at (8.2,1.35) {Port 2};
    \node[right] at (8.2,-1.35) {Port 3};

    % Impedance and dimension labels
    \node[above] at (0.1,0.05)
        {\(\SI{50}{\ohm},\; w\approx\SI{1.83}{\milli\metre}\)};

    \node[above,align=center] at (4.5,1.35)
        {\(\SI{70.71}{\ohm}\), \(w_t\approx\SI{0.803}{\milli\metre}\)\\
         \(l=\lambda_g/4\approx\SI{12.53}{\milli\metre}\)};

    \node[below,align=center] at (4.5,-1.35)
        {\(\SI{70.71}{\ohm}\), \(w_t\approx\SI{0.803}{\milli\metre}\)\\
         \(l=\lambda_g/4\approx\SI{12.53}{\milli\metre}\)};

    \node[above] at (7.45,1.38) {\(\SI{50}{\ohm}\)};
    \node[below] at (7.45,-1.38) {\(\SI{50}{\ohm}\)};
\end{tikzpicture}
\caption{Layout of the equal-split Wilkinson power divider.}
\label{fig:q3-wilkinson}
\end{figure}

%===========================================================
\newpage
\section{Question 4: Quarter-Wave Transformers}

\subsection*{Original Question}

\begin{quote}
\small
Design a microstrip quarter-wave transformer to match a
\(\SI{50}{\ohm}\) microwave source to a \(\SI{100}{\ohm}\) planar antenna
at \(\SI{3}{\giga\hertz}\). The substrate has relative permittivity
\(\varepsilon_r=9.8\) and thickness \(h=\SI{0.9}{\milli\metre}\).
Calculate:

\begin{enumerate}[label=(\roman*)]
\item the transformer characteristic impedance \(Z_{0T}\);
\item the transformer width \(w\);
\item the effective dielectric constant \(\varepsilon_{\mathrm{eff}}\);
\item the guided wavelength \(\lambda_g\);
\item the physical transformer length;
\item and sketch the circuit layout.
\end{enumerate}

Using the same source, load, substrate, and centre frequency, design a
maximally flat three-section quarter-wave transformer. The adjacent
section impedances satisfy

\begin{equation}
\ln\left(\frac{Z_{n+1}}{Z_n}\right)
=
2^{-N}\binom{N}{n}
\ln\left(\frac{Z_L}{Z_0}\right),
\end{equation}

where

\[
N=\text{number of transformer sections},
\qquad
\binom{N}{n}=\frac{N!}{(N-n)!n!},
\]

\(Z_n\) is the impedance of the \(n\)-th step, \(Z_L\) is the terminating
impedance, and \(Z_0\) is the source impedance.
\end{quote}

\subsection*{Detailed Solution}


\subsection{Single-section transformer}

The source impedance and load impedance are

\begin{equation}
Z_0=\SI{50}{\ohm},
\qquad
Z_L=\SI{100}{\ohm}.
\end{equation}

The operating frequency and substrate parameters are

\begin{equation}
f_0=\SI{3}{\giga\hertz},
\qquad
\varepsilon_r=9.8,
\qquad
h=\SI{0.9}{\milli\metre}.
\end{equation}

\subsubsection{Transformer impedance}

For a quarter-wave transformer,

\begin{equation}
Z_{0T}=\sqrt{Z_0Z_L}.
\end{equation}

Therefore,

\begin{align}
Z_{0T}
&=
\sqrt{(50)(100)}
\\
&=
\SI{70.71}{\ohm}.
\end{align}

Hence,

\begin{equation}
\boxed{Z_{0T}=\SI{70.71}{\ohm}.}
\end{equation}

\subsubsection{Transformer width}

For \(\varepsilon_r=9.8\) and \(Z_{0T}=\SI{70.71}{\ohm}\),

\begin{equation}
\frac{w}{h}\approx0.4274.
\end{equation}

Therefore,

\begin{align}
w
&=
0.4274(0.9)
\\
&=
\SI{0.3846}{\milli\metre}.
\end{align}

Thus,

\begin{equation}
\boxed{w\approx\SI{0.385}{\milli\metre}.}
\end{equation}

\subsubsection{Effective dielectric constant}

\begin{align}
\varepsilon_{\mathrm{eff}}
&=
\frac{9.8+1}{2}
+
\frac{9.8-1}{2}
\left(
1+\frac{12}{0.4274}
\right)^{-1/2}
\\
&=
6.216.
\end{align}

Hence,

\begin{equation}
\boxed{\varepsilon_{\mathrm{eff}}\approx6.216.}
\end{equation}

\subsubsection{Guided wavelength}

\begin{align}
\lambda_g
&=
\frac{c}{f_0\sqrt{\varepsilon_{\mathrm{eff}}}}
\\
&=
\frac{3.0\times10^8}
{(3.0\times10^9)\sqrt{6.216}}
\\
&=
\SI{40.11}{\milli\metre}.
\end{align}

Therefore,

\begin{equation}
\boxed{\lambda_g\approx\SI{40.11}{\milli\metre}.}
\end{equation}

\subsubsection{Transformer length}

\begin{align}
l
&=
\frac{\lambda_g}{4}
\\
&=
\frac{40.11}{4}
\\
&=
\SI{10.03}{\milli\metre}.
\end{align}

Hence,

\begin{equation}
\boxed{l\approx\SI{10.03}{\milli\metre}.}
\end{equation}

\subsubsection{Circuit layout}

\begin{figure}[H]
\centering
\begin{tikzpicture}[x=1cm,y=1cm]
\draw[thick] (0,0) -- (2.2,0);
\draw[very thick] (2.2,0) -- (6.2,0);
\draw[thick] (6.2,0) -- (8.4,0);

\node[above] at (1.1,0.1) {\(\SI{50}{\ohm}\) source line};
\node[above] at (4.2,0.1) {\(\SI{70.71}{\ohm}\), \(l=\lambda_g/4\)};
\node[above] at (7.3,0.1) {\(\SI{100}{\ohm}\) antenna};

\draw[<->] (2.2,-0.65) -- (6.2,-0.65);
\node[below] at (4.2,-0.65) {\(\SI{10.03}{\milli\metre}\)};
\end{tikzpicture}
\caption{Single-section quarter-wave transformer.}
\end{figure}

%-----------------------------------------------------------
\subsection{Three-section maximally flat binomial transformer}

For an \(N=3\) binomial transformer,

\begin{equation}
\ln\left(\frac{Z_{n+1}}{Z_n}\right)
=
2^{-N}
\binom{N}{n}
\ln\left(\frac{Z_L}{Z_0}\right),
\qquad n=0,1,2,3.
\end{equation}

Here,

\begin{equation}
\frac{Z_L}{Z_0}=\frac{100}{50}=2,
\qquad
\ln 2=0.69315.
\end{equation}

The binomial coefficients are

\begin{equation}
\binom{3}{0}=1,
\quad
\binom{3}{1}=3,
\quad
\binom{3}{2}=3,
\quad
\binom{3}{3}=1.
\end{equation}

The first section is

\begin{align}
\ln\left(\frac{Z_1}{50}\right)
&=
\frac{1}{8}\ln 2,
\\
Z_1
&=
50(2)^{1/8}
\\
&=
\SI{54.53}{\ohm}.
\end{align}

The second section is

\begin{align}
\ln\left(\frac{Z_2}{Z_1}\right)
&=
\frac{3}{8}\ln 2,
\\
Z_2
&=
Z_1(2)^{3/8}
\\
&=
\SI{70.71}{\ohm}.
\end{align}

The third section is

\begin{align}
\ln\left(\frac{Z_3}{Z_2}\right)
&=
\frac{3}{8}\ln 2,
\\
Z_3
&=
Z_2(2)^{3/8}
\\
&=
\SI{91.70}{\ohm}.
\end{align}

Finally,

\begin{align}
Z_L
&=
Z_3(2)^{1/8}
\\
&=
\SI{100}{\ohm},
\end{align}

which confirms the design.

The corresponding approximate dimensions are summarised below.

\begin{table}[H]
\centering
\caption{Three-section binomial transformer dimensions.}
\begin{tabular}{ccccc}
\toprule
Section & \(Z_n\) (\(\si{\ohm}\)) & \(w/h\) & \(w\) (\(\si{\milli\metre}\)) &
\(l=\lambda_g/4\) (\(\si{\milli\metre}\))\\
\midrule
1 & 54.53 & 0.8115 & 0.730 & 9.80\\
2 & 70.71 & 0.4274 & 0.385 & 10.03\\
3 & 91.70 & 0.1887 & 0.170 & 10.25\\
\bottomrule
\end{tabular}
\end{table}

Thus,

\begin{equation}
\boxed{
Z_1=\SI{54.53}{\ohm},
\quad
Z_2=\SI{70.71}{\ohm},
\quad
Z_3=\SI{91.70}{\ohm}.
}
\end{equation}

The physical lengths are slightly different because each section has a
different effective dielectric constant.

%===========================================================
\newpage
\section{Question 5: Oscillators and Varactor Diode}

\subsection*{Original Question}

\begin{quote}
\small
\begin{enumerate}[label=\alph*)]
\item Explain the principles of the Nyquist criterion for oscillation.
Also explain how the Colpitts-oscillator feedback network can be used to
select suitable reactive components, namely inductors and capacitors, that
contribute to energy efficiency and environmental sustainability in modern
wireless communication systems.

\item Calculate the oscillation frequency of a Colpitts oscillator using
\[
L=\SI{70}{\nano\henry},
\qquad
C_1=\SI{60}{\pico\farad},
\qquad
C_2=\SI{350}{\pico\farad}.
\]

\item Calculate \(C_1\) for a Colpitts oscillator if
\(C_2=\SI{7}{\nano\farad}\) and the transistor base-current gain is
\(\beta=45\).

\item Calculate the inductance \(L\) required for a Colpitts oscillator to
operate at \(\SI{30}{\mega\hertz}\) using
\[
C_1=\SI{170}{\pico\farad},
\qquad
C_2=\SI{190}{\pico\farad}.
\]

\item A silicon graded-junction PN diode has a junction capacitance of
\(\SI{22}{\pico\farad}\) at zero bias. Determine the reverse-bias voltage
required to obtain a junction capacitance of
\(\SI{13}{\pico\farad}\). Assume the junction potential is
\(\phi=\SI{0.7}{\volt}\) and the grading coefficient is
\(\gamma=0.33\).
\end{enumerate}
\end{quote}

\subsection*{Detailed Solution}


\subsection{Nyquist oscillation criterion and Colpitts feedback network}

Let the loop gain be

\begin{equation}
L(s)=A(s)\beta(s).
\end{equation}

The closed-loop characteristic equation is

\begin{equation}
1+L(s)=0.
\end{equation}

According to the Nyquist stability criterion, sustained oscillation occurs
at the boundary of stability when the Nyquist locus passes through the
critical point \(-1+\jmathunit0\). Equivalently, at the oscillation
frequency \(\omega_0\),

\begin{equation}
\lvert A(\jmathunit\omega_0)\beta(\jmathunit\omega_0)\rvert=1,
\end{equation}

and

\begin{equation}
\angle A(\jmathunit\omega_0)\beta(\jmathunit\omega_0)
=
(2m+1)180\degree
\end{equation}

for the negative-feedback form \(1+L=0\). In the usual positive-feedback
Barkhausen representation, the total loop phase is \(0\degree\) or an
integer multiple of \(360\degree\).

A Colpitts oscillator uses an inductor and two series capacitors as the
frequency-selective feedback network. The equivalent capacitance is

\begin{equation}
C_{\mathrm{eq}}
=
\frac{C_1C_2}{C_1+C_2}.
\end{equation}

The oscillation frequency is approximately

\begin{equation}
f_0
=
\frac{1}{2\pi\sqrt{LC_{\mathrm{eq}}}}.
\end{equation}

The ratio of \(C_1\) and \(C_2\) determines the feedback fraction. Proper
selection of the ratio allows the circuit to start reliably without using
excess transistor gain or bias current.

From an energy-efficiency and environmental perspective, the following
design choices are beneficial:

\begin{enumerate}[label=(\alph*)]
\item High-\(Q\) inductors and low-loss capacitors reduce circulating loss
and lower the required active-device power.
\item Correct feedback ratio avoids overdriving the transistor, reducing
harmonic generation and wasted DC power.
\item A stable resonant frequency reduces retransmissions and spectral
interference in wireless systems.
\item Varactor or digitally controlled tuning can replace mechanically
adjusted components and reduce maintenance and component replacement.
\item Lower power consumption reduces heat generation, cooling demand,
and lifetime carbon emissions.
\end{enumerate}

%-----------------------------------------------------------
\subsection{Oscillation frequency}

Given

\begin{equation}
L=\SI{70}{\nano\henry},
\quad
C_1=\SI{60}{\pico\farad},
\quad
C_2=\SI{350}{\pico\farad},
\end{equation}

the equivalent capacitance is

\begin{align}
C_{\mathrm{eq}}
&=
\frac{(60)(350)}{60+350}
\\
&=
\SI{51.22}{\pico\farad}.
\end{align}

Therefore,

\begin{align}
f_0
&=
\frac{1}
{2\pi\sqrt{(70\times10^{-9})(51.22\times10^{-12})}}
\\
&=
8.405\times10^7~\si{\hertz}
\\
&=
\SI{84.05}{\mega\hertz}.
\end{align}

Hence,

\begin{equation}
\boxed{f_0\approx\SI{84.05}{\mega\hertz}.}
\end{equation}

%-----------------------------------------------------------
\subsection{Capacitor \(C_1\) from transistor gain}

Using the common Colpitts start-up approximation

\begin{equation}
\beta_{\mathrm{transistor}}
\geq
\frac{C_2}{C_1},
\end{equation}

the limiting design value is

\begin{equation}
C_1=\frac{C_2}{\beta_{\mathrm{transistor}}}.
\end{equation}

Given

\begin{equation}
C_2=\SI{7}{\nano\farad},
\qquad
\beta_{\mathrm{transistor}}=45,
\end{equation}

\begin{align}
C_1
&=
\frac{7~\si{\nano\farad}}{45}
\\
&=
\SI{0.1556}{\nano\farad}
\\
&=
\SI{155.6}{\pico\farad}.
\end{align}

Therefore,

\begin{equation}
\boxed{C_1\approx\SI{156}{\pico\farad}.}
\end{equation}

The exact capacitor ratio depends on the transistor connection and on
which capacitor is defined as the feedback capacitor. The expression above
uses the standard convention stated in the solution.

%-----------------------------------------------------------
\subsection{Required inductance at \SI{30}{\mega\hertz}}

Given

\begin{equation}
f_0=\SI{30}{\mega\hertz},
\quad
C_1=\SI{170}{\pico\farad},
\quad
C_2=\SI{190}{\pico\farad},
\end{equation}

the equivalent capacitance is

\begin{align}
C_{\mathrm{eq}}
&=
\frac{(170)(190)}{170+190}
\\
&=
\SI{89.72}{\pico\farad}.
\end{align}

From

\begin{equation}
f_0=\frac{1}{2\pi\sqrt{LC_{\mathrm{eq}}}},
\end{equation}

the inductance is

\begin{equation}
L
=
\frac{1}{(2\pi f_0)^2C_{\mathrm{eq}}}.
\end{equation}

Therefore,

\begin{align}
L
&=
\frac{1}
{[2\pi(30\times10^6)]^2(89.72\times10^{-12})}
\\
&=
3.137\times10^{-7}~\si{\henry}
\\
&=
\SI{313.7}{\nano\henry}.
\end{align}

Hence,

\begin{equation}
\boxed{L\approx\SI{314}{\nano\henry}.}
\end{equation}

%-----------------------------------------------------------
\subsection{Reverse bias required for a graded-junction diode}

The junction capacitance is

\begin{equation}
C_j(V_R)
=
\frac{C_0}
{\left(1+\dfrac{V_R}{\phi}\right)^\gamma}.
\end{equation}

Rearranging,

\begin{equation}
V_R
=
\phi
\left[
\left(\frac{C_0}{C_j}\right)^{1/\gamma}
-1
\right].
\end{equation}

Given

\begin{equation}
C_0=\SI{22}{\pico\farad},
\quad
C_j=\SI{13}{\pico\farad},
\quad
\phi=\SI{0.7}{\volt},
\quad
\gamma=0.33,
\end{equation}

\begin{align}
V_R
&=
0.7
\left[
\left(\frac{22}{13}\right)^{1/0.33}
-1
\right]
\\
&=
\SI{2.75}{\volt}.
\end{align}

Therefore,

\begin{equation}
\boxed{V_R\approx\SI{2.75}{\volt}.}
\end{equation}

%===========================================================
\newpage
\section{Question 6: Varactor-Tuned Resonant Circuits}

\subsection*{Original Question}

\begin{quote}
\small
\textbf{Part A}

A varactor-tuned LC resonant circuit operates at
\(\SI{6}{\mega\hertz}\) with \(L=\SI{65}{\micro\henry}\). It must be
tunable over a \(\pm3\%\) frequency range using a single silicon
graded-junction varactor diode with \(\gamma=0.5\). Assume ideal
components.

\begin{enumerate}[label=(\roman*)]
\item Calculate the required capacitance range.
\item Determine the corresponding varactor capacitance at both tuning
limits.
\end{enumerate}

\medskip
\textbf{Part B}

A varactor diode with
\[
C_0=\SI{30}{\pico\farad},
\qquad
\phi=\SI{0.7}{\volt},
\qquad
\gamma=0.33
\]
is added in parallel with a resonant circuit operating at
\(\SI{5}{\mega\hertz}\), with \(L=\SI{53}{\micro\henry}\).

\begin{enumerate}[label=(\roman*)]
\item Create a design that reduces the resonant frequency by \(3\%\) using
reverse bias.
\item Calculate the required DC bias voltage applied to the varactor.
\end{enumerate}

\medskip
\textbf{Part C}

An existing RF tuning circuit uses manual trimmer capacitors. Redesign the
tuning approach to better satisfy zero-carbon and environmental objectives,
and evaluate the benefits and trade-offs.
\end{quote}

\subsection*{Detailed Solution}


\subsection{Capacitance range for a \(\pm3\%\) tuning range}

The nominal frequency is

\begin{equation}
f_0=\SI{6}{\mega\hertz}.
\end{equation}

The lower and upper frequencies are

\begin{align}
f_{\min}
&=
0.97f_0
=
\SI{5.82}{\mega\hertz},
\\
f_{\max}
&=
1.03f_0
=
\SI{6.18}{\mega\hertz}.
\end{align}

For an ideal LC resonator,

\begin{equation}
C
=
\frac{1}{(2\pi f)^2L}.
\end{equation}

Given \(L=\SI{65}{\micro\henry}\), the maximum capacitance occurs at the
minimum frequency:

\begin{align}
C_{\max}
&=
\frac{1}
{[2\pi(5.82\times10^6)]^2(65\times10^{-6})}
\\
&=
\SI{11.505}{\pico\farad}.
\end{align}

The minimum capacitance occurs at the maximum frequency:

\begin{align}
C_{\min}
&=
\frac{1}
{[2\pi(6.18\times10^6)]^2(65\times10^{-6})}
\\
&=
\SI{10.204}{\pico\farad}.
\end{align}

Therefore,

\begin{equation}
\boxed{
C_{\min}=\SI{10.204}{\pico\farad},
\qquad
C_{\max}=\SI{11.505}{\pico\farad}.
}
\end{equation}

The required tuning span is

\begin{align}
\Delta C
&=
C_{\max}-C_{\min}
\\
&=
\SI{1.301}{\pico\farad}.
\end{align}

Hence,

\begin{equation}
\boxed{\Delta C\approx\SI{1.30}{\pico\farad}.}
\end{equation}

For a single ideal varactor that provides all of the resonant capacitance,

\begin{equation}
\boxed{
C_V(f_{\min})=\SI{11.505}{\pico\farad},
\qquad
C_V(f_{\max})=\SI{10.204}{\pico\farad}.
}
\end{equation}

%-----------------------------------------------------------
\subsection{Reduction of a \SI{5}{\mega\hertz} resonant frequency by \(3\%\)}

The original frequency is

\begin{equation}
f_0=\SI{5}{\mega\hertz},
\end{equation}

and the target frequency is

\begin{align}
f_1
&=
0.97f_0
\\
&=
\SI{4.85}{\mega\hertz}.
\end{align}

With \(L=\SI{53}{\micro\henry}\), the original capacitance is

\begin{align}
C_{\mathrm{original}}
&=
\frac{1}
{[2\pi(5\times10^6)]^2(53\times10^{-6})}
\\
&=
\SI{19.117}{\pico\farad}.
\end{align}

The required total capacitance at \SI{4.85}{\mega\hertz} is

\begin{align}
C_{\mathrm{new}}
&=
\frac{1}
{[2\pi(4.85\times10^6)]^2(53\times10^{-6})}
\\
&=
\SI{20.318}{\pico\farad}.
\end{align}

Therefore, the varactor must add

\begin{align}
C_V
&=
C_{\mathrm{new}}-C_{\mathrm{original}}
\\
&=
20.318-19.117
\\
&=
\SI{1.201}{\pico\farad}.
\end{align}

Hence,

\begin{equation}
\boxed{C_V\approx\SI{1.201}{\pico\farad}.}
\end{equation}

For the varactor,

\begin{equation}
C_V
=
\frac{C_0}
{\left(1+\dfrac{V_R}{\phi}\right)^\gamma}.
\end{equation}

Solving for \(V_R\),

\begin{equation}
V_R
=
\phi
\left[
\left(\frac{C_0}{C_V}\right)^{1/\gamma}
-1
\right].
\end{equation}

Using

\begin{equation}
C_0=\SI{30}{\pico\farad},
\quad
\phi=\SI{0.7}{\volt},
\quad
\gamma=0.33,
\end{equation}

\begin{align}
V_R
&=
0.7
\left[
\left(\frac{30}{1.201}\right)^{1/0.33}
-1
\right]
\\
&\approx
\SI{1.20e4}{\volt}.
\end{align}

Thus, the direct mathematical result is

\begin{equation}
\boxed{V_R\approx\SI{12.0}{\kilo\volt}.}
\end{equation}

This result is physically impractical. It shows that placing the stated
\(\SI{30}{\pico\farad}\) varactor directly in parallel is not a suitable
implementation because the required effective capacitance is only about
\(\SI{1.2}{\pico\farad}\). A practical circuit should place a small fixed
capacitor in series with the varactor so that the series equivalent
capacitance is approximately \(\SI{1.2}{\pico\farad}\), while the varactor
itself operates at a safe reverse bias.

%-----------------------------------------------------------
\subsection{Environmentally improved tuning approach}

The manual trimmer capacitor may be replaced by an electronically controlled
varactor-tuning network. The proposed design contains:

\begin{enumerate}[label=(\roman*)]
\item a reverse-biased varactor diode,
\item a low-power DAC or PWM-to-DC control circuit,
\item a high-value RF isolation resistor or RF choke,
\item a DC-blocking capacitor where required,
\item closed-loop frequency calibration in firmware.
\end{enumerate}

The principal benefits are:

\begin{enumerate}[label=(\alph*)]
\item No repeated mechanical adjustment is required.
\item Remote calibration reduces travel and maintenance.
\item Automatic tuning can compensate for temperature and component ageing.
\item Improved matching can reduce transmitter power loss and retransmission.
\item Reduced mechanical wear may extend product lifetime and reduce
electronic waste.
\end{enumerate}

The trade-offs are:

\begin{enumerate}[label=(\alph*)]
\item A varactor has finite \(Q\), causing additional RF loss.
\item The capacitance-voltage relationship is nonlinear.
\item Bias noise can cause phase noise or frequency modulation.
\item The tuning range may be smaller than that of a mechanical trimmer.
\item Additional control electronics create embodied carbon and require
a small amount of operating power.
\end{enumerate}

Overall, electronic tuning is more consistent with zero-carbon objectives
when the circuit is produced at scale, operates for a long lifetime, and
reduces maintenance, power loss, and premature replacement.

%-----------------------------------------------------------
\subsection{Proposed varactor-tuning circuit}

A practical electronically controlled tuning network is shown in
Figure~\ref{fig:q6-varactor}. The fixed capacitor \(C_F\) establishes the
main resonant capacitance, while the series capacitor \(C_S\) limits the
effective contribution of the varactor. The large bias resistor \(R_B\)
isolates the RF tank from the DC tuning source, and \(C_B\) bypasses noise
on the tuning voltage.

\begin{figure}[H]
\centering
\begin{circuitikz}[american]
    % Resonant tank top rail
    \draw (0,3) -- (6,3);
    \node[left] at (0,3) {RF tank node};

    % Inductor branch
    \draw (1,3) to[L,l_=\(L\)] (1,0) node[ground]{};

    % Fixed capacitor branch
    \draw (3,3) to[C,l=\(C_F\)] (3,0) node[ground]{};

    % Series capacitor and varactor-equivalent capacitance
    \draw (5,3) to[C,l=\(C_S\)] (5,1.55)
          to[C,l_=\(C_V(V_R)\)] (5,0) node[ground]{};

    % Bias network
    \draw (5,1.55) to[R,l=\(R_B\)] (7.5,1.55);
    \node[right] at (7.5,1.55) {\(V_{\mathrm{tune}}\)};

    % Bypass capacitor
    \draw (7.0,1.55) to[C,l_=\(C_B\)] (7.0,0) node[ground]{};

    % Junction marker
    \fill (5,1.55) circle (1.8pt);
    \fill (7.0,1.55) circle (1.8pt);
\end{circuitikz}
\caption{Electronically controlled varactor-tuning network.}
\label{fig:q6-varactor}
\end{figure}

At the RF frequency, \(R_B\) is selected to be much larger than the tank
impedance so that the control circuit does not significantly load the
resonator. The bypass capacitor \(C_B\) should present a low impedance to
ground at unwanted noise and modulation frequencies.

%===========================================================
\newpage
\section{Question 7: Simultaneous Conjugate Matching}

\subsection*{Original Question}

\begin{quote}
\small
A \(\SI{300}{\mega\hertz}\) silicon transistor has the following
\(S\)-parameters at \(V_{CE}=\SI{10}{\volt}\) and
\(I_C=\SI{10}{\milli\ampere}\):

\begin{equation}
[S]
=
\begin{bmatrix}
0.39\angle160\degree & 0.02\angle58\degree\\
4.9\angle62\degree & 0.37\angle(-42\degree)
\end{bmatrix}.
\end{equation}

The amplifier operates between \(\SI{50}{\ohm}\) terminations. Design the
input and output matching networks for simultaneous conjugate matching and
maximum gain by calculating:

\begin{enumerate}[label=(\roman*)]
\item Rollet's stability factor \(K\) and the determinant \(\Delta\);
\item the maximum available gain;
\item the load reflection coefficient \(\Gamma_L\);
\item the source reflection coefficient \(\Gamma_S\);
\item the corresponding input-side impedance;
\item the corresponding output-side impedance.
\end{enumerate}
\end{quote}

\subsection*{Detailed Solution}


The transistor scattering parameters are

\begin{equation}
[S]
=
\begin{bmatrix}
\polar{0.39}{160} & \polar{0.02}{58}\\
\polar{4.9}{62} & \polar{0.37}{-42}
\end{bmatrix}.
\end{equation}

The system reference impedance is

\begin{equation}
Z_0=\SI{50}{\ohm}.
\end{equation}

%-----------------------------------------------------------
\subsection{Rollet stability factor and determinant}

The determinant is

\begin{equation}
\Delta=S_{11}S_{22}-S_{12}S_{21}.
\end{equation}

Converting and calculating,

\begin{align}
\Delta
&=
-0.01874+\jmathunit0.04254
\\
&=
\polar{0.04649}{113.78}.
\end{align}

Therefore,

\begin{equation}
\boxed{
\Delta=-0.01874+\jmathunit0.04254,
\qquad
\lvert\Delta\rvert=0.04649.
}
\end{equation}

Rollet's stability factor is

\begin{equation}
K
=
\frac{
1-\lvert S_{11}\rvert^2-\lvert S_{22}\rvert^2+\lvert\Delta\rvert^2
}{
2\lvert S_{12}S_{21}\rvert
}.
\end{equation}

Substitution gives

\begin{align}
K
&=
\frac{
1-(0.39)^2-(0.37)^2+(0.04649)^2
}{
2(0.02)(4.9)
}
\\
&=
3.639.
\end{align}

Therefore,

\begin{equation}
\boxed{K=3.639.}
\end{equation}

Since

\begin{equation}
K>1
\qquad\text{and}\qquad
\lvert\Delta\rvert<1,
\end{equation}

the transistor is unconditionally stable at the stated frequency and bias.

%-----------------------------------------------------------
\subsection{Maximum available gain}

For an unconditionally stable transistor,

\begin{equation}
MAG
=
\left|\frac{S_{21}}{S_{12}}\right|
\left(
K-\sqrt{K^2-1}
\right).
\end{equation}

Thus,

\begin{align}
MAG
&=
\frac{4.9}{0.02}
\left(
3.639-\sqrt{3.639^2-1}
\right)
\\
&=
34.33.
\end{align}

In decibels,

\begin{align}
MAG_{\mathrm{dB}}
&=
10\log_{10}(34.33)
\\
&=
\SI{15.36}{\decibel}.
\end{align}

Hence,

\begin{equation}
\boxed{MAG=34.33=\SI{15.36}{\decibel}.}
\end{equation}

%-----------------------------------------------------------
\subsection{Optimum source and load reflection coefficients}

Define

\begin{equation}
B_1
=
1+\lvert S_{11}\rvert^2-\lvert S_{22}\rvert^2-\lvert\Delta\rvert^2,
\end{equation}

\begin{equation}
C_1
=
S_{11}-\Delta S_{22}^{*},
\end{equation}

\begin{equation}
B_2
=
1+\lvert S_{22}\rvert^2-\lvert S_{11}\rvert^2-\lvert\Delta\rvert^2,
\end{equation}

and

\begin{equation}
C_2
=
S_{22}-\Delta S_{11}^{*}.
\end{equation}

Numerically,

\begin{equation}
B_1=1.01304,
\end{equation}

\begin{equation}
C_1=-0.35079+\jmathunit0.12633,
\end{equation}

\begin{equation}
B_2=0.98264,
\end{equation}

and

\begin{equation}
C_2=0.26242-\jmathunit0.23449.
\end{equation}

The optimum source reflection coefficient is

\begin{equation}
\Gamma_S
=
\frac{
B_1-\sqrt{B_1^2-4\lvert C_1\rvert^2}
}{
2C_1
},
\end{equation}

where the sign is selected so that \(\lvert\Gamma_S\rvert<1\).

Thus,

\begin{align}
\Gamma_S
&=
-0.41301-\jmathunit0.14874
\\
&=
\polar{0.43897}{-160.19}.
\end{align}

Therefore,

\begin{equation}
\boxed{
\Gamma_S
=
-0.4130-\jmathunit0.1487
=
\polar{0.4390}{-160.19}.
}
\end{equation}

Similarly,

\begin{equation}
\Gamma_L
=
\frac{
B_2-\sqrt{B_2^2-4\lvert C_2\rvert^2}
}{
2C_2
}.
\end{equation}

Hence,

\begin{align}
\Gamma_L
&=
0.31459+\jmathunit0.28110
\\
&=
\polar{0.42188}{41.78}.
\end{align}

Therefore,

\begin{equation}
\boxed{
\Gamma_L
=
0.3146+\jmathunit0.2811
=
\polar{0.4219}{41.78}.
}
\end{equation}

%-----------------------------------------------------------
\subsection{Corresponding source and load impedances}

The impedance corresponding to a reflection coefficient is

\begin{equation}
Z
=
Z_0
\frac{1+\Gamma}{1-\Gamma}.
\end{equation}

For the source,

\begin{align}
Z_S
&=
50
\frac{1+\Gamma_S}{1-\Gamma_S}
\\
&=
19.996-\jmathunit7.368~\si{\ohm}.
\end{align}

Thus,

\begin{equation}
\boxed{Z_S\approx20.00-\jmathunit7.37~\si{\ohm}.}
\end{equation}

For the load,

\begin{align}
Z_L
&=
50
\frac{1+\Gamma_L}{1-\Gamma_L}
\\
&=
74.891+\jmathunit51.221~\si{\ohm}.
\end{align}

Thus,

\begin{equation}
\boxed{Z_L\approx74.89+\jmathunit51.22~\si{\ohm}.}
\end{equation}

The input matching network must transform the external
\(\SI{50}{\ohm}\) source to \(Z_S\), while the output matching network must
transform the external \(\SI{50}{\ohm}\) load to \(Z_L\).

%-----------------------------------------------------------
\subsection{Input and output matching-network layout}

The matching-network arrangement is shown in
Figure~\ref{fig:q7-matching}. The input network presents the optimum source
impedance to port 1 of the transistor, and the output network presents the
optimum load impedance to port 2.

\begin{figure}[H]
\centering
\begin{tikzpicture}[x=1cm,y=1cm]
    % Blocks
    \node[draw,minimum width=1.7cm,minimum height=1.0cm,align=center]
        (source) at (0,0) {\(\SI{50}{\ohm}\)\\source};

    \node[draw,minimum width=2.4cm,minimum height=1.2cm,align=center]
        (imn) at (3.0,0) {Input matching\\network};

    \node[draw,minimum width=2.3cm,minimum height=1.45cm,align=center]
        (device) at (6.4,0) {Transistor\\two-port \(S\)};

    \node[draw,minimum width=2.4cm,minimum height=1.2cm,align=center]
        (omn) at (9.8,0) {Output matching\\network};

    \node[draw,minimum width=1.7cm,minimum height=1.0cm,align=center]
        (load) at (12.8,0) {\(\SI{50}{\ohm}\)\\load};

    % Interconnections
    \draw[->,thick] (source.east) -- (imn.west);
    \draw[->,thick] (imn.east) -- (device.west);
    \draw[->,thick] (device.east) -- (omn.west);
    \draw[->,thick] (omn.east) -- (load.west);

    % Port labels
    \node[above] at (4.75,0.2) {Port 1};
    \node[above] at (8.05,0.2) {Port 2};

    % Target impedances
    \node[below,align=center] at (4.75,-0.25)
        {\(Z_S\approx20.00-\jmathunit7.37~\si{\ohm}\)\\
         \(\Gamma_S=\polar{0.4390}{-160.19}\)};

    \node[below,align=center] at (8.05,-0.25)
        {\(Z_L\approx74.89+\jmathunit51.22~\si{\ohm}\)\\
         \(\Gamma_L=\polar{0.4219}{41.78}\)};
\end{tikzpicture}
\caption{Simultaneous-conjugate matching arrangement for Question 7.}
\label{fig:q7-matching}
\end{figure}

The matching blocks may be implemented using lumped \(L\)-networks,
single-stub networks, or microstrip sections. Their purpose is the same:
to convert the external \(\SI{50}{\ohm}\) terminations into the calculated
complex impedances at the transistor reference planes.

%===========================================================
\newpage
\section{Question 8: Power-Amplifier Stability and Matching}

\subsection*{Original Question}

\begin{quote}
\small
A power amplifier must deliver \(\SI{10}{\watt}\)
(\(\SI{40}{\dBm}\)) output power at \(\SI{3}{\giga\hertz}\), with
system impedance \(Z_0=\SI{50}{\ohm}\). The following small-signal
\(S\)-parameters are given at \(\SI{3}{\giga\hertz}\) and
\(V_{DS}=\SI{25}{\volt}\):

\[
S_{11}=0.32\angle(-150\degree),
\qquad
S_{12}=0.004\angle50\degree,
\]

\[
S_{21}=4.5\angle(-90\degree),
\qquad
S_{22}=0.36\angle(-120\degree).
\]

Large-signal load-pull data for \(\SI{10}{\watt}\) operation give

\[
Z_{SP}=17-\jmathunit5~\si{\ohm},
\qquad
Z_{LP}=6+\jmathunit5~\si{\ohm}.
\]

\begin{enumerate}[label=\alph*)]
\item Determine the stability of the amplifier at
\(\SI{2.4}{\giga\hertz}\) using the supplied small-signal scattering
parameters.

\item Evaluate the effect of unconditional stability on public health and
safety.

\item Convert the large-signal source and load impedances into reflection
coefficients.

\item Determine the source and load reflection coefficients for
simultaneous conjugate matching and calculate their corresponding
impedances.

\item If the drain efficiency is \(\eta_D=28\%\), determine:
\begin{enumerate}[label=\roman*.]
\item the maximum available gain;
\item the power-added efficiency.
\end{enumerate}
\end{enumerate}
\end{quote}

\subsection*{Detailed Solution}


The small-signal parameters supplied are

\begin{equation}
S_{11}=\polar{0.32}{-150},
\end{equation}

\begin{equation}
S_{12}=\polar{0.004}{50},
\end{equation}

\begin{equation}
S_{21}=\polar{4.5}{-90},
\end{equation}

and

\begin{equation}
S_{22}=\polar{0.36}{-120}.
\end{equation}

The data are stated at \SI{3}{\giga\hertz}, although part (a) asks for
stability at \SI{2.4}{\giga\hertz}. Since no separate \SI{2.4}{\giga\hertz}
data are supplied, the following calculation uses the given S-parameters
and therefore strictly represents the stated \SI{3}{\giga\hertz} operating
point.

%-----------------------------------------------------------
\subsection{Stability}

The determinant is

\begin{align}
\Delta
&=
S_{11}S_{22}-S_{12}S_{21}
\\
&=
-0.01379+\jmathunit0.12677
\\
&=
\polar{0.12752}{96.21}.
\end{align}

Therefore,

\begin{equation}
\boxed{\lvert\Delta\rvert=0.1275.}
\end{equation}

The stability factor is

\begin{align}
K
&=
\frac{
1-\lvert S_{11}\rvert^2-\lvert S_{22}\rvert^2+\lvert\Delta\rvert^2
}{
2\lvert S_{12}S_{21}\rvert
}
\\
&=
21.785.
\end{align}

Thus,

\begin{equation}
\boxed{K=21.785.}
\end{equation}

Since

\begin{equation}
K>1
\qquad\text{and}\qquad
\lvert\Delta\rvert<1,
\end{equation}

the device is unconditionally stable for all passive source and load
terminations at the frequency represented by the supplied data.

%-----------------------------------------------------------
\subsection{Effect of unconditional stability on health and safety}

Unconditional stability reduces the risk of unintended self-oscillation
when the amplifier is connected to passive source and load impedances.
This has several safety implications:

\begin{enumerate}[label=(\alph*)]
\item It reduces unintended RF emissions that may interfere with medical,
aviation, navigation, and communication systems.
\item It reduces excessive transistor current and overheating caused by
parasitic oscillation.
\item It lowers the risk of component failure, burns, smoke, or fire in
high-power RF hardware.
\item It improves compliance with electromagnetic compatibility and
occupational RF-exposure limits.
\item It improves reliability under antenna mismatch, cable movement, and
manufacturing tolerances.
\end{enumerate}

Unconditional small-signal stability does not by itself guarantee complete
large-signal safety. Bias-network resonances, thermal instability,
out-of-band oscillations, and breakdown under severe mismatch must still
be checked.

%-----------------------------------------------------------
\subsection{Large-signal load-pull reflection coefficients}

The load-pull source impedance is

\begin{equation}
Z_{SP}=17-\jmathunit5~\si{\ohm}.
\end{equation}

The corresponding reflection coefficient is

\begin{align}
\Gamma_{SP}
&=
\frac{Z_{SP}-Z_0}{Z_{SP}+Z_0}
\\
&=
\frac{(17-\jmathunit5)-50}
{(17-\jmathunit5)+50}
\\
&=
-0.48427-\jmathunit0.11077
\\
&=
\polar{0.49678}{-167.12}.
\end{align}

Therefore,

\begin{equation}
\boxed{
\Gamma_{SP}
=
-0.4843-\jmathunit0.1108
=
\polar{0.4968}{-167.12}.
}
\end{equation}

The load-pull load impedance is

\begin{equation}
Z_{LP}=6+\jmathunit5~\si{\ohm}.
\end{equation}

Thus,

\begin{align}
\Gamma_{LP}
&=
\frac{Z_{LP}-Z_0}{Z_{LP}+Z_0}
\\
&=
\frac{(6+\jmathunit5)-50}
{(6+\jmathunit5)+50}
\\
&=
-0.77159+\jmathunit0.15818
\\
&=
\polar{0.78764}{168.41}.
\end{align}

Therefore,

\begin{equation}
\boxed{
\Gamma_{LP}
=
-0.7716+\jmathunit0.1582
=
\polar{0.7876}{168.41}.
}
\end{equation}

%-----------------------------------------------------------
\subsection{Small-signal simultaneous conjugate match}

Using the simultaneous conjugate-match equations,

\begin{equation}
\Gamma_S
=
\frac{
B_1-\sqrt{B_1^2-4\lvert C_1\rvert^2}
}{
2C_1
},
\end{equation}

and

\begin{equation}
\Gamma_L
=
\frac{
B_2-\sqrt{B_2^2-4\lvert C_2\rvert^2}
}{
2C_2
},
\end{equation}

the passive roots are

\begin{align}
\Gamma_S
&=
-0.27597+\jmathunit0.15274
\\
&=
\polar{0.31542}{151.04},
\end{align}

and

\begin{align}
\Gamma_L
&=
-0.18228+\jmathunit0.30588
\\
&=
\polar{0.35607}{120.79}.
\end{align}

Therefore,

\begin{equation}
\boxed{
\Gamma_S
=
-0.2760+\jmathunit0.1527
=
\polar{0.3154}{151.04},
}
\end{equation}

and

\begin{equation}
\boxed{
\Gamma_L
=
-0.1823+\jmathunit0.3059
=
\polar{0.3561}{120.79}.
}
\end{equation}

The corresponding impedances are

\begin{align}
Z_S
&=
50\frac{1+\Gamma_S}{1-\Gamma_S}
\\
&=
27.265+\jmathunit9.249~\si{\ohm},
\end{align}

and

\begin{align}
Z_L
&=
50\frac{1+\Gamma_L}{1-\Gamma_L}
\\
&=
29.276+\jmathunit20.510~\si{\ohm}.
\end{align}

Hence,

\begin{equation}
\boxed{
Z_S\approx27.26+\jmathunit9.25~\si{\ohm},
}
\end{equation}

and

\begin{equation}
\boxed{
Z_L\approx29.28+\jmathunit20.51~\si{\ohm}.
}
\end{equation}

The small-signal conjugate-match impedances are different from the
large-signal load-pull impedances because a power amplifier is nonlinear
at the \SI{10}{\watt} operating point. For maximum output power and
efficiency, the load-pull impedances normally take priority.

%-----------------------------------------------------------
\subsection{Maximum available gain}

Because the amplifier is unconditionally stable,

\begin{equation}
MAG
=
\left|\frac{S_{21}}{S_{12}}\right|
\left(
K-\sqrt{K^2-1}
\right).
\end{equation}

Thus,

\begin{align}
MAG
&=
\frac{4.5}{0.004}
\left(
21.785-\sqrt{21.785^2-1}
\right)
\\
&=
25.834.
\end{align}

In decibels,

\begin{align}
MAG_{\mathrm{dB}}
&=
10\log_{10}(25.834)
\\
&=
\SI{14.12}{\decibel}.
\end{align}

Therefore,

\begin{equation}
\boxed{MAG=25.83=\SI{14.12}{\decibel}.}
\end{equation}

%-----------------------------------------------------------
\subsection{Power-added efficiency}

The output power is

\begin{equation}
P_{\mathrm{out}}=\SI{10}{\watt}.
\end{equation}

The drain efficiency is

\begin{equation}
\eta_D
=
\frac{P_{\mathrm{out}}}{P_{\mathrm{DC}}}
=
0.28.
\end{equation}

Therefore,

\begin{align}
P_{\mathrm{DC}}
&=
\frac{P_{\mathrm{out}}}{\eta_D}
\\
&=
\frac{10}{0.28}
\\
&=
\SI{35.714}{\watt}.
\end{align}

Assuming the available gain is used as the power gain,

\begin{align}
P_{\mathrm{in}}
&=
\frac{P_{\mathrm{out}}}{MAG}
\\
&=
\frac{10}{25.834}
\\
&=
\SI{0.387}{\watt}.
\end{align}

The power-added efficiency is

\begin{equation}
PAE
=
\frac{P_{\mathrm{out}}-P_{\mathrm{in}}}
{P_{\mathrm{DC}}}.
\end{equation}

Thus,

\begin{align}
PAE
&=
\frac{10-0.387}{35.714}
\\
&=
0.2692
\\
&=
26.92\%.
\end{align}

Therefore,

\begin{equation}
\boxed{PAE\approx26.92\%.}
\end{equation}

\end{document}

```
