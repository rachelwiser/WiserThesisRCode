# FloricultureWTP


### This is designed to take the raw survey data from Qualtrics and convert it to a useable format for the support.CEs package. It then runs the package and saves the results (including bar graphs).

#### To make the decisions that will be available to the respondent, run the Support.CEs package. I run it again in 3. Secondary Data Processing below again. 

### For each R Markdown, there is an initial line data_date = "April14". Change this to the MonthDate. For example, April5. This should match the Qualtrics Data. The R markdowns are saved in the R markdown folder.

## Order of R Markdowns
###     1. Creating Directories
####          This creates the directories structure. It only needs to be run the first time you do an analysis.
####          Save the DataApril28.xls in the Data|QualtricsDownloads file once it is created.
###     2. Initial Data Processing
####          This takes the responses to the survey and turns it into a more numerical data set. For example, if they choose neither bouquet, it is now a 3 instead of "Neither". It also adjusts the responses to the environmental and social views so that a 7 is pro environment/society and 1 is not. Some of the initial questions to these were worded so that for their response it was flipped (worded so for that question a 1 was pro-environment). The data is then saved in the Data folder as IPDData(MonthDate from above).csv. IPD stands for Initially Processed Data.
###     3. Secondary Data Processing
####          This then uses the support.CEs package to design survey questions (which were used in Qualtrics). It then arranges so each respondent goes from one observation to 36 observations. One for each alternative of each decision shown to them (three alternatives times twelve decisions). There is now a column of RES with values of TRUE or FALSE depending on if the respondent chose that alternative. The demographic and environmental/social views data is still with each observation. The data is then saved in the data folder as AD(MonthDate from above).csv. AD stands for Analysis Data.
###     4. WTP Calculations
####           This then calculates the MWTP for each attribute. The total WTP is assumed to be the sum of the MWTP plus some errors (measurement errors, not including other attributes of interest, etc). The output is a WTP table, barplot of the MWTP for each attribute, and a boxplot of the environmental and social views.
###     5. Anova Analysis
####          This takes the data and looks at anova and simple linear models. For example, with choosing local as the dependent variable, what independent variables are significant? Who, what attributes, or what demographics makes one more likely to choose an attribute.
###     6. Demographics
####          This takes the demographic information and makes it into various barplots and then saves them as pdfs.
###     7. Environmental and Social View
####          This takes the environmental and social responses and turns them into boxplots for each statement, all the statements, or category of statements and then saves as pdfs.


### Some basic information:
####     WTP: Willingness to Pay
####     MWTP: Marginal Willingness to Pay

####     Bouquet Attributes of Interest (and the levels)
#####          Production (Local, Fairtrade, Freshness Guaranteed Fairtrade, Standard)
#####          Organic (Yes or No)
#####          Carbon Offsetting (Yes or No)
#####          Grower Information (Yes or No)

####     Each respondent went through 12 buying decisions where they chose bouquet A, B or neither. Each bouquet was comprised of varying levels of attributes. They also ranked 21 environmental and social statements from strongly agree to strongly disagree and answered questions on their demographics. 
