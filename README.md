# Loan Approval Prediction
Loan approval predictions based on client's credit score and finance.

## Virtual Environment
1. Install Anaconda. [Anaconda](https://www.anaconda.com/)
2. Open the Anaconda Prompt or Terminal on your system.
3. Navigate to the directory where you want to create the virtual environment using the cd command.
4. Run the following command to create a new virtual environment:

```
conda create --name myenv python=3.8 -y
conda activate myenv
conda install ipykernel

# Check Virtual Environments
conda info --envs

# Remove the virtual environment
conda deactivate
conda remove --name myenv --all

# Verify existing environments
conda env list
```

## Basic GitHub commands
```
git pull
git add .
git commit -m "adding readme notes"
git push -u origin main

# Check status
git status
git remote -v

# Remove files
git rm -r folder_name
## Example:
git rm -r --cached venv

```

## Connect Virtual Environment to cloned repository
1. In VS Code, open the cloned repository folder.
2. Press Ctrl+Shift+P (Windows/Linux) or Cmd+Shift+P (macOS) to open the Command Palette.
3. Type "Python: Select Interpreter" and select the option.
4. From the list of available interpreters, choose the one corresponding to your 'loan' virtual environment (e.g., ~/anaconda3/envs/loan/python.exe on Windows or ~/anaconda3/envs/loan/bin/python on macOS/Linux).
5. Verify that the 'loan' virtual environment is selected in the bottom-left corner of the VS Code window.

## Tools used in this project
* [hydra](https://hydra.cc/): Manage configuration files - [article](https://mathdatasimplified.com/stop-hard-coding-in-a-data-science-project-use-configuration-files-instead/)
* [pdoc](https://github.com/pdoc3/pdoc): Automatically create an API documentation for your project
* [pre-commit plugins](https://pre-commit.com/): Automate code reviewing formatting


## Project Structure

```bash
.
├── config                      
│   ├── main.yaml                   # Main configuration file
│   ├── model                       # Configurations for training model
│   │   ├── model1.yaml             # First variation of parameters to train model
│   │   └── model2.yaml             # Second variation of parameters to train model
│   └── process                     # Configurations for processing data
│       ├── process1.yaml           # First variation of parameters to process data
│       └── process2.yaml           # Second variation of parameters to process data
├── data            
│   ├── final                       # data after training the model
│   ├── processed                   # data after processing
│   └── raw                         # raw data
├── docs                            # documentation for your project
├── .gitignore                      # ignore files that cannot commit to Git
├── Makefile                        # store useful commands to set up the environment
├── models                          # store models
├── notebooks                       # store notebooks
├── pyproject.toml                  # Configure black

├── README.md                       # describe your project
├── src                             # store source code
│   ├── __init__.py                 # make src a Python module 
│   ├── process.py                  # process data before training model
│   ├── train_model.py              # train model
│   └── utils.py                    # store helper functions
└── tests                           # store tests
    ├── __init__.py                 # make tests a Python module 
    ├── test_process.py             # test functions for process.py
    └── test_train_model.py         # test functions for train_model.py
```
## Folder Structure Template
Install Cookiecutter
```
pip install cookiecutter
```
Create a project based on the template
```
cookiecutter https://github.com/khuyentran1401/data-science-template
```

## Set up the requirements

1. Install [Poetry](https://python-poetry.org/docs/#installation)
```
conda install -c conda-forge poetry
```
2. Activate the virtual environment:
```bash
poetry shell
```
3. Install dependencies:
- To install all dependencies from pyproject.toml, run:
```bash
poetry install
```
- To install only production dependencies, run:
```bash
poetry install --only main
```
- To install a new package, run:
```bash
poetry add <package-name>
```


## View and alter configurations
To view the configurations associated with a Pythons script, run the following command:
```bash
python src/process.py --help
```
Output:
```yaml
process is powered by Hydra.

== Configuration groups ==
Compose your configuration from those groups (group=option)

model: model1, model2
process: process1, process2


== Config ==
Override anything in the config (foo.bar=value)

process:
  use_columns:
  - col1
  - col2
model:
  name: model1
data:
  raw: data/raw/sample.csv
  processed: data/processed/processed.csv
  final: data/final/final.csv
```

To alter the configurations associated with a Python script from the command line, run the following:
```bash
python src/process.py data.raw=sample2.csv
```

## Auto-generate API documentation

To auto-generate API document for your project, run:

```bash
make docs
```


