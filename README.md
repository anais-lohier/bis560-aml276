# bis560-aml276
BIS 560 Final Project Analysis

## Data Pre-Processing ##
This stage imports the cleaned dataset, assesses completeness, and isolates the subset of variables used in the analysis. The dataset `data_pre_processed.csv` contains all temperature measurements recorded across four rounds, along with corresponding demographic fields. To quantify data quality, missing values are evaluated for each round and measurement type `canthiMax` and `T_Max` before mean values are computed. The resulting table expresses missingness both as raw counts and as percentages relative to the total sample size, providing a transparent account of where attrition or sensor loss may have occurred.

After verifying completeness, the dataset is restricted to the analytic subset: `T_CEmax_mean`, `T_max_mean`, `Gender`, `Age`, and `Ethnicity`. The focus on these columns aligns with validated variables and ensures that subsequent computations are limited to fields directly relevant to the analytic question. Age is filtered to retain participants between 18 and 30 years, mirroring the study’s dominant demographic composition and minimizing variability attributable to thermoregulatory differences outside this range. The previewed output confirms that the filtered dataset contains only the intended records and variables.

## Data Pre-Analysis Summary Statistics ##
Following the construction of the analytic subset, a second completeness assessment confirms the absence of residual missingness in the primary analysis variables. This step ensures that the averaged thermal values `T_CEmax_mea` and `T_max_mean` are not compromised by incomplete data from earlier rounds. The summary table provides a compact audit trail of data integrity after aggregation.

To contextualize the sample composition, the distribution of ethnicity is then summarized as both counts and percentages. This table reflects the categorical encoding used in the source dataset—derived from administrative reporting rather than biological classification—and provides an overview of representation across groups. Because several categories are sparsely populated, these descriptive statistics are primarily interpretive rather than inferential, clarifying the dataset’s internal structure and highlighting the limitations of subgroup analysis.
