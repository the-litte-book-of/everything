---
title: The Little Book of Everything
subtitle: Version 0.1.0
author: Duc-Tam Nguyen
date: \today

papersize: a4
geometry:
  - a4paper
  - margin=2.5cm
  - heightrounded
fontsize: 12pt

toc: true
toc-depth: 2
numbersections: false   # don't ask Pandoc to number
mathjax: true
equation-numbering: none

pdf-engine: xelatex
mainfont: Noto Serif
monofont: Noto Sans Mono
# If available, uncomment one of these for consistent math glyphs:
# mathfont: Noto Serif Math
# mathfont: Latin Modern Math

# mainfont: Libertinus Serif
# monofont: Libertinus Mono
# mathfont: Libertinus Math

colorlinks: true
linkcolor: blue
urlcolor: blue

header-includes:
  - \usepackage{amsmath}   % already pulled in by Pandoc, but safe
  - \renewenvironment{equation}{\begin{equation*}}{\end{equation*}}
  
  #  typography & utilities 
  - \usepackage{microtype}

  #  single-source version macro (edit once here) 
  - \newcommand{\docversion}{0.1.1}

  #  FORCE no numbering (override Pandoc's \setcounter{secnumdepth}{5}) 
  - \setcounter{secnumdepth}{0}
  - \setcounter{tocdepth}{2} % keep TOC depth as desired

  #  ensure header marks show titles without numbers 
  - \makeatletter
  - \renewcommand{\sectionmark}[1]{\markboth{#1}{}}
  - \renewcommand{\subsectionmark}[1]{\markright{#1}}
  - \makeatother

  #  page style: title page plain, content fancy with version in footer 
  - \usepackage{fancyhdr}
  - \fancypagestyle{content}{%
      \fancyhf{}%
      \fancyhead[LE,RO]{\thepage}%
      \fancyhead[LO,RE]{\nouppercase{\leftmark}}%
      \fancyfoot[C]{Version \docversion}%
      \renewcommand{\headrulewidth}{0.4pt}%
      \setlength{\headheight}{13.6pt}%
    }
  - \usepackage{etoolbox}
  - \AtBeginDocument{\thispagestyle{plain}\pagestyle{content}}

  #  start every top-level section on a new page 
  - \let\oldsection\section
  - \renewcommand{\section}{\clearpage\oldsection}
---

42