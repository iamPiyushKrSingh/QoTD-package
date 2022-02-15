# QoTD-package
This is a latex package help you creating a good looking QoTD's. For your educational discussion in LaTeX.

* [Installation](README.md#Installation)
  * [Overleaf](README.md#on-overleaf)
* [Features](README.md#features-it-includes)
* [Basic Uses](README.md#basic-uses)

## Installation
The installation is so easy, it is just like copy and pasting a file from one drive to another. 
#### On Overleaf

To start with copy the code from the file `qotd.sty` and paste it in a new file in Overleaf but that file _must be having_ an extension of `.sty`.
And now just paste this command in the preamble
```tex
\usepackage{qotd}
```
and after this pasting your file manager on left side should look like this
![preamble](https://i.ibb.co/Z6dnFWY/Screenshot-2022-02-16-02-45-44-13-40deb401b9ffe8e1df2f1cc5ba480b12.jpg)

> _An important **NOTE** this package requires `logo.jpg` file to work properly so ensure that you have that too in the file manager._
![logo.jpg](https://i.ibb.co/wcRNVRR/logo.jpg)

## Features it includes
1. It has got all the basic packages which is required for **mathematics** and **physics**. Like `amsmath`, `amssymb`, `amsthm`, `physics` and `mathtools`.
2. It has a special condition
   ```tex
   \everymath{\displaystyle}
   ```
   which renders all the inline mathematical expression as like in `maths-mode`.
3. Having all the important packages for image formatting like `graphicx`, `float`, `wrapfig`, and `adjustbox`.
4. Having all the important packages for table formatting like `array`, `tabularx`, `multirow`, `longtable`.
5. Making the page `top margin = 5mm` and `bottom margin = 1mm` and width be unchanged from **standard a4paper**.
6. Having `tikz` package pre-installed.
7. And having alot of customised commands for fast typesetting of maths and physics:
   ```tex
   \newcommand{\cbrt}[1]{\sqrt[3]{#1}}
   \newcommand{\floor}[1]{\left\lfloor #1 \right\rfloor}
   \newcommand{\ceil}[1]{\left\lceil #1 \right\rceil}
   \newcommand{\inv}{^{-1}}
   \newcommand{\sq}{^2}
   \newcommand{\dg}{^{\circ}}
   \newcommand{\naut}{_{\circ}}
   ```
   and some short commands for easy `maths-fonts`
   ```tex
   \newcommand{\mbb}[1]{\mathbb{#1}}
   \newcommand{\mfk}[1]{\mathfrak{#1}}
   ```
8.

## Basic Uses
In this section you will get to know all the features available to use right out of the box.

### 
