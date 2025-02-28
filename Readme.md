                            Regression with an Insurance Dataset

    Goal : The objectives of this challenge is to predict insurance premiums based on various factors
    Evaluation: Root Mean Squared Logarithmic Error (RMSLE) --> metric: RMSLE 

    I - EDA (Exploratory Data Analysis)
        Objective: Maximise data understanding to define a modelling strategy.
        1 - Shape analysis : 
            # Target identification : Premium Amount
            # Number of rows and columns : (1200000, 21)
            # Variable types : object 11, float64 9, int64 1
            # Identification of missing values : few missing data compared to the size of the dataset and no data groups identified

        2 - Background analysis:
            # Target visualisation : 
                Asymmetric data distribution
                premium 0, count arround 65000 
                premium 100 - 300, count arround 13000
                premium around 350, count arround 35000
                premium around 2000, count arround 2500 
            # Understanding the different variables
                - Quantitative variables : 
                    Age = Uniform Distribution
                    Annual Income = Asymmetric distribution
                    Number of Dependents = Distribution multimodale
                    Health Score =  Normal distribution
                    Previous Claims = Asymmetric & multimodale distribution
                    Vehicle Age = Distribution multimodale
                    Credit Score = Asymmetric distribution
                    Insurance Duration = Distribution multimodale
                - Qualitative variables : 
                    several categories for each variable, 
                    equal distribution of data by category, 
                    Occupation : 23.8% Nan
            # Visualising features-target relationships
                -Variable numerical/ target : No obvious correlation
                -variable categorical/ target : many outliers

        3 - Detailed analysis :
            # Relationship between variables and variables:
                -Variable numerical/Variable numerical: No obvious correlation
                -variable categorical/variable categorical : after chi2 test
                    strong correlation between : 
                    Gender as a significative correlation with Marital Status
                    Gender as a significative correlation with Smoking Status
                    Marital Status as a significative correlation with Occupation
                    Marital Status as a significative correlation with Customer Feedback
                    Marital Status as a significative correlation with Property Type
                    Education Level as a significative correlation with Location
                    Education Level as a significative correlation with Policy Type
                    Education Level as a significative correlation with Exercise Frequency
                    Education Level as a significative correlation with Property Type
                    Occupation as a significative correlation with Property Type
                    Location as a significative correlation with Customer Feedback
                    Policy Type as a significative correlation with Exercise Frequency
                    Customer Feedback as a significative correlation with Exercise Frequency
                    Customer Feedback as a significative correlation with Property Type
                -Numerical variable/Categorical variable :
                    Age could have an impact on Location
                    Annual Income could have an impact on Education Level
                    Annual Income could have an impact on Exercise Frequency
                    Number of Dependents could have an impact on Exercise Frequency
                    Number of Dependents could have an impact on Property Type
                    Health Score could have an impact on Gender
                    Health Score could have an impact on Education Level
                    Health Score could have an impact on Location
                    Health Score could have an impact on Policy Type
                    Health Score could have an impact on Smoking Status
                    Health Score could have an impact on Property Type
                    Previous Claims could have an impact on Policy Type
                    Vehicle Age could have an impact on Property Type
                    Credit Score could have an impact on Education Level
            # Nan Analysis:
                - numerical var : 595316/1200000 not NAN
                - categorical var : 775274/1200000 not NAN
    II - Preprocessing
    Objective: Transform data into a format suitable for machine learning.
        1 - Put data in a format suitable for ML
             # Create train set/ Test set
             # Encode : onehotencoder because we have several categories in categorical variable
             # Eliminate NAN: dropna(), imputation, empty columns
             #--> first model: eval-->diagnosis (principle: idea --> code --> eval)
        2 - Improve model performance
             # Feature selection
             # Feature Engineering
             # Feature Scaling
             # Remove outliers harmful to the model

    III - Modeling
                
            