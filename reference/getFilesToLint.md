# getFilesToLint

Get the R files the current git user is responsible for to pass them to
the auto-formatter and/or linter.

## Usage

``` r
getFilesToLint(pathToGitRepo = ".")
```

## Arguments

- pathToGitRepo:

  path to a git repository

## Details

The files of interest are identified using git via system() (and shell()
for windows). All currently untracked files and changed files (both
staged and unstaged) are collected, as well as files that were changed
in non-merge commits authored by the current git user since the last
version commit (a commit where .buildLibrary was changed, presumably to
increase the version number). Of those the absolute paths to .R, .Rmd
and .Rnw files are returned as a character vector.

## See also

[`lint`](lint.md), [`autoFormat`](autoFormat.md)

## Author

Pascal Sauer

## Examples

``` r
lucode2:::getFilesToLint()
#> Warning: running command 'git config user.email' had status 1 and error message 'Function not implemented'
#>  [1] "/__w/lucode2/lucode2/R/SystemCommandAvailable.R"                         
#>  [2] "/__w/lucode2/lucode2/R/addEOF.R"                                         
#>  [3] "/__w/lucode2/lucode2/R/addGitHubActions.R"                               
#>  [4] "/__w/lucode2/lucode2/R/autoFormat.R"                                     
#>  [5] "/__w/lucode2/lucode2/R/buildLibrary.R"                                   
#>  [6] "/__w/lucode2/lucode2/R/check.R"                                          
#>  [7] "/__w/lucode2/lucode2/R/checkRepoUpToDate.R"                              
#>  [8] "/__w/lucode2/lucode2/R/checkRequiredPackages.R"                          
#>  [9] "/__w/lucode2/lucode2/R/check_versions.R"                                 
#> [10] "/__w/lucode2/lucode2/R/citationDoi.R"                                    
#> [11] "/__w/lucode2/lucode2/R/conditionalCopy.R"                                
#> [12] "/__w/lucode2/lucode2/R/eprint.R"                                         
#> [13] "/__w/lucode2/lucode2/R/eprint_list.R"                                    
#> [14] "/__w/lucode2/lucode2/R/escapeRegex.R"                                    
#> [15] "/__w/lucode2/lucode2/R/extract_arguments.R"                              
#> [16] "/__w/lucode2/lucode2/R/findCoupledruns.R"                                
#> [17] "/__w/lucode2/lucode2/R/findDeps.R"                                       
#> [18] "/__w/lucode2/lucode2/R/findDuplicates.R"                                 
#> [19] "/__w/lucode2/lucode2/R/findIterations.R"                                 
#> [20] "/__w/lucode2/lucode2/R/fixBuildLibraryMergeConflict.R"                   
#> [21] "/__w/lucode2/lucode2/R/fixfile.R"                                        
#> [22] "/__w/lucode2/lucode2/R/functionHeaderDefaults.R"                         
#> [23] "/__w/lucode2/lucode2/R/getClusterLoad.R"                                 
#> [24] "/__w/lucode2/lucode2/R/getFilesToLint.R"                                 
#> [25] "/__w/lucode2/lucode2/R/getLine.R"                                        
#> [26] "/__w/lucode2/lucode2/R/getPackageAuthors.R"                              
#> [27] "/__w/lucode2/lucode2/R/getScenNames.R"                                   
#> [28] "/__w/lucode2/lucode2/R/gitAuthors.R"                                     
#> [29] "/__w/lucode2/lucode2/R/incrementVersion.R"                               
#> [30] "/__w/lucode2/lucode2/R/isVersionUpdated.R"                               
#> [31] "/__w/lucode2/lucode2/R/lint.R"                                           
#> [32] "/__w/lucode2/lucode2/R/lintrRules.R"                                     
#> [33] "/__w/lucode2/lucode2/R/loadBuildLibraryConfig.R"                         
#> [34] "/__w/lucode2/lucode2/R/lucode2-package.R"                                
#> [35] "/__w/lucode2/lucode2/R/manipulateConfig.R"                               
#> [36] "/__w/lucode2/lucode2/R/manipulateFile.R"                                 
#> [37] "/__w/lucode2/lucode2/R/memCheck.R"                                       
#> [38] "/__w/lucode2/lucode2/R/mergestatistics.R"                                
#> [39] "/__w/lucode2/lucode2/R/modifyRproj.R"                                    
#> [40] "/__w/lucode2/lucode2/R/package2readme.R"                                 
#> [41] "/__w/lucode2/lucode2/R/packageInfo.R"                                    
#> [42] "/__w/lucode2/lucode2/R/path.R"                                           
#> [43] "/__w/lucode2/lucode2/R/piamPackages.R"                                   
#> [44] "/__w/lucode2/lucode2/R/produce_missing_reports.R"                        
#> [45] "/__w/lucode2/lucode2/R/readArgs.R"                                       
#> [46] "/__w/lucode2/lucode2/R/readRuntime.R"                                    
#> [47] "/__w/lucode2/lucode2/R/removeEOF.R"                                      
#> [48] "/__w/lucode2/lucode2/R/rename_scenario.R"                                
#> [49] "/__w/lucode2/lucode2/R/rmAllbut.R"                                       
#> [50] "/__w/lucode2/lucode2/R/runstatistics.R"                                  
#> [51] "/__w/lucode2/lucode2/R/sendmail.R"                                       
#> [52] "/__w/lucode2/lucode2/R/setup_info.R"                                     
#> [53] "/__w/lucode2/lucode2/R/setwd2.R"                                         
#> [54] "/__w/lucode2/lucode2/R/snakeToCamel.R"                                   
#> [55] "/__w/lucode2/lucode2/R/testPackage.R"                                    
#> [56] "/__w/lucode2/lucode2/R/updateRepo.R"                                     
#> [57] "/__w/lucode2/lucode2/R/validationkey.R"                                  
#> [58] "/__w/lucode2/lucode2/R/validkey.R"                                       
#> [59] "/__w/lucode2/lucode2/R/variableLinks.R"                                  
#> [60] "/__w/lucode2/lucode2/tests/testthat.R"                                   
#> [61] "/__w/lucode2/lucode2/tests/testthat/test-checkRequiredPackages.R"        
#> [62] "/__w/lucode2/lucode2/tests/testthat/test-conditionalCopy.R"              
#> [63] "/__w/lucode2/lucode2/tests/testthat/test-eprint.R"                       
#> [64] "/__w/lucode2/lucode2/tests/testthat/test-findCoupledruns.R"              
#> [65] "/__w/lucode2/lucode2/tests/testthat/test-findIterations.R"               
#> [66] "/__w/lucode2/lucode2/tests/testthat/test-fixBuildLibraryMergeConflict.R" 
#> [67] "/__w/lucode2/lucode2/tests/testthat/test-getScenNames.R"                 
#> [68] "/__w/lucode2/lucode2/tests/testthat/test-manipulateConfig.R"             
#> [69] "/__w/lucode2/lucode2/tests/testthat/test-manipulateFile.R"               
#> [70] "/__w/lucode2/lucode2/tests/testthat/test-package2readme.R"               
#> [71] "/__w/lucode2/lucode2/tests/testthat/test-readArgs.R"                     
#> [72] "/__w/lucode2/lucode2/tests/testthat/test-snakeToCamel.R"                 
#> [73] "/__w/lucode2/lucode2/tests/testthat/test-theOneAndOnlyTandFsymbolFixer.R"
#> [74] "/__w/lucode2/lucode2/tests/testthat/test-updateRepo.R"                   
```
