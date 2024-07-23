# Iris Flower Classification Project

This project demonstrates the implementation of a machine learning pipeline to classify iris flowers into three species (Setosa, Versicolor, Virginica) using the Iris dataset from the UCI Machine Learning Repository. The project involves data acquisition, ingestion, processing, model training, and visualization using various tools and technologies such as Python, Azure Blob Storage, Azure SQL Database, Azure Data Factory, and Power BI.

## Project Structure

- **Irisclassification.ipynb**: Jupyter Notebook containing the code for data preprocessing, model training, and evaluation.
- **Load dataset.ipynb**: Jupyter Notebook containing the code for loading the Iris dataset and saving it as a CSV file.

## Project Overview

### Data Acquisition
The Iris dataset was acquired using the `load_iris` function from the Scikit-learn library. The dataset was then converted into a Pandas DataFrame and saved as a CSV file.

### Data Storage
The CSV file (iris.csv) was uploaded to Azure Blob Storage, serving as the source for data ingestion.

### Data Ingestion
Using Azure Data Factory, a pipeline was created to transfer the data from Azure Blob Storage to Azure SQL Database. A table named `iris_data` was created in the database to store the dataset.

### Data Processing and Model Training
The data was loaded from the Azure SQL Database into a Pandas DataFrame for preprocessing. A Support Vector Machine (SVM) classifier was trained using Scikit-learn, achieving high accuracy.

### Data Visualization
The results were visualized using Power BI, including a confusion matrix and pair plots.

## Setup and Usage

### Prerequisites
- Python 3.x
- Jupyter Notebook
- Azure account
- Azure Blob Storage
- Azure SQL Database
- Azure Data Factory
- Power BI

### Steps

#### Load and Save Dataset:

1. Open the `Load dataset.ipynb` notebook.
2. Run the cells to load the Iris dataset and save it as `iris.csv`.

#### Upload CSV to Azure Blob Storage:

1. Create a container in Azure Blob Storage.
2. Upload the `iris.csv` file to the container.

#### Create Table in Azure SQL Database:

1. Connect to your Azure SQL Database.
2. Run the following SQL script to create the `iris_data` table:
   ```sql
   CREATE TABLE iris_data (
       sepal_length FLOAT,
       sepal_width FLOAT,
       petal_length FLOAT,
       petal_width FLOAT,
       target INT
   );
### Data Ingestion using Azure Data Factory:
1. Create linked services for Azure Blob Storage and Azure SQL Database.
2. Create datasets for the source (Azure Blob Storage) and sink (Azure SQL Database).
3. Create and configure a pipeline with a Copy Data activity.
4. Run the pipeline to transfer data from Azure Blob Storage to Azure SQL Database.

### Data Processing and Model Training:
1. Open the `Irisclassification.ipynb` notebook.
2. Run the cells to load data from Azure SQL Database, preprocess the data, train the SVM model, and evaluate its performance.

### Data Visualization in Power BI:
1. Load the data from Azure SQL Database into Power BI.
2. Create visualizations such as scatter plots, pair plots, and confusion matrix.

### Results
- The SVM model achieved high accuracy in classifying the iris species.
- Visualizations in Power BI provided insights into the model's performance and the relationships between features.

### Challenges
- Configuring data ingestion in Azure Data Factory.
- Establishing a connection to Azure SQL Database using Python.

### Future Work
- Experiment with other machine learning models.
- Optimize data processing and model performance.

### Contributing
Contributions are welcome! Please feel free to submit a pull request or open an issue.

### License
This project is licensed under the MIT License. See the LICENSE file for details.
