# FVS Modeling for the Black Hills National Forest Management Plan

## Description of the project

Built with Quarto and R, this project combines narrative text, code execution, and output in multiple formats (HTML, Word, and PDF).

🌐 GitHub Pages

The rendered report is published and publicly accessible at:

## 📂 Project Structure

- `index.qmd`: The landing page/preface of the report

- `_quarto.yml`: The YAML configuration file for the report's structure and styling

- `CITATION.cff`: Citation file

- `Template.Rproj`: The R project file

- `references.bib`: BibTeX file for citations

- `references.qmd`: The reference section of the report

- `forest-ecology-and-management.csl`: A citation style library file for formatting citations

- `renv/`: Reproducible environment files

- `renv.lock`: A plain text file with the exact versions of every R package used

- `.github/workflows/publish.yml`: A YAML file that tells GitHub Actions to publish the report to GitHub Pages whenever changes are pushed to the `main` branch

- `_freeze`:

- `custom-reference-doc.docx`: A template word document for formatting output word files

**🛠️ Prerequisites**

Before rendering the report, you need to install the following tools:

1.  **R**: Download and install the latest version from CRAN.
2.  **RStudio**: Download and install the latest version of RStudio from Posit.
3.  **Quarto**: This is bundled with RStudio, but you can also download the standalone CLI from the Quarto Website.
4.  **GDAL**: Download and install from [https://gdal.org](https://gdal.org/en/stable/)

## **📦 R** Environment Setup & Dependency Management

This project uses **`{renv}`** to manage R packages and ensure reproducibility. This means that when you build the report, it will use the exact same R version and package versions that were used during initial development.

**For Local R Users**

1.  Clone the repository to your local machine.

2.  Open the project in [RStudio](https://posit.co/download/rstudio-desktop/)

3.  You will see a console message indicating that **`{renv}`** has loaded.

4.  **`{renv}`** should automatically install the packages used, but if not run the following command in your R console to install the exact packages needed:

    ```         
    renv::restore()
    ```

## ⚙️ **How to Render the Report**

You can render the book either through the RStudio or directly via the command line.

**Method 1: Using RStudio**

1.  Open the project folder in RStudio.
2.  In the top-right pane, click on the **Build** tab.
3.  Click the **Render Book** button.

**Method 2: Using the Command Line/Terminal**

Open your terminal or command prompt, navigate to the project directory, and run the following command:

```         
quarto render
```

**Rendering Specific Formats**

If you only want to render a specific format instead of all formats configured in `_quarto.yml`, use one of these commands:

```         
quarto render --to html
quarto render --to pdf
```

## **🚀 How to Publish the Report to Github pages**

Publishing is handled automatically via GitHub Actions whenever changes are pushed to the `main` branch. The workflow uses Quarto's freeze feature to avoid re-executing R code, so no R installation is required on the runner.

To trigger a publish, simply push your changes to `main` through the RStudio or directly via the command line.

**Method 1: Using RStudio**

1.  In the top-right pane, click on the **Git** tab.
    2.  Check the box next to any files you want to commit in the staged column.

    3.  Click **Commit**, add a commit message describing your changes, and click **Commit** again.

    4.  Click **Push** (the green upward arrow) to push your changes to GitHub.

**Method 2: Using the Command Line/Terminal**

Open your terminal or command prompt, navigate to the project directory, and run the following command:

```         
git push origin main
```

The workflow will:

1.  Check out the repository
2.  Set up Quarto
3.  Publish the frozen outputs to the `gh-pages` branch

To update the frozen outputs locally before pushing, render the report and then commit the updated `_freeze/` directory along with your changes.

## License

This project is licensed under the MIT License - see the LICENSE.md file for details

## Citation

Please cite this work following the Citation.cff file
