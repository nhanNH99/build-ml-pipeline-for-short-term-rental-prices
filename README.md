# Build an ML Pipeline for Short Term Rental Prices in NYC

The project provided me with the fundamental knowledge of using MLflow combined with W&B. This is a project in the Udacity course.

# Set up and install 

Step 1: Fork the git from uda repo and move to the project

`
git clone https://github.com/nhanNH99/build-ml-pipeline-for-short-term-rental-prices.git
`

`
cd build-ml-pipeline-for-short-term-rental-prices 
`

Step 2: Create the enviroment 

`
conda env create -f environment.yml
`

`
conda activate nyc_airbnb_dev
`

Step 3: Create the API key for Weights and Biases

`
wandb login [your API key]
`

Step 4: Set up cookie cutter

if you can't find the cookiecutter, you can run :
`
sudo apt install cookiecutter
`

### INFO ABOUT WANDB ACCOUNT : 
Link: https://wandb.ai/ngonhanit-fpt/nyc_airbnb

After that:

`
cookiecutter cookie-mlflow-step -o src
`

## EDA data 

Download data ` mlflow run . -P steps=download`

EDA step: 

`
mlflow run src/eda
`

## DATA CLEANING


`
mlflow run . -P steps=basic_cleaning
`

## DATA TESTING

`
mlflow run . -P steps=data_check
`

## TRAINING RANDOM FOREST
You must to download and split train/val data: `mlflow run . -P steps=data_split`

And training: 

`
mlflow run . -P steps=train_random_forest
`

## GIT FLOW AND RELEASE 
You can run step by step

Step 1: 
`
git add .
`

Step 2: 
`
git commit -m "your commit"
`

Step 3: 
`
git tag -a 1.0.1 -m "Version 1.0.1"
`

Step 4: 
`
git push origin 1.0.1
`


## FINALLY, you can run the new data with CLI terminal 

`
mlflow run https://github.com/nhanNH99/build-ml-pipeline-for-short-term-rental-prices.git -v 1.0.1 -P hydra_options="etl.sample='sample2.csv'"
`



