# Introduction: 

    for successfully running the business it is important to reasonably control a lot of resources, including human resources.
    In the real world, employee attrition might occur due to various and sometimes unexpected reasons and it may create problems for the business.
    In order to prevent such cases and to optimise and ease the work of HR processes in the companies we have started working on that projects

    In this project, we decided to work with the dataset containing various details of each individual empolyee including his proffesional and personal information as well as his attitude, position, salary and etc.. at the workplace.



# Objectives: 

    Our goals:

        1. To develop a ML model that predicts the attrition status
    
        2. To develop a DL model that predicts the attrition status
    
        3. To find insights into the patterns between work-life balance, attitude, perosnal and many more factors and how it affects the attrition rates.

        

# Description:  

    1. Type of problem: classification.

    2. Variables: 26 Numerical, 8 Categorical:          

    3. Target: Attrition (object):

          1. Attrition: whether the employee got attrition or not

    4. Steps we made
  
          1. Train / Test split:
    
                > Train - 70%
    
                > Test - 30%

        2. Imputation of Nan values:

              > Numerical - MeanMedianImputer
  
              > Categorical - FrequentCategory

        3. Categorical variables Encoding:

              > OneHotEncoder - ('BusinessTravel', 'Gender', 'MaritalStatus', 'Over18', 'OverTime')
  
              > count_frequency_encoder - (other variables)

        4. Discretization:

              > EqualFrequencyDiscretiser

        5. Scaling:

              > RobustScaler

        6. Feature Selection:

              1. Filtering methods:
  
                    > Constant variables
    
                    > Quasi-Constant variables
    
                    > Duplicated variables
    
                    > Correleted variables
  
              2. Wrapper methods:
  
                    > RFE (based on RandomForestClassifier)

        7. Balancing dataset:

              > RandomOverSampler
  
              > RandomUnderSampler
  
              > SMOTE

        8. Training Classification Algorithms

        9. Fine-tuning hyperparameters:

              > GridSearchCV

        10. Training ANN

        11. Model evaluation and result analysis

    
    
    5. Deep Learning Algorithms we used:

          For predicting the pollution rate for the next hour:
  
                1. LSTM (Long-Short-Term Memory) with 2 hidden layers (100 neurons each).
    
                2. LSTM with 4 hidden layers (100 neurons each) + 3 Dropout layers (0.3)
    
              
          For predicting the pollution rate for the next hour:
  
                1. LSTM (Long-Short term memory) with 2 hidden layers (100 neurons each) + 2 Dropout layers (0.6, 0.5)


     
    6. Evaluation Metrix we used:

          1. Mean Absolute Error(MAE)
  
          2. Mean Square Error(MSE)
  
          3. Root Mean Square Error(RMSE)
  
          4. R2 score



# Conclusion

##  Data Analysis

    After completing the data analysis step, we found several insights. 

          1. The older the employee the more working years he has.
  
          2. Years spent at a company and total working years are highly correlated which means that people tend to work a lot in one place.
  
          3. The higher the total working years, the higher the job level and vice versa.
  
          4. The higher the total working years, the higher the monthly income.
  
          5. It seems that employee spend most of their working years at company in one role.
  
          6. It seems that the amount of years working in one role is highly correlated with the current manager.
  
          7. It seems that the job level and the monthly income has a correlation with years at the company.
  
          8. The years spend with current manager highly correlated with total years at company.
  
          9. Monthly income is highly correlated with job level.
  
          10. Women in Human Resources experienced the highest amount of turnover, with nearly 1 out of every 3 women in HR leaving the company. For men, the highest turnover occurred in the Sales department.
  
          11. Among employees who left, the majority were satisfied in their job with 53% rating their job satisfaction as Good or Excellent, while 28% were least satisfied in their job.
  
          12. Across each department, women on average have higher salaries than men.
  
          13. In comparison to current employees, former employees had lower median salaries across all three departments. In Human Resources, women tend to have higher median salaries than men.
  
          14. Women with the lowest-rated work-life balance have the highest median salary out of all of the groups at $5,400/month.

        
        
## Training & Evaluating ML models
   
     > We have tested 5 popular models with the same data and same preprocessing steps to then compare them and choose only fixed amounts to tune the hyperparameters. 

     > After testing 5 models, we chose only 2 best models according to the accuracy metrics 

     > Then, we used cross-validation and started to fine-tune hyperparameters to boost the performance 

     > lastly, We have evaluated the models we built using several metrics including: 

           1. F1 score
  
           2. Roc-auc 
  
           3. Confusion Matrix 
  
           4. Precision
  
           5. Recall 
  
           6. Accuracy

        

    By analyzing all metrics we can tell that: 

          1. The results for accuracy, roc-auc and precision seems to be high enough. However, the resutls for recall and f1 are terrible having less than 50% which is not acceptible. It seems that is because of the extremely not-balanced datasets
  
          2. If we had to choose one, I would choose SVC because although it does not give the highest results, it gives the most stable and consistent results.


                
   ## Training & Evaluating ANN

        1. The loss has dropped to its minimum at 0.04 in the train set and 0.09 in the test set. The training process was stable

        2. The accuracy has reached it's maximum at about 95% in train and 87% in test set. The training process was stable

        3. It seems that ANN is not the best choice here, because in spite of the fact that the metrics including accuracy and ROC-AUC are better compared to the ML models, precision, recall and F1 are considerably lower than the ML models. 

        
        We tend to think that it would be better to gain more data and may be try to use different approaches to process the time series data and may be use something else for feature selection.

                
   # THANKS!!! :)
