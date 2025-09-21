# Music Genre Recommender

A machine learning project that predicts music genre preferences based on user demographics (age and gender). This is my first machine learning project, built to explore and learn fundamental ML concepts.

## 📖 Project Overview

This project uses a **Decision Tree Classifier** to predict music genre preferences. The model analyzes user age and gender to recommend one of four music genres:
- **HipHop**
- **Jazz** 
- **Classical**
- **Dance**

### Learning Objectives
- Understand the machine learning workflow (data loading, training, testing, evaluation)
- Learn to use scikit-learn for classification tasks
- Practice data preprocessing and model evaluation
- Explore decision tree visualization
- Get hands-on experience with model persistence (saving/loading)

## 📊 Dataset

The project uses a small dataset (`data/music.csv`) with 18 samples containing:
- **age**: User's age
- **gender**: User's gender (1 = male, 0 = female)
- **genre**: Preferred music genre (target variable)

## 🛠️ Technical Stack

- **Python 3.x**
- **pandas** - Data manipulation and analysis
- **scikit-learn** - Machine learning algorithms and tools
- **joblib** - Model serialization
- **Jupyter Notebook** - Interactive development environment

## 🚀 Setup Instructions

### Prerequisites
- Anaconda or Miniconda installed

### 1. Clone the Repository
```bash
git clone github.com/jfgmesquita/my-first-ml-project.git
cd MachineLearning
```

### 2. Create and Activate Conda Environment
```bash
# Create environment from file
conda env create -f environment.yml

# Activate environment
conda activate ml_env
```

**Alternative setup (if environment.yml doesn't work):**
```bash
# Create new environment
conda create -n ml_env python=3.12

# Activate environment
conda activate ml_env

# Install dependencies
pip install -r requirements.txt
```

### 3. Launch Jupyter Notebook
```bash
jupyter notebook
```

Navigate to `notebooks/music_recommender.ipynb` and run the cells.

## 📁 Project Structure

```
MachineLearning/
│
├── data/
│   └── music.csv                    # Training dataset
│
├── models/
│   └── music-recommender.joblib     # Trained model (saved)
│
├── notebooks/
│   └── music_recommender.ipynb      # Main Jupyter notebook
│
├── outputs/
│   └── music-recommender.dot        # Decision tree visualization
│
├── .gitignore                       # Git ignore rules
├── environment.yml                  # Conda environment file
├── requirements.txt                 # Python dependencies
└── README.md                        # Project documentation
```

## How to Run

1. **Training and Evaluation**: Open and run `notebooks/music_recommender.ipynb`
2. **Make Predictions**: The notebook includes examples of predicting genres for new users
3. **Visualize Decision Tree**: The model exports a `.dot` file for tree visualization

### Example Usage
```python
import pandas as pd
import joblib

# Load the trained model
model = joblib.load('models/music-recommender.joblib')

# Create new user data
new_users = pd.DataFrame([
    [25, 1],  # 25-year-old male
    [30, 0]   # 30-year-old female
], columns=['age', 'gender'])

# Predict genres
predictions = model.predict(new_users)
print(f"Predicted genres: {predictions}")
```
