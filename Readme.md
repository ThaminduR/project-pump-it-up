# Pump it Up: Data Mining the Water Table
# Git repo: [ThaminduR/project-pump-it-up (github.com)](https://github.com/ThaminduR/project-pump-it-up)

## EDA and Preprocessing

### Missing Values Exploration

- Funder, installer, subvillage, public_meeting, scheme_management, scheme_name, permit columns have missing values.
- Scheme_name has significantly large number of missing values.

### Columns with Similar Data

- Dataset contains several columns with similar data. 
- During the preprocessing these columns were explored in-depth and one from each similar group was selected for the final dataset.

- scheme_management and management have almost same data except scheme_management has around 3000 missing values. Futher, the management_group is a grouped version of the management column. management column was kept since it carries more details.

- source and source_type contains almost same information. Also source_type is a grouped verison of source. Since source has more detailed data, we will be keeping that column.

- Since extraction_type, extraction_type_group columns have similar info and the extraction_type_class has grouped info, only the extraction type group will be kept. Even though extraction class has more detailed data most value counts are small.

- Since the quantity, quantity_group columns have exact same info quantity column will be kept.

- Since water_quality, quality_group have almost exact same info and water_quality column has it more detailed we will keep water_quality column.

- Since the waterpoint_type, waterpoint_type_group columns have exact same info quantity column will be kept.

- Since the payment, payment_type columns have exact same info quantity column will be kept.
### Unrelated columns

- Several unrelated columns were also dropped since they don't provide any information towards functionality of the pumps. 
- These columns include 'date_recorded', 'wpt_name', 'recorded_by', 'scheme_name','region_code', 'num_private'.

### New features

- 'decade' features was added to the dataset using the construction year.
- Before converting construction year to decade, 0 values in that column were replaced by median value (2000).

### Other dropped columns

- amount_tsh column was dropped since it didn't provide any useful information.
- subvillage column was dropped since there we already had region column to represent thhe geolocation information. Also it had high-cardinality which made it difficult to encode.

### Handling Missing Values of rest of the columns

- population, public_meeting, permit, intaller, funder columns had missing values which were then replaced by means and modes.

### Geo-coordinates

- longitudes and latitudes were plotted and outliers were detected in the longitude column.
- There were 0 values in longitude columns. This had to be a data input error.
- These 0 values were replaced by the mean.

## Categorical Encoding

- One-hot encoding was not used since it increases the number of columns.
- Label encoding was employed on the dataset.

## Numerical data rescaling

- Numerical data were standardized

## Final Rank


## Proof of Submission