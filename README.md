# Customer Churn Prediction

### Table of Contents

1. [Installation](#installation)
2. [Project Motivation](#motivation)
3. [File Descriptions](#files)
4. [Results](#results)
5. [Licensing, Authors, and Acknowledgements](#licensing)

## Installation <a name="installation"></a>
The code was tested using Python version 3.9. and Pyspark 3.1.2 .
For other necessary libraries please use requirements.txt
```bash
pip install -r requirements.txt
```

## Project Motivation<a name="motivation"></a>
Sparkify is the fictitious music service similar to Spotify where the users can have either a free account with advertisement or paid account without. The log contains the information about user interaction with the service e.g., number of items per session, artist/ songs they are listened to or information about the device etc.   



This project aim is to analyze the dataset containing user churns in order to identify the customer who are dissatisfied with the service before they cancel the subscription. 

For this project, it was of interest in investigation of : 

1. Which factors have impact on the cancelling the subscription? 
2. How well can we predict customer churn? 


 The analysis, data exploration as well as building/ tuning machine learning models involves **Pyspark**.

## File Descriptions <a name="files"></a>
The repository contains one notebook with all necessary tools and steps.  
-	Load Data into Spark and Clean Dataset 
-	Exploratory Data Analysis
-	Feature Engineering
-	Modeling
-	Churn Prediction


The analysis was limited to data subset. The data was provided by Udacity and unfortunately couldn’t be uploaded due to the size. 

## Results<a name="results"></a>
The baseline is to compare different ML algorithms based on their default settings except to include the column classWeightCol to re-balance the weights  

| Model | f1_score | Area Under ROC |accuracy |time ms |
| :---: | :---: | :---: | :---: | ---: | 
| LogisticRegression | 0.52 | 0.43 |0.5   |309
| LogisticRegression + Threshold| 0.37 | 0.43  |0.37   | -
| LinearSVC  | 0.52 | 0.39 |0.5   | 3257
| RandomForest | 0.6 | 0.59 |0.67  | 79
| Gradient-boosted Tree | 0.66 | 0.51 |0.7   | 852

Parameter Tuning was done for all above models except LinearSVC due to the fact that this algorithm achieved the same results as LogisticRegression but the training last 10 times longer.

| Model | f1_score | Area Under ROC |accuracy |
| :---: | :---: | :---: | :---: |
| LogisticRegression Test Set | 0.49 | 0.46 |0.47   |
| LogisticRegression Validation Set| 0.72| 0.53  |0.7   | 
| RandomForest Test Set| 0.56 | 0.5 |0.67  | 
| RandomForest Validation Set| 0.74 | 0.52 |0.8  | 
| Gradient-boosted Tree Test Set| 0.71 | 0.48 |0.73   | 
| Gradient-boosted Validation Test Set| 0.58 | 0.41 |0.57  | 

The main findings of the code can be found at the post available [here](https://eneuburg.medium.com/3012772cab48).

## Licensing, Authors, Acknowledgements<a name="licensing"></a>
 

Great thanks to Udacity for their contribution during the process.



###### Copyright (C) 2021 August
###### TO THE FULLEST EXTENT PERMITTED UNDER APPLICABLE LAW, THE CODE COMPONENTS ARE PROVIDED BY THE AUTHORS, COPYRIGHT HOLDERS, CONTRIBUTORS, LICENSORS, “AS IS”.

######  DISCLAIMED ARE ANY REPRESENTATIONS OR WARRANTIES OF ANY KIND, WHETHER ORAL OR WRITTEN, WHETHER EXPRESS, IMPLIED, OR ARISING BY STATUTE, CUSTOM, COURSE OF DEALING, OR TRADE USAGE, INCLUDING WITHOUT LIMITATION THE IMPLIED WARRANTIES OF TITLE, MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE, AND NON-INFRINGEMENT.
######  IN NO EVENT WILL THE COPYRIGHT OWNER, CONTRIBUTORS, LICENSORS BE LIABLE FOR ANY DIRECT, INDIRECT, INCIDENTAL, SPECIAL, EXEMPLARY, OR CONSEQUENTIAL DAMAGES (INCLUDING, BUT NOT LIMITED TO, PROCUREMENT OF SUBSTITUTE GOODS OR SERVICES; LOSS OF USE, DATA, OR PROFITS; OR BUSINESS INTERRUPTION). HOWEVER, CAUSED AND ON ANY THEORY OF LIABILITY, WHETHER IN CONTRACT, STRICT LIABILITY, OR TORT (INCLUDING NEGLIGENCE OR OTHERWISE) ARISING IN ANY WAY OUT OF THE USE OF THE CODE COMPONENTS, EVEN IF ADVISED OF THE POSSIBILITY OF SUCH DAMAGE. 


