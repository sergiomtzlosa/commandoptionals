# commandoptionals

## Description
The `commandoptionals` package provides a command `\newcommandoptionals` that allows defining new commands with a variable number of optional and mandatory arguments. It is implemented using `xparse` (LaTeX3).

## Installation
Copy `commandoptionals.sty` to a location where LaTeX can find it (e.g., your local texmf tree or the same directory as your project).

## Usage
Load the package in your preamble:
```latex
\usepackage{commandoptionals}
```

Define a new command with optional arguments:
```latex
% \mycmd[opt1][opt2]{mand1}
\newcommandoptionals{\mycmd}[2][1]{...} 
```
The syntax `\newcommandoptionals{\cmd}[N][M]` defines a command with `N` optional arguments and `M` mandatory arguments. `N+M` must be at most 9.

You can specify default values for the optional arguments in the definition:
```latex
\newcommandoptionals{\mycmd}[2][1]{...}
% Arguments:
% 1. Optional (default: defined by first optional arg of \newcommandoptionals, here none specified so uses empty or standard behavior? Actually see documentation)
% Wait, the syntax is:
% \newcommandoptionals{\cmd}[N][M][Default1]...[DefaultN]{Body}
```
*Wait, looking at the code:*
```latex
% \newcommandoptionals{\cmd}[N][M]
% Followed by [Default1]...[DefaultN] 
```
Example:
```latex
\newcommandoptionals{\mycmd}[2][1][Def1][Def2]{Arg1: #1, Arg2: #2, Mand: #3}
```

## License
This work may be distributed and/or modified under the
conditions of the LaTeX Project Public License, either version 1.3
of this license or (at your option) any later version.
The latest version of this license is in
  http://www.latex-project.org/lppl.txt
and version 1.3 or later is part of all distributions of LaTeX
version 2005/12/01 or later.

This work has the LPPL maintenance status `maintained`.
The Current Maintainer of this work is "Sergio Martinez-Losa".
