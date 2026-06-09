# analysisdedatos

R analysis of research variables collected from animal subjects in tumor-growth studies.

## Variables (from `R Raw Data.csv`)

| Variable | Description |
|---|---|
| `Tiempo (sem)` | Time in weeks (decimal comma format) |
| `¿Llegó a término?` | Terminal endpoint indicator (`1` = Yes, `0` = No) |
| `Sexo` | Sex category (`Macho` or `Hembra`) |

## Files

```
analysis.Rmd          # Main R Markdown analysis (open in RStudio and knit)
R Raw Data.csv        # Main dataset used by analysis.Rmd
data/sample_data.csv  # Optional template dataset
```

## Usage

1. **Install R and RStudio** if you have not already.
2. **Install required R packages** (run once in the R console):
   ```r
   install.packages(c("ggplot2", "dplyr", "tidyr", "knitr", "scales", "rmarkdown"))
   ```
3. **Use the dataset** `R Raw Data.csv` with the columns shown above, or edit the `read.csv()` path in `analysis.Rmd` to point to your file.
4. **Knit the report**: open `analysis.Rmd` in RStudio and click **Knit**, or run from the R console:
   ```r
   rmarkdown::render("analysis.Rmd")
   ```
   This produces `analysis.html` with all tables, plots, and statistical results.

## Analysis sections

1. Age at enrollment — distribution summary and bar chart
2. Sex — counts and bar chart
3. Weeks at euthanasia — summary, histogram by sex, and box plot
4. Terminal endpoint — counts, percentages, and bar chart
5. Cross-tabulations — terminal endpoint by sex; weeks at euthanasia by terminal endpoint
6. Statistical tests — Welch *t*-test and chi-squared test
## Dataset

This repository includes the dataset `R Raw Data.csv`.

### Files
- `R Raw Data.csv`

### Columns
- `Tiempo (sem)`: time in weeks
- `¿Llegó a término?`: term outcome indicator
- `Sexo`: sex category (`Macho` or `Hembra`)

### Notes
- CSV values in `Tiempo (sem)` use a decimal comma.
- The file appears to begin with an extra leading row `,,` before the header row.
- You may want to clean the file before analysis depending on the tools you use.
