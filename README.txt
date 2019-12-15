Process WiFi
Folder – SCRIPTS
Source File – Script00_Project_Sources
Subfolders - 
1 – Preparation 
Script01_0_00-Libraries
Script01_1_00-Import
Script01_2_00-Inspection 
# View df info summary, stats, str, dim …
# Create df<-ori
Script01_3_00-Cleaning --->
# Check Column Headings
# Trim whitespaces
# Change 100 values to -110
# Check for Duplicate Vars
# Check Zero and Near Zero Variance
# Check Data Types
# Check for Missing Values
# Drop Unused Columns
# Rename Columns
# Clean the SPACEID String
# Create MAX value column
# Recode Variables

2 – Pre-Process
Script02_1_00-Manipulation
# Generate ID column which is used to join the various tables
# Create Specialized dfs
# headers_df: Transposed df Hearders
# eda_wap_df: Complete set of WAPS
# wap_details_df: Summarizes Totals of valid invalid and out of range WAPS
# eda_accessed_df: Full list per row of MAX, MIN, VALID, INVALID, TOT TRIES 

# Creation of base_df<-df
# eda_qnt_df: Contains all quantative vars
# Creation of STRENGTH attribute
# eda_qlt_df: Contains all qualitative vars
# Creation of QUALITY attribute

# final_wap_df: Filtered WAP Columns between -96 and -30

# wifi_df<- final_wap_df and all other Attributes

# Categorical data: create count tables to understand different categories.
# Failed access imputation (gather and spread, calculate Max, Min, Valid and Invalid accesses)
Script02_Plots
3 - EDA (Engineering Data Analysis)
Script03_1_00_Insight
#  Identify levels of possible response vars
#  This is a multi-class or a multinomial classification problem. 
# Find out the nlevels of the categorical vars
# Calculate the Percentage of STRENGTH for each Categorical var
# Make histograms to view frequencies of each categorical var
# Examine the data distribution of a qnt vars
# Make boxplots for each categorical var
# Explore the relationship between quantative vars LONGITUDE and LATITUDE
# PLOTTING CATEGORICAL COUNT VARS
# Calculating Quantiles and Whiskers
# Summarize qnt data with o
# Summarize qlt data with charSummary
# Calculate bivariates of QUALITY against qlt vars
# Rerun new datasets for qnt, qlt, accessed, wap based on wifi_df
# Plot validity against invalidity of each observation

Script03_1_02_Plotting_3D
Script03_2_00_Correlation
# Data needs to be normaly distributed to decide the correlation

# Test Correlation between eda_qnt_df ~ model_qnt_df
# Test Correlation between eda_accessed_df ~ model_accessed_df
    # cor.test
    # Find high correlated vars
# Take out any uncorrelated vars from the datasets 
# Corrplot access vars and qnt vars

Script03_2_01_CLUSTERING
# Scale the data (column wise)
# K-means
	# kmean_withinss
# Clustering Analysis
# Elbow Technique to find optimal number of clusters
# VIF to test if the vars suffer from multicollinearity
# Check for multicollinearity in numeric data
# Do a first lm

Script03_3_00_Chai-Square
Script03_3_01_PCA
# No further processing
Script03_3_02_MDS
# No further processing

4 - MODELS 
Script04_1_ModelData
# Factorize variable that will act as predictors
# Make a model on wifi_df
# Create a function that can be called from all Trainings
  # Split the data into a smaller subset
  # Split the data into training (75%) and test set (25%)
  # Create a 5 fold cross validation

# Divide wifi_df into groups by Predictor Vars: Run model

PLAN of ATTACK for all Models
# Call the function
# Fit the Model 
# Print Accuracy and Kappa values
# Compute the prediction error RMSE
# Plot final Tree Model
# Make predictions
# Confusion Matrix to see how well the prediction went
# Run a confusion Matrix to view errors
# Analyze the Errors

Models tested
Script04_CLS-KN
Script04_CLS-RF
Script04_CLS-RPART
Script04_CLS-SVM
