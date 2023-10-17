Azure ML Analysis of Historical Lottery Data
This project uses Azure Machine Learning (Azure ML) and JupyterLabs to process, analyze, and generate insights from 5 years of historical lottery data. The aim is to explore patterns and provide unique lottery combinations not previously seen in the dataset.

Project Workflow:
1. Data Acquisition
Visit Lottology.com
Download the historical lottery data, which will be in .txt format.
2. Data Transformation
Clean the acquired data to remove any inconsistencies or errors.
Transform the cleaned .txt data into a more manageable .csv format, suitable for further processing and analysis.
3. Setting up Azure ML
Create a new Azure Machine Learning workspace. If you're new to Azure ML, here's a guide https://docs.microsoft.com/en-us/azure/machine-learning/how-to-manage-workspace to help you get started.
4. Data Upload
Upload the transformed .csv file into the Azure ML workspace datastore.
5. Compute Environment
Initiate a compute instance in Azure ML. Ensure you select appropriate compute specifications based on the size and complexity of your dataset.
6. Analysis using JupyterLabs
Once your compute is up and running, launch JupyterLabs.
Run your analysis code within JupyterLabs, making use of Azure ML's integrated tools and capabilities.
