# **ODU College of Sciences LaTeX ETD Template**

Welcome to the LaTeX Electronic Thesis and Dissertation (ETD) template for the College of Sciences at Old Dominion University. This template is designed to assist students in formatting their theses and dissertations according to the guidelines provided by the college.

## **Before You Begin**

- Please refrain from altering the spacing on any of the pages, as it is specified according to the guidelines provided by the College of Science.
- You may add any packages that you require for your ETD, but the base template may encounter issues when adding conflicting packages. Keep an eye out for errors and warnings that may arise during each compilation, especially when introducing new packages or implementing significant modifications.

## **Template Structure**

The template repository contains the following files and directories:

- **main.tex:** Main LaTeX document file, demonstrating various cases
- **minimal.tex:** LaTeX document file containing the minimal working example
- **Chapters/:** Folder containing .tex files for individual chapters.
- **Figures/:** Folder for storing figures.
- **ref.bib:** BibTeX bibliography file.
- **odusci.sty:** Style file for the College of Science Electronic Thesis and Dissertation (ETD)
- **README.md:** This README file providing instructions for using the template.

## **ETD LaTeX template on Overleaf**

This template is also hosted on [Overleaf](https://www.overleaf.com/), an online LaTeX editor.

You can view both the source and generated PDF of the ETD LaTeX template on Overleaf at <https://www.overleaf.com/read/srctgbpbygzp#51ddaa>

See the "Copying a project" (<https://www.overleaf.com/learn/how-to/Copying_a_project>) article at Overleaf for instructions on how to copy the project into your own space.

## **Getting Started**

1. **Font Size, Document Class, and Margins:**
- The font size throughout the document is set to 12 points, as required by the College of Sciences.
- The document class used is ‘report’, suitable for longer documents like dissertations.
- The margin is set uniformly to 1 inch around the document

2. **‘odusci’ Package options \[main.tex]:**

- The ‘odusci’ package is the default choice and it is used for PhD dissertations.

  ```\usepackage{odusci} ``` 

- For a Master's thesis, you can use the thesis option with the odusci package.

  ```\usepackage\[thesis]{odusci}```

- The diss option can be used for PhD dissertations if desired.

  ```\usepackage\[diss]{odusci}```

3. **References**
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

        ```% \usepackage\[style=**ieee**, sorting=nyt, maxnames=10, minnames=10]{biblatex}```

        ```% \usepackage\[style=**apa**, sorting=nyt, maxnames=10, minnames=10]{biblatex}```

        ```% \usepackage\[style=**science**, sorting=nyt, maxnames=10, minnames=10]{biblatex}```
