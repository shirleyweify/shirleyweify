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
### Parallel
- **Library: `foreach` | `doParallel`**
```
cl <- makeCluster(core)
registerDoParallel(cl)

res = foreach(..., .combine = "rbind", .packages = c("dplyr", "matlib"), .errorhandling = "stop") %dopar% {
    ...
    return()
}

stopCluster(cl)
```

- **Library: `foreach` | `doSNOW`**
```
cl <- makeCluster(core)
registerDoSNOW(cl)

iterations <- length(seq(start, end, update))
pb <- txtProgressBar(max = iterations, style = 3)
progress <- function(n) setTxtProgressBar(pb, n)
opts <- list(progress = progress)

res = foreach(..., .combine = "cbind", .options.snow = opts, .errorhandling = "remove") %dopar% {
    ...
    return()
}

stopCluster(cl)
```

### System
- **Library: `tictoc`**
```
tic("Task")
...
toc()
```

### File handling
| Function | Details |
| ---- | ---- |
| `file.exists()` |
| `file.create()` |
| `file.path()` |
| `dir.exists()` |
| `dir.create()` |

### Error handling

https://cran.r-project.org/web/packages/tryCatchLog/vignettes/tryCatchLog-intro.html



## Data Type
### Strings and characters
| Function | Details |
| ---- | ---- |
| `gsub` | `gsub(".RData", ".csv", "xxx.RData")` |
| `grepl` | contain or not: `grepl(".RData", "xxx.RData", fixed = TRUE)` |
| `nchar` | number of characters in a string: `nchar("apple")` = 5 |
| `substr` | `substr("apple", 3, 5)` = "ple" |

### Date and time
| Function | Details |
| ---- | ---- |
| `strptime` | converts characters to time objects |
| `strftime` | converts time objects to characters |
| `lubridate::ymd` | `ymd("20100101")` = "2010-01-01" |



## Data Structure
### Read / Write data
| Data type | Library::function |
| ---- | ---- |
| ".RData" | `load` / `save` |
| ".csv" | `read.csv` / `write.csv` |
| ".sas7bdat" | `haven::read_sas` |

### Data wrangling
- **Library: `dplyr` | `tidyr`**

https://www.rstudio.com/wp-content/uploads/2015/02/data-wrangling-cheatsheet.pdf

| Function | Example |
| ---- | ---- |
| mutate | `mutate(var1 = var2 + var3)` |
| mutate_at | `mutate_at(c('var1', 'var2'), fn)` |
| mutate_if | `mutate_if(is.character, as.numeric)` |
| filter | `filter(date >= "2010-01-01")` |
| group_by | `group_by(year) %>% summarize(across(all_of(colnames(data)), ~ sum(.x, na.rm = TRUE)))`<br />`group_by(xxx) %>% summarize(yyy = list(unique(yyy)))` |
| ungroup | removes grouping ... |

- **Library: `maditr`**
Convert data between wide and long forms.

| Function | Example |
| ---- | ---- |
| melt | wide form to long form ... |
| dcast | `df %>% dcast(LHS ~ RHS, value.var = "y", fun.aggregate = sum, na.rm = TRUE)` |

### Data formatting
- **Library: `Hmisc`**

| Function | Example |
| ---- | ---- |
| label |


## Model
### GARCH
- **Library: `rugarch`**



## Chart
### Plot
- **Library: `ggplot2`**

https://homepages.gac.edu/~anienow2/MCS_142/R/ggplot2-basics.html



## R Markdown

[cheat sheet](https://www.rstudio.com/wp-content/uploads/2015/02/rmarkdown-cheatsheet.pdf)

