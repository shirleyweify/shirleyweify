# R Packages and Packed Functions
http://www.cookbook-r.com/

## Shortcut

### Rstudio
| Action | Keys |
| ---- | ---- |
| run | `command` + `enter` |
| comment | `shift` + `command` + `C` |
| uncomment | `shift` + `command` + `C` |

### VS code
| Action | Keys |
| ---- | ---- |
| run | `command` + `enter` |
| comment | `Command` + `K`, `Command` + `C` |
| uncomment | `Command` + `K`, `Command` + `U` |
| format | `shift` + `option` + `F` |

## Basic

### Parallel: `foreach`, `doParallel`, `doSNOW`

```
    library(foreach)
    library(doParallel)

    cl <- makeCluster(core)
    registerDoParallel(cl)

    res = foreach(..., .combine = 'rbind') %dopar% {
        return()
    }

    stopCluster(cl)
```

```
    library(foreach)
    library(doSNOW)

    cl <- makeCluster(core)
    registerDoSNOW(cl)

    iterations <- length(seq(start, end, update))
    pb <- txtProgressBar(max = iterations, style = 3)
    progress <- function(n) setTxtProgressBar(pb, n)
    opts <- list(progress = progress)

    res = foreach(..., .combine = 'rbind', .options.snow = opts, .errorhandling="remove") %dopar% {
        return()
    }

    stopCluster(cl)
```

### System

| Library | Description |
| - | - |
| tictoc | `tic("Task")`, `toc()` |

### Error handling
https://cran.r-project.org/web/packages/tryCatchLog/vignettes/tryCatchLog-intro.html


## Data Structure

### Read / Write data

| Data type | Library::function |
| ---- | ---- |
| ".RData" | `load` / `save` |
| ".csv" | `read.csv` / `write.csv` |
| ".sas7bdat" | `haven::read_sas` |

### Data formatting

- **Library: `dplyr` | `tidyr`**
https://www.rstudio.com/wp-content/uploads/2015/02/data-wrangling-cheatsheet.pdf

| Function | Example |
| ---- | ---- |
| mutate | `mutate(var1 = var2 + var3)` |
| filter | `filter(date >= "2010-01-01")` |
| group_by | `group_by(year) %>% summarise(across(all_of(colnames(data)), ~ sum(.x, na.rm = TRUE)))` |
| ungroup | removes grouping ... |

- **Library: `maditr`**
Convert data between wide and long forms.

| Function | Example |
| ---- | ---- |
| melt | wide form to long form ... |
| dcast | long form to wide form ... |


## Model

### GARCH

- **Library: `rugarch`**
