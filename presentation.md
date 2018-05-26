Simple and Reliable R Package Documentation with Sinew
========================================================
author: Jonathan Sidi
date: 2018-05-25
autosize: true

Whoami
========================================================

Jonathan Sidi - [Metrum Research Group](http://metrumrg.com/)

- Research Scientist at Metrum Research Group
  - Biomedical Modeling and Simulation
- Stats Phd Student at the Hebrew University in Jerusalem

R Packages
========================================================

- **What**: Bundled script to reproduce analysis
  - Code
  - Data
  - Documentation
  - Tests
- **Why**: Promotes collaboration across researchers
- **Added Value**: Consistent help documentation format

Structure
========================================================

- **DESCRIPTION** : Package Metadata
- **NAMESPACE** : Manages how the packages interacts with other packages
- **R/** : script
- **man/** : documentation (Rd files)
- **data/** : data
- **tests/** : unit tests

Roxygen2
========================================================

[Roxygen2](https://github.com/klutometis/roxygen) is a R package that creates an easy api to maintain the documentation for each function and the package namespace. 

- You do not have to manually write the Rd files that are needed to populate the man subdirectory.
  - The documentation is in the same place as the object that it is describing.
- You do not have to manually maintain the NAMESPACE file.
  - Namespacing for the object is part of the documentation.
  
High Bars
========================================================

This is great, but is still a pretty high bar to pass for a non-expert developers.

- You have to understand and track what are the `depends`, `imports` and `suggests` of the package.
  - `@import` and  `@importFrom`
- You have to keep a consistent documentation layout across functions.
  - `@params`, `@examples`
- You have to manage links across packages
  - `@seealso`
  
Juggling Act
========================================================

For more seasoned package developers this also can be an arduous task.

- Every change to the script
  - e.g. using another package, add a formal argument

- You need to update the `Roxygen2` documentation
  - update `@params`, `@imports`, `@importFrom`

Sinew
========================================================

- Sinew is a package that progrmatically populates roxygen2 fields with inoformation found within the function you are documenting. 

- Allowing the developer to focus on the development and not on the continuous managment of the namespacing and mundane manual documentation tasks.

CRAN: https://cran.r-project.org/web/packages/sinew/index.html

Github Repository: https://www.github.com/metrumresearchgroup/sinew

Gitbook: https://metrumresearchgroup.github.io/sinew/

```r
# CRAN
install.packages('sinew')

# Github
remotes::install_github('www.github.com/metrumresearchgroup/sinew')
```

Package Goal
========================================================

The goal of `{sinew}` is to 
- automate nearly all of the manual tasks needed to document functions
- properly set up the import fields for oxygenation
- make it easier to attain documentation consistency across functions and packages.
- change and append updated parameters, definitions, namespacing to existing documentation

Sinew Workflow Example
========================================================

In the following example we will create a fully functional package with valid namespacing and documentation that passes `R CMD check --as-cran` using `{sinew}` in 10 minutes. 

Time permitting we will see the interactive shiny gadget of `{sinew}`

Moving to Rmd.... 

```r
rstudioapi::navigateToFile('sinew_example.Rmd') 
```