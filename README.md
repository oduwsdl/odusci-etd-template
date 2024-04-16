# ODU College of Sciences LaTeX ETD Template

Welcome to the LaTeX Electronic Thesis and Dissertation (ETD) template for the College of Sciences at Old Dominion University. This template is designed to assist students in formatting their theses and dissertations according to the guidelines provided by the college.

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
  [`\usepackage{odusci}`](https://github.com/oduwsdl/odusci-etd-template/blob/62a6f1c63d76d7375941a522554ab5e2e9159af2/main.tex#L8)

- For a Master's thesis, you can use the `thesis` option  
  `\usepackage[thesis]{odusci}`

- The `diss` option can also be used for PhD dissertations, if desired  
  `\usepackage[diss]{odusci}`

### References

#### Bibliography

- Ensure that your bibliography file, [ref.bib](ref.bib), contains all the necessary references for your document.

- If you want to use a different filename for your references, you must change the file referenced in [`\addbibresource{ref.bib}`](https://github.com/oduwsdl/odusci-etd-template/blob/62a6f1c63d76d7375941a522554ab5e2e9159af2/main.tex#L29) in `main.tex`.     

#### Reference Citation Style
   
- The style file uses the `biblatex` Package for formatting references. See ["Bibliography management with biblatex"](https://www.overleaf.com/learn/latex/Bibliography_management_with_biblatex) for more information.

- The College of Sciences is allowing 3 different options for bibliography styles:
    - IEEE - commonly used by Computer Science, Physics, Math
    - APA - commonly used by Psychology
    - Science - commonly used by other sciences

- See ["Biblatex bibliography styles"](https://www.overleaf.com/learn/latex/Biblatex_bibliography_styles) for examples of each of these.

- Select the appropriate bibliography style for your field by uncommenting one of the following lines in `main.tex`:

    [`% \usepackage[style=ieee, sorting=nyt, maxnames=10, minnames=10]{biblatex}`](https://github.com/oduwsdl/odusci-etd-template/blob/62a6f1c63d76d7375941a522554ab5e2e9159af2/main.tex#L18)  
    [`% \usepackage[style=apa, sorting=nyt, maxnames=10, minnames=10]{biblatex}`](https://github.com/oduwsdl/odusci-etd-template/blob/62a6f1c63d76d7375941a522554ab5e2e9159af2/main.tex#L20)  
    [`% \usepackage[style=science, sorting=nyt, maxnames=10, minnames=10]{biblatex}`](https://github.com/oduwsdl/odusci-etd-template/blob/62a6f1c63d76d7375941a522554ab5e2e9159af2/main.tex#L22)

### Front Matter

#### Title Page

- Add the title, author name, prior degrees, department, submit date, and committee.
   
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
  * In **\[main.tex]**
  ```
  \coadvisers{Director Name}
  \coadvisers{Director Name}
  \member{Member Name}
  \member{Member Name}
  \member{Member Name}
  ```
     
  * In **\[odusci.sty]**  
  Comment out `\onedirectortrue` and uncomment `\onedirectorfalse`
   
#### Abstract 
- Please insert your abstract here, ensuring it does not exceed a maximum of 350 words.
- The upper sections of the page, including the title, author, university, and director information, will be automatically generated based on the input provided on the title page. You do not need to make any modifications to the template regarding this section.
  
#### Copyrights
- This page will be automatically generated based on the input of the author's name on the title page. You do not need to make any modifications to the template regarding this section.
     
#### Dedication 
- Please include your dedication here. Ensure that it does not exceed one page in length.
- This section is used to recognize those who have supported you during your graduate studies.
     
#### Acknowledgments 
- This section is different from the dedication page. Recognition of individuals who contributed to your academic research should be provided here.
     
#### Table of Contents, List of Tables, and List of Figures
- These sections will be automatically generated based on the content of your document. You do not need to make any modifications to the template regarding these sections. LaTeX will handle the generation of the table of contents, list of tables, and list of figures for you.
     
#### Nomenclature
  If you need to add a Nomenclature list, you must made adjustments in both `main.tex` and `odusci.sty`

- In **\[main.tex]**

  The nomenclature page provides a comprehensive list of symbols and abbreviations used throughout the document, along with their corresponding definitions or explanations. Add your nomenclature in the provided format in the template. The inclusion of a nomenclature page is optional.

- In **\[odusci.sty]**  
  Comment out `\nomenclaturefalse` and uncomment `\nomenclaturetrue`

### Chapters and Sections

- It is recommended to put the contents of each chapter in a separate .tex file in the "Chapters" folder.

- Start a new chapter with `\chapter{Chapter Title}`

- Sections and subsections can be created as normal with `\section{Section Title}` and `\subsection{Section Title}`.

### Figures and Tables

- Figures, tables, and equations can be added as normal. There are several examples of these throughout the example document:

  - figure - [01_introduction.tex](https://github.com/oduwsdl/odusci-etd-template/blob/62a6f1c63d76d7375941a522554ab5e2e9159af2/Chapters/01_introduction.tex#L10)
  - subfigure - [02_background.tex](https://github.com/oduwsdl/odusci-etd-template/blob/62a6f1c63d76d7375941a522554ab5e2e9159af2/Chapters/02_background.tex#L23)
  - landscape figure - [02_background.tex](https://github.com/oduwsdl/odusci-etd-template/blob/62a6f1c63d76d7375941a522554ab5e2e9159af2/Chapters/02_background.tex#L49)
  - equation - [02_background.tex](https://github.com/oduwsdl/odusci-etd-template/blob/62a6f1c63d76d7375941a522554ab5e2e9159af2/Chapters/02_background.tex#L42)
  - table - [03_relatedwork.tex](https://github.com/oduwsdl/odusci-etd-template/blob/62a6f1c63d76d7375941a522554ab5e2e9159af2/Chapters/03_relatedwork.tex#L17)

### Appendix

- [`Chapters/98_appendices.tex`](https://github.com/oduwsdl/odusci-etd-template/blob/main/Chapters/98_appendices.tex) contains an example of specifying the appendices. The file starts with the keyword `\appendix` and each new appendix should begin with the line `\achapter{Title of Appendix}`.

### Vita

- [`Chapters/99_vita.tex`](https://github.com/oduwsdl/odusci-etd-template/blob/main/Chapters/99_vita.tex) contains an example of specifying the vita page. All of the content must be placed inside the `\vita{}` command, and the last line should be `\vitapage`. It is important to note that the vita is limited to a maximum of 1 page.

## Support

- College of Sciences Guidelines for Submitting a Thesis/Dissertation for Review:
<https://www.odu.edu/sci/students/graduate/thesis>

- Overleaf Documentation:
<https://www.overleaf.com/learn>
