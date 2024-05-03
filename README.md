# Messy Data and Machine Learning Project

## Team Members
- Zhenyu Li
- Jiayu Li
- Siyuan Lu

## Date
April 30, 2024

## Overview
This project uses R and various machine learning models to analyze and predict whether a person's annual income is above the average. It is based on the 2021-2023 data from the U.S. Census Bureau's Annual Social and Economic Supplement.

## Libraries Used
- `tidyverse`
- `VIM`
- `ranger`
- `tidymodels`
- `mlr`
- `mlbench`
- `randomForest`
- `ROCR`

## Data Collection
Data was collected from three annual datasets: 
- [`pppub21.csv`](https://www2.census.gov/programs-surveys/cps/datasets/2021/march/asecpub21csv.zip) for the year 2021.
- [`pppub22.csv`](https://www2.census.gov/programs-surveys/cps/datasets/2022/march/asecpub22csv.zip) for the year 2022.
- [`pppub23.csv`](https://www2.census.gov/programs-surveys/cps/datasets/2023/march/asecpub23csv.zip) for the year 2023.
These datasets include detailed records of demographic and economic characteristics.
Download and unzip, only save datasets listed here and delete all other files inside the zip file.


## Data Preprocessing
The datasets undergo preprocessing to select relevant variables and transform categorical variables into meaningful groups. Efforts are made to handle unusual values and missing data effectively.

## Exploratory Data Analysis
We conduct visual analysis to understand the distribution of the target variable and explore relationships between features. Techniques include bar plots and histograms of missing data.

## Model Selection and Training
We explore several models to classify individuals based on their income levels:
- Decision Trees
- Logistic Regression
- Random Forests
- Majority Vote
- Stacking

## Model Evaluation
Models are evaluated based on their accuracy, precision, and area under the ROC curve. These metrics help assess the effectiveness of each model.

## Combining Models
We employ advanced techniques like majority voting and stacking to combine predictions from different models, aiming to enhance prediction accuracy.

## Conclusions
Our findings highlight the effectiveness of different models and techniques in predicting income levels. We discuss insights into the features that significantly influence income levels.

## Appendix: Code
The R Markdown document includes all code used for data collection, preprocessing, model training, evaluation, and visualization, ensuring reproducibility and transparency.

## Variable Descriptions and Values

### A_AGE - Age of the individual.
- **Values**:
  - `00-79`: Age in years.
  - `80`: 80-84 years of age.
  - `85`: 85 years of age and over.

### PTOT_R - Total personal income recoded into brackets.
- **Values**:
  - `1`: UNDER $2,500
  - `2`: $2,500 TO $4,999
  - `3`: $5,000 TO $7,499
  - `4`: $7,500 TO $9,999
  - `5`: $10,000 TO $12,499
  - `6`: $12,500 TO $14,999
  - `7`: $15,000 TO $17,499
  - `8`: $17,500 TO $19,999
  - `9`: $20,000 TO $22,499
  - `10`: $22,500 TO $24,999
  - `11`: $25,000 TO $27,499
  - `12`: $27,500 TO $29,999
  - `13`: $30,000 TO $32,499
  - `14`: $32,500 TO $34,999
  - `15`: $35,000 TO $37,499
  - `16`: $37,500 TO $39,999
  - `17`: $40,000 TO $42,499
  - `18`: $42,500 TO $44,999
  - `19`: $45,000 TO $47,499
  - `20`: $47,500 TO $49,999
  - `21`: $50,000 TO $52,499
  - `22`: $52,500 TO $54,999
  - `23`: $55,000 TO $57,499
  - `24`: $57,500 TO $59,999
  - `25`: $60,000 TO $62,499
  - `26`: $62,500 TO $64,999
  - `27`: $65,000 TO $67,499
  - `28`: $67,500 TO $69,999
  - `29`: $70,000 TO $72,499
  - `30`: $72,500 TO $74,999
  - `31`: $75,000 TO $77,499
  - `32`: $77,500 TO $79,999
  - `33`: $80,000 TO $82,499
  - `34`: $82,500 TO $84,999
  - `35`: $85,000 TO $87,499
  - `36`: $87,500 TO $89,999
  - `37`: $90,000 TO $92,499
  - `38`: $92,500 TO $94,999
  - `39`: $95,000 TO $97,499
  - `40`: $97,500 TO $99,999
  - `41`: $100,000 AND OVER

### A_HGA - Highest grade attended or degree received.
- **Values**:
  - `0`: No schooling completed
  - `31`: Less than 1st grade
  - `32`: 1st, 2nd, 3rd, or 4th grade
  - `33`: 5th or 6th grade
  - `34`: 7th and 8th grade
  - `35`: 9th grade
  - `36`: 10th grade
  - `37`: 11th grade
  - `38`: 12th grade, no diploma
  - `39`: High school graduate - high school diploma or equivalent (includes equivalency)
  - `40`: Some college but no degree
  - `41`: Associate degree in college - occupational/vocational program
  - `42`: Associate degree in college - academic program
  - `43`: Bachelor's degree (for example: BA, AB, BS)
  - `44`: Master's degree (for example: MA, MS, MENG, MED, MSW, MBA)
  - `45`: Professional school degree (for example: MD, DDS, DVM, LLB, JD)
  - `46`: Doctorate degree (for example: PhD, EdD)

### A_CLSWKR - Class of worker.
- **Values**:
  - `1`: Government worker
  - `2`: Private not-for-profit wage and salary workers
  - `3`: Private for-profit wage and salary workers (employee of private company workers)
  - `4`: Self-employed in own not incorporated business workers
  - `5`: Self-employed in own incorporated business workers
  - `6`: Without pay

### A_MARITL - Marital status.
- **Values**:
  - `1`: Married, spouse present
  - `2`: Married, spouse absent
  - `3`: Widowed
  - `4`: Divorced
  - `5`: Separated
  - `6`: Never married/single

### A_MJOCC - Major occupation code.
- **Values**:
  - `001-099`: Specific codes for different occupations from Management to Military specific roles

### A_PFREL - Primary family relationship.
- **Values**:
  - `1`: Husband
  - `2`: Wife
  - `3`: Child
  - `4`: Other relatives
  - `5`: Non-relatives

### PRDTRACE - Race of the individual.
- **Values**:
  - `1`: White alone
  - `2`: Black or African American alone
  - `3`: American Indian alone
  - `4`: Alaska Native alone
  - `5`: American Indian and Alaska Native tribes specified; or American Indian or Alaska Native, not specified and no other races
  - `6`: Asian alone
  - `7`: Native Hawaiian and Other Pacific Islander alone
  - `8`: Some other race alone
  - `9`: Two or more races

### CAP_VAL - Capital gains.
- **Values**:
  - Numeric value indicating the amount of capital gains received.

### PEHRUSLT - Usual hours worked per week at all jobs.
- **Values**:
  - Numeric value indicating the usual hours worked per week.

### PENATVTY - Country of origin or nationality.
- **Values**:
  - Numerical codes corresponding to specific countries or areas:
    - `057`: United States
    - `060`: American Samoa
    - `066`: Guam
    - `069`: Northern Marianas
    - `073`: Puerto Rico
    - `078`: U.S. Virgin Islands
    - `100`: Albania
    - `102`: Austria
    - `103`: Belgium
    - `104`: Bulgaria
    - `105`: Czechoslovakia
    - `106`: Denmark
    - `108`: Finland
    - `109`: France
    - `110`: Germany
    - `116`: Greece
    - `117`: Hungary
    - `118`: Iceland
    - `119`: Ireland
    - `120`: Italy
    - `126`: Netherlands
    - `127`: Norway
    - `128`: Poland
    - `129`: Portugal
    - `130`: Azores
    - `132`: Romania
    - `134`: Spain
    - `136`: Sweden
    - `137`: Switzerland
    - `138`: United Kingdom
    - `139`: England
    - `140`: Scotland
    - `142`: Northern Ireland
    - `147`: Yugoslavia
    - `148`: Czech Republic
    - `149`: Slovakia
    - `150`: Bosnia & Herzegovina
    - `151`: Croatia
    - `152`: Macedonia
    - `154`: Serbia
    - `155`: Estonia
    - `156`: Latvia
    - `157`: Lithuania
    - `158`: Armenia
    - `159`: Azerbaijan
    - `160`: Belarus
    - `161`: Georgia
    - `162`: Moldova
    - `163`: Russia
    - `164`: Ukraine
    - `165`: USSR
    - `166`: Europe, not specified
    - `168`: Montenegro
    - `200`: Afghanistan
    - `202`: Bangladesh
    - `203`: Bhutan
    - `205`: Myanmar (Burma)
    - `206`: Cambodia
    - `207`: China
    - `209`: Hong Kong
    - `210`: India
    - `211`: Indonesia
    - `212`: Iran
    - `213`: Iraq
    - `214`: Israel
    - `215`: Japan
    - `216`: Jordan
    - `217`: Korea
    - `218`: Kazakhstan
    - `220`: South Korea
    - `222`: Kuwait
    - `223`: Laos
    - `224`: Lebanon
    - `226`: Malaysia
    - `228`: Mongolia
    - `229`: Nepal
    - `231`: Pakistan
    - `233`: Philippines
    - `235`: Saudi Arabia
    - `236`: Singapore
    - `238`: Sri Lanka
    - `239`: Syria
    - `240`: Taiwan
    - `242`: Thailand
    - `243`: Turkey
    - `245`: United Arab Emirates
    - `246`: Uzbekistan
    - `247`: Vietnam
    - `248`: Yemen
    - `249`: Asia, not specified
    - `300`: Bermuda
    - `301`: Canada
    - `303`: Mexico
    - `310`: Belize
    - `311`: Costa Rica
    - `312`: El Salvador
    - `313`: Guatemala
    - `314`: Honduras
    - `315`: Nicaragua
    - `316`: Panama
    - `321`: Antigua and Barbuda
    - `323`: Bahamas
    - `324`: Barbados
    - `327`: Cuba
    - `328`: Dominica
    - `329`: Dominican Republic
    - `330`: Grenada
    - `332`: Haiti
    - `333`: Jamaica
    - `338`: St. Kitts--Nevis
    - `339`: St. Lucia
    - `340`: St. Vincent and the Grenadines
    - `341`: Trinidad and Tobago
    - `343`: West Indies, not specified
    - `360`: Argentina
    - `361`: Bolivia
    - `362`: Brazil
    - `363`: Chile
    - `364`: Columbia
    - `365`: Ecuador
    - `368`: Guyana
    - `369`: Paraguay
    - `370`: Peru
    - `372`: Uruguay
    - `373`: Venezuela
    - `374`: South America, not specified
    - `399`: Americas, not specified
    - `400`: Algeria
    - `407`: Cameroon
    - `408`: Cape Verde
    - `412`: Congo
    - `414`: Egypt
    - `416`: Ethiopia
    - `417`: Eritrea
    - `421`: Ghana
    - `423`: Guinea
    - `425`: Ivory Coast
    - `427`: Kenya
    - `429`: Liberia
    - `430`: Libya
    - `436`: Morocco
    - `440`: Nigeria
    - `444`: Senegal
    - `447`: Sierra Leone
    - `448`: Somalia
    - `449`: South Africa
    - `451`: Sudan
    - `453`: Tanzania
    - `454`: Togo
    - `457`: Uganda
    - `459`: Zaire
    - `460`: Zambia
    - `461`: Zimbabwe
    - `462`: Africa, not specified
    - `501`: Australia
    - `508`: Fiji
    - `511`: Marshall Islands
    - `512`: Micronesia
    - `515`: New Zealand
    - `523`: Tonga
    - `527`: Samoa
    - `555`: Elsewhere

### A_SEX - Sex of the individual.
- **Values**:
  - `1`: Male
  - `2`: Female
