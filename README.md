# Qualitative-data-analysis
This repository contains an R script for performing descriptive statistical analysis on a dataset named WHEAT, which includes agro-morphological traits of wheat genotypes. The analysis covers the frequency and percentage of qualitative data using the summarytools package.

# Load the summarytools package for summarizing data
library(summarytools)

# Generate a frequency table for the 'growth habit' variable
# This will show how many observations fall under each category (e.g., erect, semi-erect, prostrate)
freq(WHEAT$`growth habit`)

# Generate a frequency table for the 'awnedness' variable
# The option report.nas = FALSE removes the count of missing (NA) values from the table
freq(WHEAT$awnedness,
     report.nas = FALSE)

# Generate a frequency table for the 'leaf color' variable
# Several options are used here to simplify the output:
# - report.nas = FALSE: exclude NA values
# - totals = FALSE: remove the total count row
# - cumul = FALSE: remove cumulative percentages
# - headings = FALSE: suppress the heading/title of the output
freq(WHEAT$`leaf color`,
     report.nas = FALSE,
     totals = FALSE,
     cumul = FALSE,
     headings = FALSE)

# Generate descriptive statistics for the 'Anther color' variable
# This command provides basic statistics such as mean, median, mode (as appropriate for the data type)
# - headings = FALSE: removes the default heading from the output
# - stats = "common": displays only commonly used statistics (e.g., mean, min, max, standard deviation)
descr(WHEAT$`Anther color`,
      headings = FALSE,
      stats = "common")

###Results
 library(readxl)
> WHEAT <- read_excel("D:/khem data analysis/WHEAT.xlsx", 
+     sheet = "Qualitative")
> View(WHEAT)
> library(summarytools)
Warning message:
package ‘summarytools’ was built under R version 4.3.3 
> freq(WHEAT$`growth habit`)
Frequencies  
WHEAT$`growth habit`  
Type: Numeric  

              Freq   % Valid   % Valid Cum.   % Total   % Total Cum.
----------- ------ --------- -------------- --------- --------------
          3     20     17.24          17.24     17.24          17.24
          5     26     22.41          39.66     22.41          39.66
          7     70     60.34         100.00     60.34         100.00
       <NA>      0                               0.00         100.00
      Total    116    100.00         100.00    100.00         100.00
> freq(WHEAT$awnedness,
+      report.nas = FALSE # remove NA information
+ )
Frequencies  
WHEAT$awnedness  
Type: Numeric  

              Freq        %   % Cum.
----------- ------ -------- --------
          0     29    25.00    25.00
          3     19    16.38    41.38
          7     68    58.62   100.00
      Total    116   100.00   100.00
> freq(WHEAT$`leaf color`,
+      report.nas = FALSE, # remove NA information
+      totals = FALSE, # remove totals
+      cumul = FALSE, # remove cumuls
+      headings = FALSE # remove headings
+ )

           Freq       %
-------- ------ -------
       3     34   29.31
       5     62   53.45
       7     20   17.24
> descr(WHEAT$`Anther color`,
