# jDepacWrappeR
Wrapper function to run jDepac from CSV input. 
 - See DemoInput.csv for definition of input CSV structure. Column "ID" can be used to identify simulations (e.g. a location name and/or timestamp). It is the only column that is not provided to jDepac as input.
 - See InputMapping.csv for information how CSV column names map to jDepac parameter names.
 - See DemoBatchOutput.csv for an example of batch results.
 
 ## How to use
  - Download all files from this repository (click on "Code" (green button, top right) -> Download ZIP above).
  - Create a working directory and a subfolder "Input".
  - Copy the files "jDepacWrappeR.R", "HelpingFunctions.R" and "JDepac-0.2.1.jar" (not included in this repository) into the working directory.
  - Copy the files "DemoInput.csv" and "InputMapping.csv" into the "Input" folder.
  - Open the file "jDepacWrappeR.R" and adjust the variable "WorkDir" to match the path of the working directory.
  - Execute the "jDepacWrappeR.R" to run all lines in the "DemoInput.csv" one by one through jDepac. The results will be saved in a subfolder named "Output" in the working directory. R libraries "tidyverse" and "stringr" must be installed.
  - Change the content "DemoInput.csv" to run different scenarios with jDepac.

Currently only tested for MS Windows.

## Update history
 - Update 2021-06-28
    - Fixed inconsistency in output table structure if substances with less output columns (e.g. particles) are simulated before substances with more output column (e.g. NH3)
    - UNDEF in jDepac results is now saved as NA
 - Update 2021-06-27
   - Added update history in readme file 
 - Update 2021-06-05
   - Renamed CSV input column "BackgroundCmp" to "CmpConcentration" to emphasize that this column refers to the *current* concentration of the substance specified in column "cmp" and not to average background concentrations like columns "BackgroundNH3" and "BackgroundSO2"
   - Corrected command line parameter for latitude (it is "l" not "d")
   - Added handling of unexpected output format
 - Update 2021-04-16
   - Improved description in readme file
 - Update 2021-03-26
   - Initial commit
