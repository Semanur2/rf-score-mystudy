# Molecular Docking Scoring Function

This repository contains a saved scoring function for molecular docking calculations. The scoring function is serialized in a `.pkl` file format, which can be loaded and used in your own molecular docking workflow.

## Prerequisites

- Python 3.x
- [ODDT](https://github.com/oddt/oddt) library (for handling molecular files and scoring)
- Pickle library (Python standard library)

## Installation

Clone this repository to your local machine:

```bash
git clone https://github.com/YourGitHubUsername/your-repository-name.git
Ensure you have the necessary Python libraries installed:


pip install oddt
Loading the Scoring Function
You can load the scoring function saved in the .pkl file with the following Python code:

import pickle

# Specify the file path (assuming it is saved on the desktop)
file_path = r'C:/Users/YourUsername/Desktop/my_sf.pkl'

# Load the .pkl file
with open(file_path, 'rb') as file:
    loaded_scoring_function = pickle.load(file)

# Print the loaded object
print(loaded_scoring_function)  # Optional: Print the loaded object for verification
Using the Scoring Function
Once you’ve loaded the scoring function, you can use it to calculate docking scores for ligands and proteins. Here’s an example of how to use it:


# Load protein and ligands (replace with your own file paths)
protein = next(oddt.toolkit.readfile('mol2', 'path/to/your/protein.mol2'))
ligands = list(oddt.toolkit.readfile('mol2', 'path/to/your/ligands.mol2'))

# Set the protein and predict docking scores for the ligands
loaded_scoring_function.set_protein(protein)
scores = loaded_scoring_function.predict(ligands)

# Print the scores for each ligand
for idx, score in enumerate(scores):
    print(f"Score for Ligand {idx + 1}: {score}")
Output
The program will output docking scores for each ligand in the provided ligand file.

Contributing
If you would like to contribute to this repository, please fork the repository and submit a pull request with your changes.
