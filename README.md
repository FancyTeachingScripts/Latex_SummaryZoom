# Latex SummaryZoom
A small Latex library working similar to power points summary zoom based on an answer by [Steven B. Segletes](https://tex.stackexchange.com/users/25858/steven-b-segletes) in [this](https://tex.stackexchange.com/questions/224267/how-to-include-a-preview-of-next-slide-in-beamers-speaker-notes) TexExchange thread.

For a defined set of slides, it creates a summary slide with clickable previews to each slide. The summary slide can be used to quickly navigate to any of the slides in the set and offer a quick overview of the content.

It offers options to show the summary at the beginning of a defined set of slides or both before and after the set. Additionally it is possible to show all slides since the last summary zoom in the first line and the slides of the upcoming section in the second line. This is e.g. helpful for multiple seminar sessions or lectures. A summary slide can either define a latex section or work independently of the section structure.

Besides the sample code in the main.tex of this repository, the following code snippet shows how to use the library in a beamer document.

**Compile with LuaLatex (or if not available with Xelatex)!**
Tested with TexLive 2024 in Overleaf.

```Tex
\documentclass[aspectratio=169]{beamer}
\usepackage{sty/SummaryZoom}

% Recommended theming:
\usetheme{moloch} % More modern theme. Comment out for default theme. 
\usecolortheme{owl} % ~Darkmode (looks ugly with moloch-light theme)
\setbeamertemplate{navigation symbols}{} % Remove navigation 

\ZoomSection % \ZoomSection or \Zoom (without creating a section)
{Some title} % Zoom (and Section) title
{false} % true/false: Repeat summary Zoom after slides 
{false} % true/false: Show previous (since last summary zoom)
{
    \begin{sframe}{Frame title} 
        Use sframe instead of frame to create a slide
        that is part of the summary zoom.
    \end{sframe}
}
```



It's not too pretty yet but offer is constantly improving :)



