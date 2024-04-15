# **ODU College of Sciences LaTeX ETD Template**

Welcome to the LaTeX Electronic Thesis and Dissertation (ETD) template for the College of Sciences at Old Dominion University. This template is designed to assist students in formatting their theses and dissertations according to the guidelines provided by the college.

## **Before You Begin**

- Please refrain from altering the spacing on any of the pages, as it is specified according to the guidelines provided by the College of Science.
- You may add any packages that you require for your ETD, but the base template may encounter issues when adding conflicting packages. Keep an eye out for errors and warnings that may arise during each compilation, especially when introducing new packages or implementing significant modifications.

## **Template Structure**

The template repository contains the following files and directories:

- **[main.tex](main.tex):** Main LaTeX document file, demonstrating various cases
- **[minimal.tex](minimal.tex):** LaTeX document file containing the minimal working example
- **[Chapters/](Chapters):** Folder containing .tex files for individual chapters.
- **[Figures/](Figures):** Folder for storing figures.
- **[ref.bib](ref.bib):** BibTeX bibliography file.
- **[odusci.sty](odusci.sty):** Style file for the College of Science Electronic Thesis and Dissertation (ETD)
- **README.md:** This README file providing instructions for using the template.

## **ETD LaTeX template on Overleaf**

This template is also hosted on [Overleaf](https://www.overleaf.com/), an online LaTeX editor.

You can view both the source and generated PDF of the ETD LaTeX template on Overleaf at <https://www.overleaf.com/read/srctgbpbygzp#51ddaa>

See the "Copying a project" (<https://www.overleaf.com/learn/how-to/Copying_a_project>) article at Overleaf for instructions on how to copy the project into your own space.

## **Getting Started**

#### **Font Size, Document Class, and Margins:**
- The font size throughout the document is set to 12 points, as required by the College of Sciences.
- The document class used is ‘report’, suitable for longer documents like dissertations.
- The margin is set uniformly to 1 inch around the document

#### **‘odusci’ Package options \[main.tex]:**

- The ‘odusci’ package is the default choice and it is used for PhD dissertations.

  ```\usepackage{odusci} ``` 

- For a Master's thesis, you can use the thesis option with the odusci package.

  ```\usepackage[thesis]{odusci}```

- The diss option can be used for PhD dissertations if desired.

  ```\usepackage[diss]{odusci}```

#### **References**
    1. **Bibliography \[ref.bib]**

       Ensure that your bibliography file (ref.bib) contains all the necessary references for your document.

       If you want to use a different filename for your references, you must change the file referenced in \addbibresource{ref.bib} in your main .tex file.     

    3. **Reference Citation Style \[main.tex]**

       The style file uses biblatex for formatting references. See "Bibliography management with biblatex"(<https://www.overleaf.com/learn/latex/Bibliography_management_with_biblatex>) for more information.

       The College of Sciences is allowing 3 different options for bibliography styles:

        - IEEE - commonly used by Computer Science, Physics, Math
        - APA - commonly used by Psychology
        - Science - commonly used by other sciences

       See "Biblatex bibliography styles" (<https://www.overleaf.com/learn/latex/Biblatex_bibliography_styles>) for examples of each of these.

       Select the appropriate bibliography style for your field by uncommenting one of the following lines in main.tex:

        ```% \usepackage[style=**ieee**, sorting=nyt, maxnames=10, minnames=10]{biblatex}```

        ```% \usepackage[style=**apa**, sorting=nyt, maxnames=10, minnames=10]{biblatex}```

        ```% \usepackage[style=**science**, sorting=nyt, maxnames=10, minnames=10]{biblatex}```

#### **Front Matter**
    1. **Title Page \[main.tex]**

       * Add the title, author name, prior degrees, department, submit date, and committee.
       
       * If the prior degrees are outside of the US, use the following format. (University and Country all in a single line)
       ```
       \degrees{B.S. July 2017, University of Oxford, United Kingdom. \\
       M.S. July 2020, University of Oxford, United Kingdom.}
       ```

       * Submit date can only be one of the below.        
       ```
       \submitdate{May 2022} - Submit date for May graduates
       \submitdate{August 2022} - Submit date for August graduates
       \submitdate{December 2022} - Submit date for December graduates
       ```

       * If you have co-advisers, use the following format.
         * In **\[main.tex]**
         ```\coadvisers{Director Name}
            \coadvisers{Director Name}
            \member{Member Name}
            \member{Member Name}
            \member{Member Name}
         ```
         
         * In **\[odusci.sty]**
           
         ```\onedirectorfalse```
       
         By default, the option is set to have one advisor. If you wish to have co-advisers, please change ‘\onedirectortrue’ to ‘\onedirectorfalse’.

    3. **Abstract \[main.tex]**
       * Please insert your abstract here, ensuring it does not exceed a maximum of 350 words.
       * The upper sections of the page, including the title, author, university, and director information, will be automatically generated based on the input provided on the title page. You do not need to make any modifications to the template regarding this section.
    1. **Copyrights \[main.tex]**
       * This page will be automatically generated based on the input of the author's name on the title page. You do not need to make any modifications to the template regarding this section.
    1. **Dedication \[main.tex]**
       * Please include your dedication here. Ensure that it does not exceed one page in length.
       * This section is used to recognize those who have supported you during your graduate studies.
    1. **Acknowledgments \[main.tex]**
       * This section is different from the dedication page. Recognition of individuals who contributed to your academic research should be provided here.
    1. **Table of Contents, List of Tables, and List of Figures**
       * These sections will be automatically generated based on the content of your document. You do not need to make any modifications to the template regarding these sections. LaTeX will handle the generation of the table of contents, list of tables, and list of figures for you.
    1. **Nomenclature**
        * In **\[main.tex]**
          
          The nomenclature page provides a comprehensive list of symbols and abbreviations used throughout the document, along with their corresponding definitions or explanations. Add your nomenclature in the provided format in the template. The inclusion of a nomenclature page is optional.

        * In **\[odusci.sty]**
                    
          ```\nomenclaturetrue```

          By default, the option is set to exclude the nomenclature page. If you wish to have a nomenclature page, you can change ‘\nomenclaturefalse’ to ‘\nomenclaturetrue’.

#### **Chapters and Sections**

* It is recommended to put the contents of each chapter in a separate .tex file in the "Chapters" folder.

* Start a new chapter with ```\chapter{Chapter Title}```

* Sections and subsections can be created as normal with ```\section{Section Title}``` and ```\subsection{Section Title}```.

#### **Figures and Tables**

* Figures, tables, and equations can be added as normal. There are several examples of these throughout the example document:

  - **figure** - 01_introduction.tex
  - **subfigure** - 02_background.tex
  - **landscape figure** - 02_background.tex
  - **equation** - 02_background.tex
  - **table** - 03_relatedwork.tex

#### **Appendix**

* The file Chapters/98_appendices.tex contains an example of specifying the appendices. The file starts with the keyword ```\appendix``` and each new appendix should begin with the line ```\achapter{Title of Appendix}```.

#### **Vita**

* The file Chapters/99_vita.tex contains an example of specifying the vita page. All of the content must be placed inside the ```\vita{}``` command, and the last line should be ```\vitapage```. It is important to note that the vita is limited to a maximum of 1 page.

## **Support**

College of Sciences Guidelines for Submitting a Thesis/Dissertation for Review:
<https://www.odu.edu/sci/students/graduate/thesis>

Overleaf Documentation:
<https://www.overleaf.com/learn>

