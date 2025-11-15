# The Significance of 37 °C: Temperature, Ethnicity, and the Limits of Normality
BIS 560 Final Project Analysis


## Data Cleaning (Excel) ##
The original raw dataset used for this project is available in the repository as [ICI_groups1and2.csv](ICI_groups1and2.csv)

Before importing the dataset into R, an initial round of cleaning was performed in Excel to simplify the raw file and retain only the variables required for analysis. I filtered the dataset to keep the essential demographic fields `SubjectID`, `Gender`, `Age`, and `Ethnicity` along with the four repeated measurement rounds for each validated facial temperature region (`canthiMax1–4` and `T_Max1–4`). Using these columns, I then calculated two averaged temperature variables for each participant: `T_CEmax_mean`, derived from the four canthus measurements, and `T_max_mean`, derived from the four full-face maximum measurements. Computing these averages reduces random noise across rounds and provides a more stable, reliable temperature estimate. The resulting cleaned dataset was saved as [data_pre_processed.csv](data_pre_processed.csv), which serves as the input for all subsequent preprocessing and analysis conducted in R.


## Data Pre-Processing ##
This stage imports the cleaned dataset, assesses completeness, and isolates the subset of variables used in the analysis. The dataset `data_pre_processed.csv` contains all temperature measurements recorded across four rounds, along with corresponding demographic fields. To quantify data quality, missing values are evaluated for each round and measurement type `canthiMax` and `T_Max` before mean values are computed. The resulting table expresses missingness both as raw counts and as percentages relative to the total sample size, providing a transparent account of where attrition or sensor loss may have occurred.

![tablec2](tablec2.png)

After verifying completeness, the dataset is restricted to the analytic subset: `T_CEmax_mean`, `T_max_mean`, `Gender`, `Age`, and `Ethnicity`. The focus on these columns aligns with validated variables and ensures that subsequent computations are limited to fields directly relevant to the analytic question. Age is filtered to retain participants between 18 and 30 years, mirroring the study’s dominant demographic composition and minimizing variability attributable to thermoregulatory differences outside this range. The previewed output confirms that the filtered dataset contains only the intended records and variables.

![preview](preview.png)

## Data Pre-Analysis Summary Statistics ##
Following the construction of the analytic subset, a second completeness assessment confirms the absence of residual missingness in the primary analysis variables. This step ensures that the averaged thermal values `T_CEmax_mean` and `T_max_mean` are not compromised by incomplete data from earlier rounds. The summary table provides a compact audit trail of data integrity after aggregation.

![tablec3](tablec3.png)

To contextualize the sample composition, the distribution of ethnicity is then summarized as both counts and percentages. This table reflects the categorical encoding used in the source dataset—derived from administrative reporting rather than biological classification—and provides an overview of representation across groups. Because several categories are sparsely populated, these descriptive statistics are primarily interpretive rather than inferential, clarifying the dataset’s internal structure and highlighting the limitations of subgroup analysis.

![tablec1](tablec1.png)
