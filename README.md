# QoTD-package
This is a latex package help you creating a good looking QoTD's. For your educational discussion in LaTeX.

* [Installation](README.md#Installation)
  * [Overleaf](README.md#on-overleaf)
* [Features](README.md#features-it-includes)
* [Basic Uses](README.md#basic-uses)
  * [New Commands](README.md#basic-commands)
  * [New Environment](README.md#new-environment)

## Installation
The installation is so easy, it is just like copy and pasting a file from one drive to another. 
#### On [Overleaf](https://www.overleaf.com)

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
8. By using following packages and options you are given with 2 tcolorboxes.
   * First box is given a name `qotdphybox`
     ```tex 
     \newtcolorbox{qotdphybox}[2][]{enhanced,skin=enhancedlast jigsaw, attach boxed title to top left={xshift=-4mm,yshift=-0.5mm}, fonttitle=\large\bfseries\sffamily,varwidth boxed title=0.7\linewidth, colbacktitle=blue!45!white,colframe=red!50!black, interior style={top color=blue!10!white,bottom color=red!10!white}, boxed title style={empty,arc=0pt,outer arc=0pt,boxrule=0pt}, underlay boxed title={\fill[blue!45!white] (title.north west) -- (title.north east) -- +(\tcboxedtitleheight-1mm,-\tcboxedtitleheight+1mm) -- ([xshift=4mm,yshift=0.5mm]frame.north east) -- +(0mm,-1mm) -- (title.south west) -- cycle; \fill[blue!45!white!50!black] ([yshift=-0.5mm]frame.north west) -- +(-0.4,0) -- +(0,-0.3) -- cycle; \fill[blue!45!white!50!black] ([yshift=-0.5mm]frame.north east) -- +(0,-0.3) -- +(0.4,0) -- cycle; }, title={#2},#1}
     ```
   * Second box is given a name `qotdmathsbox`
     ```tex
     \newtcolorbox{qotdmathsbox}[2][]{colback=yellow!5!white, colframe=blue!50!black, coltitle=white, fonttitle = \sffamily\bfseries\large , halign title = center,title={#2},#1}
     ```
9. Improving the `enumerate` environment creating a new environment by the name of `qotdques`
   ```tex
   \usepackage[shortlabels]{enumitem}
   ```
   ```tex
   \newenvironment{qotdques}{
       \begin{enumerate}[label = \fbox{\emph{\textbf{Q\arabic*:}}}]
           }
           {
       \end{enumerate}
   }
   ```
   And tweaking `\item` command to use it with a parameter explaining marks of that perticular question.
   ```tex
   \newcommand{\ques}[1]{\item (#1 marks)}
   ```
10. Making a handy QoTD title command like `\qotdtitle{#QoTD No.}{#Week No.}{#Challenge No.}`
11. Making a easy Creator name command like `\qotdcreator{#Creator's Name}`
    

## Basic Uses
In this section you will get to know all the features available to use right out of the box.

### New Commands

* QoTD Number
  ```tex
  \qotdtitle{}{}{}
  ``` 
  as all the parameters is explained in `features point 10.`.
  
  Output for the code `\qotdtitle{56}{7}{1}`
  ![qotdtitle](https://i.ibb.co/8DJv4Hn/qotd-title.jpg)
* QoTD Creator
  ```tex
  \qotdcreator{}
  ```
  as use of this code is explained in `features point 11.`.
  
  Output for the code `\qotdcreator{JØKÊR}` 
  ![qotdcreator](https://i.ibb.co/xzpWcpm/qotd-creator.jpg)
  > NOTE: This command is **right justified** by `\rightline{}` command so it may require `\\` or `\newline` command before this to work perfectly.

### New Environment
* QoTD Physics Box
  ```tex
  \begin{qotdphybox}{#Title of the box}
      .
      .
      .
   \end{qotdphybox}
   ```
   
   Its use as simple as writing a text message.

   Output for code 
   ```tex
   \begin{qotdphybox}{Testing}
      \lipsum[1-2]    % Use \usepackage{lipsum} in preamble.
   \end{qotdphybox}
   ```
   ![qotdphybox](https://i.ibb.co/549BcHS/qotd-phy-box.jpg)
   > NOTE: The title parameter is must to avoid broken results or if you don't have any title then use it like `\begin{qotdphybox}{}`.
* QoTD Maths Box
  ```tex
  \begin{qotdmathsbox}{#Title of the box}
      .
      .
      .
   \end{qotdmathsbox}
   ```
   
   Use it same as `Physics Box`.
   
   Output for the code
   ```tex
   \begin{qotdmathsbox}{} % No title box
      \lipsum[1-2]    % Use \usepackage{lipsum} in preamble.
   \end{qotdmathsbox}
   ```
   ![qotd-maths-box](https://i.ibb.co/K7yMmp9/qotd-maths-box.jpg)
* Question `Enumerate` Box
  ```tex
  \begin{qotdques}
      .
      .
      .
  \end{qotdques}
  ```
  This is the environment used for writing questions. Making the content colour **Red** and make label boxed and number goes like `Q1:`.
  
  Output for code
  ```tex
  \begin{qotdques}
      \item \lipsum[1]
      \item \lipsum[2]
  \end{qotdques}
  ```
  ![qotdenumerate](https://i.ibb.co/JrcZXBb/qotd-enumerate.jpg)
  > Incorporating this environment with tweaked `\item` command _i.e._ `\ques{}` where, parameter is the marks given that ques. You will get Output like:
  ![qotd-ques](https://i.ibb.co/j8yFRCS/qotd-ques.jpg)


