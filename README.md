## Experiments Tracking with DVC Pipeline
This project demonstrates how to set up and manage machine learning experiments using DVC (Data Version Control). It provides a structured approach to track data, code, and experiments efficiently.


### ​ Project Structure

```bash
The repository is organized as follows:

Experiments-Tracking-DVC-Pipeline/
├── .dvc/                  # DVC configuration and cache
├── data/                  # Directory for datasets
├── src/                   # Source code for data processingand modeling
│    └── app.py           #  Python file with Experiments with DVC Pipeline
│
│
├── .dvcignore             # Files and directories ignored by DVC
├── .gitignore             # Files and directories ignored by Git
├── requirements.txt       # Python dependencies
└── text.txt               # Sample text file (purpose unspecified)
```

### Getting Started
Prerequisites
- Python 
- DVC installed
- Git installed

##  Installation
1. Clone the repository:
```
git clone https://github.com/SandeepSuthar169/Experiments-Tracking-DVC-Pipeline.git
cd Experiments-Tracking-DVC-Pipeline
```
2. Install the required Python packages:

```
pip install -r requirements.txt
```


3. Initialize DVC and Pull Data
```
dvc init
dvc pull
```
- Ensure you have access to the remote storage configured in the DVC setup.


## Usage
The src/ directory is intended for your data processing and modeling scripts. You can create DVC pipelines to manage your experiments.

Example:

1. Create a DVC stage for data preprocessing:
```
dvc run -n preprocess \
        -d src/preprocess.py -d data/raw \
        -o data/processed \
        python src/preprocess.py data/raw data/processed
```

2. Create a DVC stage for model training:


```
dvc run -n train_model \
        -d src/train.py -d data/processed \
        -o models/model.pkl \
        python src/train.py data/processed models/model.pkl
```
3. Visualize the pipeline:


- `dvc dag`
## Data Management
DVC allows you to manage large datasets efficiently. You can add data files or directories to DVC tracking:

- `dvc add data/raw`
This command creates a .dvc file that tracks the data, and you can commit this file to Git.

## Experiment Tracking
DVC provides features to track different experiments, compare them, and reproduce results. You can leverage these features to manage your machine learning experiments effectively.

## Testing
You can write tests for your code using frameworks like unittest or pytest. Place your test scripts in a separate tests/ directory and run them to ensure your code's correctness.
