# Project Overview

This project is part of the FIN 550: Big Data course and focuses on property assessment for the Cook County Assessor's Office (CCAO). The goal is to enhance the accuracy and transparency of property valuations across over 130 municipalities, including the City of Chicago, using data science techniques.

## Team Members
- Shammy Ho
- Hyun Ji Lee
- Ruilin Ni
- Vishwas Rao
- Zhijie Jin
- Akshaya Suresh
- Purva Vaswani
- Manvi Nagpal

## Case Overview

The project utilizes three key datasets:
- `predict_property_data.csv`: Contains 10,000 properties to be assessed.
- `historic_property_data.csv`: Includes information on 50,000 recently sold properties.
- `codebook.csv`: Details the variables used in the analysis.

The primary objective is to predict property values in `predict_property_data.csv` using historical data and various predictive modeling techniques. The datasets are sourced from the [CCAO Res AVM GitLab repository](https://gitlab.com/ccao-data-science---modeling/models/ccao_res_avm).

## Methodology

### Preprocessing
- Dropped variables with over 50% missing data.
- Removed non-predictor variables based on the codebook.
- Cleaned and standardized the data, including the removal of negative housing prices and winsorizing to handle outliers.
- Replaced missing values with appropriate substitutes: mode for categorical variables and mean for numerical variables.

### Predictor Selection
- Addressed multicollinearity by examining variable correlations and excluding highly correlated variables.
- Employed Lasso Regression for efficient predictor selection due to the high dimensionality of the dataset.

### Model Fitting
- **Linear Regression**: Initial model yielded an MSE of 11,423,649,406.
- **Regression Tree**: Produced an MSE of 15,503,818,679, which was reduced to 12,504,983,754 after pruning.
- **Random Forest**: Achieved the lowest MSE of 8,716,355,447, making it the selected model for predictions.

## Results
The Random Forest model was used to generate the final property assessments, resulting in a diverse distribution of assessed values. The summary statistics of the assessed values are as follows:
- **Min**: $18,320
- **Max**: $1,524,386
- **Median**: $250,671
- **Mean**: $315,411
- **1st Quartile**: $154,312
- **3rd Quartile**: $379,366

## Files

### Main Files
- `Group final.Rmd`: R script for the group analysis.
- `Personal dabbing.Rmd`: R script with adjusted attributes as categorical values.
- `Executive Summary.pdf`: Detailed overview and methodology of the project.
- `Presentation Slides.pdf`: Slides summarizing the project process and results.

### Data Files
- `predict_property_data.csv`
- `historic_property_data.csv`
- `codebook.csv`

## Notable Findings
- The adjustment of attributes to categorical values in `Personal dabbing.Rmd` resulted in a higher MSE (8,748,573,417) compared to the group analysis in `Group final.Rmd` (8,716,355,447), despite the improved handling of categorical variables.

## Conclusion
The project successfully leveraged data science techniques to improve property valuation processes, providing a more transparent and reliable system for Cook County. The use of Random Forest models proved to be the most effective in minimizing prediction error.

For more details, refer to the attached R scripts and the executive summary document.