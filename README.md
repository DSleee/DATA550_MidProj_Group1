# DATA 550 Midterm Project

> **Impact of Modified Milk Formula on Infant Severe Acute Malnutrition**
>
> Author: Santino Diaz-Palma, Dongsoo Lee, Victoria Ngo

## Table of contents

-   [General Info](#general-info)
-   [Usage](#usage)
-   [Quick Guide](#quick-guide)
-   [Repository Contents](#repository-contents)
    -   [Final Report](#final-report)
    -   [Code](#code)
    -   [Data](#data)
    -   [Output](#output)

## General Info

The base dataset is from a [**randomized trial**](https://pubmed.ncbi.nlm.nih.gov/30807589/) testing whether a modified milk formula (f75) improves outcomes for children with severe acute malnutrition (first 6-months of data from year-long study).

## Quick Guide
🚨**IMPORTANT:** If you want to change the dataset for analysis, please upload the new file to the data folder with the name `f75_interim.csv`, as the input filename has been fixed.

## 🧪 Report Generation without Docker

This method runs the project directly in your local R environment using `renv`.

### ✅ 1. Install required packages

```bash
make install
```

This will restore all necessary R packages based on `renv.lock`.

---

### 📝 2. Generate the report
** It is a default (table=TRUE figure=TRUE)
```bash
make
```

The generated report will be saved in the `project` folder.

---

> 💡 **Optional: Customize content**
>
> You can choose whether to include tables or figures in the report:
>
> ```bash
make report.html table=TRUE figure=FALSE
> ```
>
> - `table=TRUE` or `FALSE` &nbsp;&nbsp;&nbsp;→ include/exclude tables  
> - `figure=TRUE` or `FALSE` → include/exclude figures
> These options are passed to the rendering script and control output contents.


## Usage
Users can set params for `table` and `figure`. 
Both options accept `TRUE` or `FALSE`. Setting a param to `TRUE` means that the report will include the corresponding element (table or figure), while `FALSE` means that it will be excluded from the report.

1. Run `code/01_vn_make_table1.R`
    - This script generates the first table (output: `vn_table1.rds`).
2. Run `code/02_vn_make_table2.R`
    - This script generates the second table (output: `vn_table2.rds`).
3. Run `code/03_sdp_make_figure1.R`
    - This script generates the first figure (output: `sdp_figure1.png`).
4. Run `code/04_sdp_make_figure2.R`
    - This script generates the second figure (output: `sdp_figure2..png`).
5. Run `code/05_make_report.R table=TRUE figure=TRUE`
    - This script generates the final report using `report.Rmd`, along with the previously generated outputs (output: `report.html`).

* all output files saved in the `output` folder.

## Repository Contents

### *Final Report* 

The final report (report.Rmd) can be found in the root directory. An HTML report file (report.html) will be **generated after running the "make" command in the command console**.

The report contains a demographics table summarizing baseline characteristics of study participants, a table tracking changes of mid-upper arm circumference (MUAC) and weight changes over time, a figure of boxplots for continuous variables, and a figure of boxplots for MUAC and weight variables over time.

### *Code* 

Code for generating the tables, figures, and rendering the .Rmd report can be found in the "Code" subdirectory.

### *Data* 

The original data from [**this study**](https://pubmed.ncbi.nlm.nih.gov/30807589/) and the data dictionary can be found in the "Data" subdirectory.


### *Output* 

Once the codes for generating the tables and figures are run, the outputs will appear in the "output" subdirectory.

The final report file will appear in the project dictory.
