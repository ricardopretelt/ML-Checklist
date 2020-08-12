# Machine Learning Checklist

## 1 Understand the problem
    1. Define the business problem and the objective 
    2. Define what are the variables, the target and the restrictions
    3. How would you solve the problem manually?
    4. Define in paper your ML solution. How will it work?
    5. What are the current solution/ workarounds?  What are the time and accuracy? Use as reference.
    6. How should you frame the ML problem? (supervised/unsupervised, online/offline, classification/regression, out-of-core? Send to multiple servers?)
    7. How should performance be measured? (MSE?, RMSE?)
    8. Is the performance measure aligned with the business objective?
    9. What would be the minimum performance needed to reach the business objective?
    10. What are comparable problems? Can you reuse experience or tools?
    11. Is human expertise available? Do you know, or at least can reach an expert in the field? Ask questions like What is the most important variable to reach the goal? What does he do to solve the problem?
    12. List the assumptions you (or others) have made so far, and verify them if possible
## 2 Get the data
    1. Define the data that you need  to solve the problem
    2. Find where you can get the data or design a method to produce the database (running an experiment or setting sensors to gather the data)
    3. Check how much space the database will take. Check the size so it fits in space in the drive and also it can be manageable in RAM. 
    4. Check legal obligations, and get authorization if necessary
    5. Create a workspace (with enough storage space) and also the needed environment 
    6. Check the type of the data (.CSV is the most common)
    7. Get the data
    8. Convert the data to a format you can easily manipulate (without changing the data itself) Most of the time you convert .csv data to dataframe.
    9. Ensure sensitive information is deleted or protected 
    10. Sample a test set, put it aside and don't look at it.
## 3 Explore the data to gain insights
    1. Create a copy of the data for exploration. Sample it down to a manageable size if necessary. If it is too large it can be sent to the cloud to work it there.
    2. Create a Jupyter notebook to keep a record of the data exploration
    3. Study each attribute and its characteristics: Name, Type (time series, sample, geographical, .json), % of missing values, Noisiness and type of noise (stochastic, outliers, rounding errors), Usefulness for the task, Type of distribution (Gaussian, uniform, logarithmic), scale of the attributes (for example USD or thousands of USD)
    4. If there is data in an unreadable form, convert it to readable (for example .JSON to string)
    5. If there is data of the same attribute but with different units or scale, set all to one.
    6. For supervised learning tasks, identify the target attributes
    7. Visualize the data. If the data is tail heavy it would be harder to predict. Also check for outliers or strange behaviors like rows of zeros
    8. Study the correlation between attributes.  Sometimes quirks in the correlation plot may be indicators to remove some data, for example straight lines that can confuse the model.
    9. Study how you would solve the problem manually
    10. Identify the promising transformations you may want to apply
    11. Identify extra data that would be useful
    12. Document everything learned
## 4 Preprocess the data that goes into the machine learning models
    1. Create a copy for the preprocessing 
    2. Write functions for all data transformations
    3. Do a stratified sampling based on the most influential variable. Random sampling is applicable just for huge datasets
    4. Fix or remove outliers (optional)
    5. Fill in missing values (with zero, mean, median...) or drop rows or column
    6. Feature selection (optional): Drop attributes not useful for the task
    7. Discretize continuous features
    8. Decompose features (categorical, date/time)
    9. Add promising transformations of features (log(x), sqrt(x), x²)
    10. Aggregate features into promising new features
    11. Feature scaling: Standardize or normalize features
## 5 Try out different models and list the best ones
    1. If the data is huge, sample smaller training sets to train more different models in less time
    2. Train many models fast with standards parameters
    3. Measure and compare their performance. Use cross-validation and calculate mean and std
    4. Analyze the most significant variables for each algorithm
    5. Analyze the errors of the models. How a human could have avoided the error?
    6. Quick round of feature selection and engineering
    7. 1 or 2 more quick iterations of the five previous steps
    8. Short list the top 3 to 5 most promising models. Prefer models that make different types of errors
## 6 Fine-tune your models and combine them into a great solution
    1. Fine tune using cross validation and as much data as possible
    2. Treat your data transformation choices as hyperparameters when you are not sure about them
    3. Prefer random search over grid search
    4. Ensemble methods
    5. Once you are confident about the final model, measure its performance on test set 
## 7 Present your solution
    1. Document what you have done
    2. Create a nice presentation: Highlight big picture first
    3. Explain why your solution achieves the business objective
    4. Describe what worked and what didn't, list assumptions and system's limitations
    5. Use beautiful visualizations and easy to remember statements 

## 8 Launch, monitor and maintain your system
    1. Get solution ready for production: Plug into production data inputs, write unit tests
    2. Write monitoring code
    3. Retrain your model on a regular basis
