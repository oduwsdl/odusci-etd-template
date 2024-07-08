# ODU College of Sciences LaTeX ETD Template

Welcome to the LaTeX Electronic Thesis and Dissertation (ETD) template for the College of Sciences at Old Dominion University. This template is designed to assist students in formatting their theses and dissertations according to the guidelines provided by the university. Those using this template must still abide by the guidelines and formatting requirements found in the [ODU Guide for Preparation of Theses and Dissertations](https://www.odu.edu/graduateschool/thesis-dissertation-preparation-submission) ([PDF](https://www.odu.edu/sites/default/files/2024/documents/thesis-dissertation-guide-03-2024.pdf), last updated March 2024).

Note that using this template removes the requirement that you submit a "journal model" with your thesis or dissertation, as noted on the College of Sciences [Check-in Sheet](https://www.odu.edu/sites/default/files/documents/check-in.pdf). You just need to check the box on the form that you have used the LaTeX template.

## Before You Begin

- Please refrain from altering the spacing on any of the pages, as it is specified according to the guidelines provided by the College of Science.
- You may add any packages that you require for your ETD, but the base template may encounter issues when adding conflicting packages. Keep an eye out for errors and warnings that may arise during each compilation, especially when introducing new packages or implementing significant modifications.

## Template Structure

The template repository contains the following files and directories:

- [odusci.sty](odusci.sty): Style file for the College of Sciences Electronic Thesis and Dissertation (ETD)
- [main.tex](main.tex): Main LaTeX document file, demonstrating various cases
- [main.pdf](main.pdf): PDF generated with `main.tex`
- [minimal.tex](minimal.tex): LaTeX document file containing the minimal working example
- [minimal.pdf](main.pdf): PDF generated with `minimal.tex`
- [ref.bib](ref.bib): BibTeX bibliography file
- [Chapters/](Chapters): Folder containing .tex files for individual chapters
- [Figures/](Figures): Folder for storing figures
- README.md: This README file providing instructions for using the template.

## ETD LaTeX Template on Overleaf

This template is also hosted on [Overleaf](https://www.overleaf.com/), an online LaTeX editor.

You can view both the source and generated PDF of the ETD LaTeX template on Overleaf at <https://www.overleaf.com/read/srctgbpbygzp#51ddaa>

See ["Copying a project"](https://www.overleaf.com/learn/how-to/Copying_a_project) at Overleaf for instructions on how to copy the project into your own space.

## Using the Template

Most of the customization you need to make is isolated to `main.tex`. Do not edit `odusci.sty` unless absolutely necessary.

### Font Size, Document Class, and Margins
- The font size throughout the document is set to 12 points, as required by the College of Sciences.
- The document class used is ‘report’, suitable for longer documents like dissertations.
- The margin is set uniformly to 1 inch around the document

### `odusci` Package options

- The default setting of the `odusci` package is for PhD dissertations  
  [`\usepackage{odusci}`](https://github.com/oduwsdl/odusci-etd-template/blob/main/main.tex#L12)

- For a Master's thesis, you can use the `thesis` option  
  `\usepackage[thesis]{odusci}`

- The `diss` option can also be used for PhD dissertations, if desired  
  `\usepackage[diss]{odusci}`

### References

#### Bibliography

- Ensure that your bibliography file, [ref.bib](ref.bib), contains all the necessary references for your document.

- If you want to use a different filename for your references, you must change the file referenced in [`\addbibresource{ref.bib}`](https://github.com/oduwsdl/odusci-etd-template/blob/main/main.tex#L27) in `main.tex`.     

#### Reference Citation Style
   
- The style file uses the `biblatex` Package for formatting references. See ["Bibliography management with biblatex"](https://www.overleaf.com/learn/latex/Bibliography_management_with_biblatex) for more information. Here are a few other references for biblatex:
    - [The biblatex Package](https://mirrors.rit.edu/CTAN/macros/latex/contrib/biblatex/doc/biblatex.pdf) - in particular, see "3.9 Citation Commands" (pg 110)
    - [A very quick introduction to managing citations in LaTeX](https://andreasmhallberg.github.io/managing-citations-in-latex/)

- The College of Sciences is allowing 3 different options for bibliography styles (see ["Biblatex bibliography styles"](https://www.overleaf.com/learn/latex/Biblatex_bibliography_styles) for examples of each of these):
    - IEEE - commonly used by Computer Science, Physics, Math
    - APA - commonly used by Psychology
    - Science - commonly used by other sciences

- Select the appropriate bibliography style for your field by uncommenting one of the following lines in `main.tex`:

    [`% \usepackage[style=ieee, sorting=nyt, maxnames=10, minnames=10]{biblatex}`](https://github.com/oduwsdl/odusci-etd-template/blob/main/main.tex#L20)  
    [`% \usepackage[style=apa, sorting=nyt, maxnames=10, minnames=10]{biblatex}`](https://github.com/oduwsdl/odusci-etd-template/blob/main/main.tex#L22)  
    [`% \usepackage[style=science, sorting=nyt, maxnames=10, minnames=10]{biblatex}`](https://github.com/oduwsdl/odusci-etd-template/blob/main/main.tex#L24)

- If you want your references to be listed in the order they are cited in your text rather than alphabetically by first author's last name, change `sorting=nyt` to `sorting=none` in the `biblatex` options line.

### Front Matter

#### Title Page

- Add the title, author name, prior degrees, department, submit date, and committee, starting on [line 33](https://github.com/oduwsdl/odusci-etd-template/blob/main/main.tex#L33) in `main.tex`
   
- If the prior degrees are outside of the US, use the following format. (University and country must be on the same line.)
  ```
  \degrees{B.S. July 2017, University of Oxford, United Kingdom. \\
  M.S. July 2020, University of Oxford, United Kingdom.}
  ```

- The submit date must use either "May", "August", or "December" for the month:
  ```
  \submitdate{May 2024} - Submit date for May (Spring) graduates
  \submitdate{August 2024} - Submit date for August (Summer) graduates
  \submitdate{December 2024} - Submit date for December (Fall) graduates
  ```

- If you have co-advisers, you must make adjustments in both `main.tex` and `odusci.sty`
  * In **\[main.tex]**, comment out [lines 59-62](https://github.com/oduwsdl/odusci-etd-template/blob/main/main.tex#L59-L62) and uncomment [lines 65-69](https://github.com/oduwsdl/odusci-etd-template/blob/main/main.tex#L65-L69):
  ```
  \coadvisers{Director Name}
  \coadvisers{Director Name}
  \member{Member Name}
  \member{Member Name}
  \member{Member Name}
  ```
     
  * In **\[odusci.sty]**, comment out `\onedirectortrue` ([line 65](https://github.com/oduwsdl/odusci-etd-template/blob/main/odusci.sty#L65)) and uncomment `\onedirectorfalse` ([line 66](https://github.com/oduwsdl/odusci-etd-template/blob/main/odusci.sty#L66))
   
#### Abstract 
- Insert your abstract starting on [line 76](https://github.com/oduwsdl/odusci-etd-template/blob/main/main.tex#L76), ensuring it does not exceed a maximum of 350 words.
- The upper sections of the page, including the title, author, university, and director information, will be automatically generated based on the input provided on the title page. You do not need to make any modifications to the template regarding this section.
  
#### Copyrights
- This page will be automatically generated based on the input of the author's name on the title page. You do not need to make any modifications to the template regarding this section.
     
#### Dedication 
- Include your dedication starting on [line 79](https://github.com/oduwsdl/odusci-etd-template/blob/main/main.tex#L79). Ensure that it does not exceed one page in length.
- This section is used to recognize those who have supported you during your graduate studies.
     
#### Acknowledgments 
- Include your acknowledgements starting on [line 82](https://github.com/oduwsdl/odusci-etd-template/blob/main/main.tex#L82)
- This section is for recognition of individuals who contributed to your academic research should be provided here.
- Note that if you want multiple paragraphs, you must explicitly add newline and indent commands: `\\ \indent`
     
#### Table of Contents, List of Tables, and List of Figures
- These sections will be automatically generated based on the content of your document. You do not need to make any modifications to the template regarding these sections. LaTeX will handle the generation of the table of contents, list of tables, and list of figures for you.
     
#### Nomenclature
  If you need to add a Nomenclature list, you must made adjustments in both `main.tex` and `odusci.sty`

- In **\[main.tex]**

  The nomenclature page provides a comprehensive list of symbols and abbreviations used throughout the document, along with their corresponding definitions or explanations. Add your nomenclature in the provided format in the template ([lines 88-95](https://github.com/oduwsdl/odusci-etd-template/blob/main/main.tex#L88-L95)). The inclusion of a nomenclature page is optional.

- In **\[odusci.sty]**, comment out `\nomenclaturefalse` ([line 58](https://github.com/oduwsdl/odusci-etd-template/blob/main/odusci.sty#L58)) and uncomment `\nomenclaturetrue` ([line 59](https://github.com/oduwsdl/odusci-etd-template/blob/main/odusci.sty#L59))

### Chapters and Sections

- It is recommended to put the contents of each chapter in a separate .tex file in the "Chapters" folder.
- Then use the `\input` command to insert the chapters into your main file, as shown in [lines 107-114](https://github.com/oduwsdl/odusci-etd-template/blob/main/main.tex#L107-L114)
- Start a new chapter with `\chapter{Chapter Title}`
- Sections and subsections can be created as normal with `\section{Section Title}` and `\subsection{Section Title}`.

### Figures and Tables

- Figures, tables, and equations can be added as normal. There are several examples of these throughout the example document:

  - figure - [01_introduction.tex](https://github.com/oduwsdl/odusci-etd-template/blob/main/Chapters/01_introduction.tex#L10)
  - subfigure - [02_background.tex](https://github.com/oduwsdl/odusci-etd-template/blob/main/Chapters/02_background.tex#L23)
  - landscape figure - [02_background.tex](https://github.com/oduwsdl/odusci-etd-template/blob/main/Chapters/02_background.tex#L45)
  - equation - [02_background.tex](https://github.com/oduwsdl/odusci-etd-template/blob/main/Chapters/02_background.tex#L39)
  - table - [03_relatedwork.tex](https://github.com/oduwsdl/odusci-etd-template/blob/main/Chapters/03_relatedwork.tex#L17)

### Appendix

- [`Chapters/98_appendices.tex`](https://github.com/oduwsdl/odusci-etd-template/blob/main/Chapters/98_appendices.tex) contains an example of specifying the appendices. The file starts with the keyword `\appendix` and each new appendix should begin with the line `\achapter{Title of Appendix}`.

### Vita

- [`Chapters/99_vita.tex`](https://github.com/oduwsdl/odusci-etd-template/blob/main/Chapters/99_vita.tex) contains an example of specifying the vita page. All of the content must be placed inside the `\vita{}` command, and the last line should be `\vitapage`. It is important to note that the vita is limited to a maximum of 1 page.

## Support

- College of Sciences Guidelines for Submitting a Thesis/Dissertation for Review:
<https://www.odu.edu/sci/students/graduate/thesis>

- Overleaf Documentation:
<https://www.overleaf.com/learn>
