# ucm-math-thesis-template
This is a modification of the `report` document class templatea common LaTeX template for writing a dissertation at UC Merced aimed at satisfying the dissertation guidelines.  Please note this repo does not contain its own `.cls` file (it calls the built-in `report.cls` script when running `\documentclass`).

The most recent UC Merced dissertation guidelines document is found here: https://graduatedivision.ucmerced.edu/sites/graduatedivision.ucmerced.edu/files/documents/PDFs/ucm_thesis_dissertation_manual.pdf

## File Structure

In the primary folder, you will find `main.tex` which is the file that will need to be compiled each time to produce the document (`main.pdf`).  It uses a modular structure in that the scripts it calls are found in subfolders within this repo.  

### Text Files

The three folders that contain all of the `.tex`  files are the `Preliminary_Pages`, `Chapters`, and `Appendices` folders respectively.  

- `Preliminary_Pages` contains the documents placed at the beginning of the dissertation in order, starting with the title page and ending with the abstract.
- `Chapters` contains the main text of each chapter.  Each are shown as `Chapter_#.tex` for convenience, but can be renamed.
- `Appendices` contains the text for supplemetaray sections that do not belong in the main text, such as areas of great detail or large images or tables.

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

