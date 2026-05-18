# chalmers-beamer-template-2026
A LaTeX Beamer theme for Chalmers University of Technology presentations, updated for 2026 with the new Chalmers identity.

> **Disclaimer:** This repository is an updated version of the original theme from [chaeger/chalmers-beamer](https://github.com/chaeger/chalmers-beamer).

## Overview
This repository contains a custom Beamer theme and a template presentation for Chalmers-style slides. The theme includes the Chalmers color palette, header/footer layout, and the new Chalmers wordmark/emblem artwork.

## Repository structure
- `template/` – example presentation and theme files.
- `template/beamerthemeChalmers.sty` – the custom Beamer theme package.
- `template/chalmers_emblem_white.pdf`, `template/chalmers_wordmark_white.pdf` – artwork files used by the theme.
- `LICENSE` – license for the repository.

## Usage
1. Copy `beamerthemeChalmers.sty` and the required Chalmers artwork files into the same folder as your presentation `.tex` file.
2. In your Beamer document, load the theme with:

```tex
\documentclass[aspectratio=169]{beamer}
\usetheme[footline=authortitle,shadow=true]{Chalmers}
\setbeamertemplate{navigation symbols}{}
```

3. Set your title metadata as usual:

```tex
\title{My Presentation Title}
\subtitle{Optional Subtitle}
\author[Short Author]{Full Author Name}
\institute[Chalmers]{Chalmers University of Technology}
\date{\today}
```

4. Compile with `pdflatex` or `latexmk`:

```bash
cd template
pdflatex template.tex
```

or

```bash
latexmk -pdf template.tex
```

## Example
The example presentation is located in `template/template.tex`. It demonstrates:
- how to load the theme,
- the default slide title page,
- the outline page,
- standard frame structure for sections and content.

## Installation
### Local installation
Put the `.sty` file and artwork files in the same directory as your `.tex` source.

### TeX tree installation
Place the theme file in your personal TeX tree, for example:

```bash
mkdir -p "$(kpsewhich -var-value=TEXMFHOME)/tex/latex/beamer/Chalmers"
cp template/beamerthemeChalmers.sty template/chalmers_*.pdf template/chalmers_*.svg "$TEXMFHOME/tex/latex/beamer/Chalmers/"
```

Then update the TeX file database if needed:

```bash
texhash "$TEXMFHOME"
```

## Notes
- The theme expects `chalmers_wordmark_white` and `chalmers_emblem_white` artwork files to be available in the same directory or in the TeX search path.
- If you want a faster compile workflow, use `latexmk -pdf` and keep the generated artifacts out of source control.

## License
See the `LICENSE` file for repository licensing information.

