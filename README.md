# unslantgreek Package

## Package Name
`unslantgreek.sty`

## Description
The `unslantgreek` package provides upright (non-slanted) versions of Greek letters in mathematical notation. By default, LaTeX Greek letters are italicized, which can be undesirable in certain mathematical contexts. This package allows users to easily display upright Greek letters throughout a document while retaining access to the original slanted versions with a simple prefix. 

It does work with any font but slant factor is adjusted to work with default Computer Modern font.  Package helps to follow the French and Russian math tradition as concerns greek letters in maths, is that they are `upright`.

XeLaTeX  not tested works in pdflatex.

## Features
- **Upright Greek Letters**: Automatically transforms Greek letters into an upright (non-italicized) style for improved clarity in mathematical and technical documents.
- **Original Greek Letters Access**: Allows access to the original slanted (italicized) Greek letters using suffix commands (e.g., `\alphasl` for slanted alpha).
- **Customizable Slant Factor**: Users can adjust the default slant factor if needed to suit different font styles.

## Installation
Place the `unslantgreek.sty` file in the same directory as your LaTeX document, or in a directory where your LaTeX distribution can find it.

## Usage
1. Load the package in your LaTeX document preamble:
   ```latex
   \usepackage{unslantgreek}
   ```

2. **Upright Greek Letters**: Use Greek letter commands as usual, and they will appear upright by default:
   ```latex
   $\alpha \beta \gamma \delta \epsilon$
   ```

3. **Access to Slanted (Original) Greek Letters**: To use the original slanted versions, use the `\sl` suffix with the Greek letter (e.g., `\alphasl` for slanted alpha):
   ```latex
   $\alphasl \betasl \gammasl \deltasl \epsilonsl$
   ```

## Customization
All customization can be done by editing `unslantgreek.sty`.
- **Adjusting the Slant Factor**: The default slant factor is set to `-.25`, which works well for most fonts. To customize this, modify the `\unslant` command in the package file or redefine it in your document:
  
  ```latex
  \renewcommand\unslant[2][-.20]{\slantbox[#1]{$#2$}}
  ```

  This changes the default unslant factor to `-.20`.
-  **Adjusting the Slant Factor for Individual Letters**: You can also adjust the slant factor for specific Greek letters if needed. For example, to apply a different slant factor only to `\delta`, use the following:

   ```latex
   \let\deltasl=\delta   \def\delta{\unslant[-.15]{\deltasl}}
   ```
   This sets the slant factor for `\delta` to `-.15` while keeping other Greek letters at the default value.

## Example

Here is an example LaTeX document using the `unslantgreek` package:

```latex
\documentclass{article}
\usepackage{unslantgreek}

\begin{document}

% Upright Greek letters by default
$\alpha \beta \gamma \delta \epsilon$

% Access original slanted versions
$\alphasl \betasl \gammasl \deltasl \epsilonsl$

\end{document}
```

## License
This package is released under the LaTeX Project Public License (LPPL).

## Version History
- **Version 1.0** - Initial release with upright Greek letters and access to original slanted versions.

