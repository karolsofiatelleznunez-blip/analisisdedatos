# analysisdedatos

R analysis of research variables collected from animal subjects in tumor-growth studies.

## Variables

| Variable | Description |
|---|---|
| `sex` | Biological sex of the animal (`Male` / `Female`) |
| `weeks_at_euthanasia` | Age in weeks when the animal was euthanized |
| `reached_terminal` | Whether the animal reached the terminal endpoint due to tumor growth (`Yes` / `No`) |

## Files

```
analysis.Rmd   # Main R Markdown analysis (open in RStudio and knit)
R Raw Data.csv # Source dataset used by the report
```

## Usage

1. **Install R and RStudio** if you have not already.
2. **Install required R packages** (run once in the R console):
   ```r
   install.packages(c("ggplot2", "dplyr", "knitr", "scales", "rmarkdown", "survival"))
   ```
3. **Keep your data** in `R Raw Data.csv` with these source columns:
   - `Tiempo (sem)`
   - `¿Llegó a término?`
   - `Sexo`
4. **Knit the report**: open `analysis.Rmd` in RStudio and click **Knit**, or run from the R console:
   ```r
   rmarkdown::render("analysis.Rmd")
   ```
   This produces `analysis.html` with tables, plots, and statistical results.

## Analysis sections

2. Sex — counts and bar chart
3. Weeks at euthanasia — summary, histogram by sex, and box plot
4. Terminal endpoint — counts, percentages, and bar chart
5. Cross-tabulations — terminal endpoint by sex; weeks at euthanasia by terminal endpoint
6. Statistical tests — Welch *t*-test and chi-squared test
7. Survival analysis — Kaplan-Meier curves by sex and log-rank test (time-to-terminal-endpoint)

## Dataset

This repository uses the dataset `R Raw Data.csv`.

### Source columns
- `Tiempo (sem)`: Weeks at euthanasia
- `¿Llegó a término?`: Terminal outcome indicator (`1` = yes, `0` = no)
- `Sexo`: Sex category (`Macho` or `Hembra`)

### Cleaning performed in the analysis
- Skips the extra leading row `,,`
- Converts decimal commas in `Tiempo (sem)` to numeric values
- Recodes `¿Llegó a término?` from `1/0` to `Yes/No`
- Recodes `Sexo` from `Macho/Hembra` to `Male/Female`

### Scope
This repository analyzes only these three variables:
- Sex
- Weeks at euthanasia
- Reached terminal
