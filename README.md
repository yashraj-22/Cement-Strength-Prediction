# Cement Strength Prediction

## Problem Statement
The quality of cement is determined by its compressive strength, which is measured
using a conventional crushing test on a cement cylinder. The strength of the concrete
is also a vital aspect in achieving the requisite longevity. It will take 28 days to test
strength, which is a long period. So, what will we do now? We can save a lot of time and
effort by using Data Science to estimate how much quantity of which raw material we
need for acceptable compressive strength.

## Variable Description
* Cement (component 1) -- quantitative -- kg in a m3 mixture -- Input Variable
* Blast Furnace Slag (component 2) -- quantitative -- kg in a m3 mixture -- Input Variable
* Fly Ash (component 3) -- quantitative -- kg in a m3 mixture -- Input Variable
* Water (component 4) -- quantitative -- kg in a m3 mixture -- Input Variable
* Superplasticizer (component 5) -- quantitative -- kg in a m3 mixture -- Input Variable
* Coarse Aggregate (component 6) -- quantitative -- kg in a m3 mixture -- Input Variable
* Fine Aggregate (component 7) -- quantitative -- kg in a m3 mixture -- Input Variable
* Age -- quantitative -- Day (1~365) -- Input Variable
* Concrete compressive strength -- quantitative -- MPa -- Output Variable

Dataset Link: [https://www.kaggle.com/datasets/maajdl/yeh-concret-data](https://www.kaggle.com/datasets/maajdl/yeh-concret-data)

## AWS Deployment link
AWS Elastic Beanstalk link: [http://cementstrengthpredictor-env-1.eba-a2i3wqzs.eu-north-1.elasticbeanstalk.com/predictdata](http://cementstrengthpredictor-env-1.eba-a2i3wqzs.eu-north-1.elasticbeanstalk.com/predictdata)

## UI Screenshot
![Capture1](https://user-images.githubusercontent.com/69323672/234964782-324a43d4-7292-48b4-a226-81465e905816.JPG)
![Capture](https://user-images.githubusercontent.com/69323672/234965008-caed6c5f-9412-4662-a1c5-6e8ac4c540df.JPG)

## Project Approach
1. Data Ingestion:
    * In Data Ingestion phase the data is first read as csv.
    * Then the data is split into training and testing and saved as csv file.

2. Data Transformation:

    * In this phase a ColumnTransformer Pipeline is created.
    * For Numeric Variables first SimpleImputer is applied with strategy median, then Standard Scaling is performed on numeric data.
    * This preprocessor is saved as a pickle file.

3. Model Training:

    * In this phase base model is tested.
    * After this hyperparameter tuning is performed.
    * This model is saved as a pickle file.

4. Prediction Pipeline:

    * This pipeline converts given data into dataframe and has various functions to load pickle files and predict the final results in python.

5. Flask App creation:
    * Flask app is created with User Interface to predict the cement strength inside a Web Application.
