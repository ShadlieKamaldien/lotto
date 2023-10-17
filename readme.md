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

Follow the below steps
Access Jupyter Notebook from Compute Instance:
In Azure ML Studio, navigate to the Compute section.
Under Compute Instances, find your instance and click on the Jupyter link to open JupyterLab.
Create a New Python Notebook:
Once you're inside JupyterLab, you can create a new Python notebook by clicking on the + button and then selecting a Python notebook from the launcher.
Connect to Your Workspace:
In the first cell of the notebook, establish a connection to your workspace:
<img width="299" alt="image" src="https://github.com/ShadlieKamaldien/lotto/assets/54892771/454d8c74-03ab-471a-bf82-43c84b330119">



