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
python

Below is a snippet of the code explained. 
from azureml.core import Workspace, Datastore, Dataset
Imports necessary modules from the Azure Machine Learning SDK. Specifically, it imports the Workspace, Datastore, and Dataset classes.
python

import itertools
Imports the itertools module, which contains tools for working with iterators (like generating combinations of numbers).
python

# 1. Connect to workspace and load the data
ws = Workspace.from_config()
Connects to an Azure Machine Learning workspace using a configuration file (config.json typically) and assigns this workspace object to the variable ws.
python

# Access the default datastore
datastore = Datastore.get(ws, datastore_name='workspaceblobstore')
Retrieves the default datastore (named 'workspaceblobstore') associated with the workspace.
python

# Define the path on the datastore
datastore_path = [(datastore, 'UT/2023-10-16_074816_UTC/combined.csv')]
Defines the path to the file on the datastore. The path is a combination of the datastore and the relative path to the file.
python

# Create a dataset from the file(s) in the datastore
dataset = Dataset.Tabular.from_delimited_files(path=datastore_path)
Creates a tabular dataset from the file specified by datastore_path.
python

# Convert to pandas dataframe
df = dataset.to_pandas_dataframe()
Converts the Azure ML dataset into a pandas DataFrame for easier data manipulation.
python

# 2. Find sequences that haven't been played
all_combinations = set(itertools.combinations(range(1, 51), 6))
Generates all possible combinations of 6 numbers from 1 to 50 (inclusive) and stores them in a set called all_combinations.
python

for index, row in df.iterrows():
Iterates over each row in the DataFrame df.
python

    sequence = tuple(sorted(row))
Takes the current row (which represents a sequence of numbers), sorts it, and then converts it to a tuple.
python

    all_combinations.discard(sequence)
Removes (discards) the current sequence from the set of all_combinations. If the sequence is not in the set, the method does nothing (this is why discard is used instead of remove).
python

# 3. Display results without overwhelming the output
print("Number of sequences that haven't been played yet:", len(all_combinations))
Prints the number of sequences that haven't been played yet (i.e., the remaining number of combinations in the set).
python

sample_sequences = list(all_combinations)[:10]
Converts the set of remaining combinations into a list and takes the first 10 sequences as a sample.
python

print("\nSample of sequences that haven't been played:", sample_sequences)
Prints the sample sequences that haven't been played yet.
In summary, this code connects to an Azure Machine Learning workspace, retrieves a dataset of played lottery combinations, and then determines


