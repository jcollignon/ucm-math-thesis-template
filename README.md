# ucm-math-thesis-template
This is a modification of the built-in `report` document class LaTeX template for writing a dissertation at UC Merced aimed at satisfying the dissertation guidelines.  Please note this repo does not contain its own `.cls` file.  As such, any definitions you plan to use in your dissertation will need to be directly defined by you.

The most recent UC Merced Dissertation Guidelines document is found here: https://graduatedivision.ucmerced.edu/sites/graduatedivision.ucmerced.edu/files/documents/PDFs/ucm_thesis_dissertation_manual.pdf

The template provided in this repository has been used to prepare my dissertation, and the content submitted has passed the necessary checks on the Proquest platform on July 24th, 2024.

DISCLAIMER: While the tools I used to format my dissertation were compliant with the guidelines, not all guidelines applied to my document.  As such, you may encounter some elements (such as illustrations, etc) that have not been adjusted to meet the guidelines.  If you encounter anything that does not meet the current dissertation guidelines, please let me know and I will update the repo periodically.  If you have formatting code to send me so I can test to see if it works with this template, please include this under Issues.

Below is information on the structure of this repository, conventions used for some elements throughout the template, and other possible suggestions that have come to mind.

## 1. Repo Structure

In the primary folder, you will find `main.tex` which is the file that will need to be compiled each time to produce the document (`main.pdf`).  It uses a modular structure in that the scripts it calls are found in subfolders within this repo.  

### 1a. Text Files

The three folders that contain all of the `.tex`  files are the `Preliminary_Pages`, `Chapters`, and `Appendices` folders respectively.  

- `Preliminary_Pages` contains the documents placed at the beginning of the dissertation in order, starting with the title page and ending with the abstract.
- `Chapters` contains the main text of each chapter.  Each are shown as `Chapter_#.tex` for convenience, but can be renamed.
- `Appendices` contains the text for supplemetaray sections that do not belong in the main text, such as areas of great detail or large images or tables.

### 1b. Figures

All images for figures are placed within subdirectories of the `Figures` folder.  Each subdirectory should correspond to a single chapter in order to conveniently ensure the locations of each image in a chapter are easy to grab.  An example image `figure_placeholder.png` is in a subdirectory whose relative directory is `Figures/Chapter_1/figure_placeholder.png`.

### 1c. References

In the main directory there is a file named `references.bib` that contains reference information on papers used for doing in-text citations.  Citation info can be collected from Google Cholar on a paer you are referencing.  Update the reference as needed, especially if there's info that is not showing up or is incorrect.

### 1d. Packages

In the main directory there is a file named `packages_formatting.tex` which is where all the `usepackage{}` commands and formatting specifications are called.  Additional detail is provided on the parameters of the package.  A couple of important packages to take note of are:

- `\usepackage{geometry}`: used to specify the type of paper (8.5" x 11") and all of the margins of the document.
- `\usepackage{fancyhdr}`: used to customize the areas in the margins of the document, such as the location of page numbers.
- `\usepackage{caption}`: useed to ensure that figures and tables placed in the appendices do not appear in the list of figures/tables as per the guidelines.  This is needed to call `\captionsetup[figure]{list=no}` and `\captionsetup[table]{list=no}` at the start of the Appendices.

Other packages can be added as needed.

### 1e. References
The primary directory contains a file names `references.bib` which stores all bibiolographical information in the BibTex format.  For each paper you ned to cite, got th Google Scholar, type the name of the paper, click "Cite", and then click the "BibTex" option.  You'll be given the formatted BibTex code for that paper that you can copy and paste into `references.bib`.  If there are issues inside the formatted code, edit it in a way where the original info is still interpretable.  The end of the `main.tex` script has a section which loads the references section showing only the materials cited.  You can add as many references in the bib fiel as you like, but only the sources you have cited in the paper will be generated in the output pdf file, so go crazy!

### 1f. Full Structure
The detailed file structure in this repo is defined as follows:
```
.
├── Appendices
│   ├── Appendix_A.tex
│   └── Appendix_B.tex
├── Chapters
│   ├── Chapter_1.tex
│   ├── Chapter_2.tex
│   ├── Chapter_3.tex
│   └── Chapter_4.tex
├── Figures
│   ├── Chapter_1
│   │   └── figure_placeholder.png
│   ├── Chapter_2
│   │   └── figure_placeholder.png
│   ├── Chapter_3
│   └── Chapter_4
├── Preliminary_Pages
│   ├── abstract.tex
│   ├── acknowledgements_page.tex
│   ├── copyright_page.tex
│   ├── cv.tex
│   ├── dedication_page.tex
│   ├── list_of_figures.tex
│   ├── list_of_illustrations.tex
│   ├── list_of_symbols.tex
│   ├── list_of_tables.tex
│   ├── signature_page.log
│   ├── signature_page.tex
│   └── title_page.tex
├── main.pdf
├── main.tex
├── packages_formatting.tex
└── references.bib
```

## 2. Reading in Chapters and Images

All the `.tex` fiiles for the main text, appendices, and preliminaries are called in the mian script using `\input{location of tex file}`.  For Chapters this is done using `\input{Chapters/Chapter_#.tex}`.

All images or figures are called using their relative locations.  For example, `\includegraphics[width=\textwidth]{Figures/Chapter_1/figure_plateholder.png}`.

## 3. Formatting Specifications

### 3a. Adding a Figure

A figure block should look like the following:

```
\begin{figure}[hbtp]
  \centering
  \includegraphics[width=\textwidth]{Figures/Chapter_1/figure_plateholder.png}
  \caption[List of Figures text]{Main caption text.}
  \label{fig:figure1}
\end{figure}
```
All captions for figures should be below the figure.  The list of figures should contain the title of the figure, which you can enter in `List of Figures text`.  Always place `\label` immediately following the caption to ensure the correct page number is shown in the list of figures.  If the figure cannot fit on the same page as the caption, the page number containing the title and caption of the figure will be referenced in the list of figures.

### 3b. Adding a Table

A table block should look like the following:

```
\begin{table}[hbtp]
	\centering
	\caption[List of Tables text]{Main Caption text.}
	\begin{tabular}{|c|c|c|c|}
	\hline
	This & is & a & table.
	\hline
	\end{tabular}
	\label{tab:table1}
\end{figure}
```
All captions for tables should be above the figure.  The list of tables should contain the title of the table, which you can enter in `List of Tables text`.  Always place `\label` immediately following the caption to ensure the correct page number is shown in the list of tables.  If the table cannot fit on the same page as the caption, the page number containing the titla and caption of the table will be referecens in the list of tables.

# Things to Investigate

## 1. Current suggestions to investigate

- Figure: In one `figure` environment, images and captions always overflow and are not separated into multiple pages.
- Currently not setup to change how footnotes and endnotes are formatted.  Default setting is currently applied, haven't checked if this meets the guidelines.

## 2. Recent Changes

TBD

