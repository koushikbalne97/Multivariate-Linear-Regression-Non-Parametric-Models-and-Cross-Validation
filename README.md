# Practical Lab 2: Diabetes Progression Regression

This project uses the diabetes dataset bundled with scikit-learn (442
observations, 10 baseline features) to explore prediction of a numerical
measure of disease progression one year after baseline. The task predicts
progression for people who already had diabetes; it does not predict whether a
person has diabetes.

The notebook, [Practical_Lab_2.ipynb](./Practical_Lab_2.ipynb), walks through:

- Data quality checks and exploratory analysis.
- BMI-only polynomial regression (degrees 0 through 5).
- Multivariate polynomial regression (degrees 2 and 3), decision trees (depths
  3 and 6), and scaled k-nearest-neighbours regression (5 and 15 neighbours).
- Logistic regression on an explicitly exploratory above-training-median
  category; this is kept separate from continuous-score regression.
- Validation-based model selection, five-fold cross-validation on training
  data, and final evaluation on a held-out test set.

## Repository

GitHub repository: [Multivariate Linear Regression, Non-Parametric Models and
Cross-Validation](https://github.com/koushikbalne97/Multivariate-Linear-Regression-Non-Parametric-Models-and-Cross-Validation).

The notebook selects the quadratic model using validation MAE. Its recorded
test MAE is 45.99 progression-score units; the BMI-only quadratic's test MAE is
54.99. These are results from this particular fixed split, not performance
guarantees.

**This is an educational exercise, not a diagnostic or clinical screening
tool.** The target is a progression score, not a diagnosis or a probability of
developing diabetes.

## Setup

Use Python 3.10 or newer. In PowerShell, from the project directory, create
and activate a virtual environment and install the packages listed in
`requirements.txt`:

```powershell
py -m venv .venv
.\.venv\Scripts\Activate.ps1
python -m pip install --upgrade pip
python -m pip install -r requirements.txt
```

If PowerShell blocks activation, install the dependencies and launch Jupyter
through the environment's Python executable:

```powershell
.\.venv\Scripts\python.exe -m pip install -r requirements.txt
.\.venv\Scripts\python.exe -m notebook
```

## Run

With the virtual environment activated, start Jupyter Notebook:

```powershell
python -m notebook
```

Open `Practical_Lab_2.ipynb` and run the cells in order. The notebook uses a
fixed random seed for its training, validation, and test split, so the split
and reported results are reproducible with compatible package versions.
