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
                [('Gender', 'Marital Status'), 
                ('Gender', 'Occupation'), 
                ('Gender', 'Exercise Frequency'), 
                ('Marital Status', 'Gender'), 
                ('Marital Status', 'Smoking Status'), 
                ('Occupation', 'Gender'), 
                ('Occupation', 'Property Type'), 
                ('Smoking Status', 'Marital Status'), 
                ('Exercise Frequency', 'Gender'), 
                ('Property Type', 'Occupation')]
            # Nan Analysis:
                - numerical var : 45046/1200000 not NAN
                - categorical var : 45746/1200000 not NAN
                
            