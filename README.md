# Leela-Manohar-
Spam Email Detection Build a machine learning classifier that distinguishes spam from legitimate email using text  features and evaluates false positives and false negatives.
 📧 Spam Email Detection

A machine learning project that classifies text messages/emails as **Spam** or **Legitimate (Ham)** using text features.

## Problem Statement

Build a machine learning classifier that distinguishes spam from legitimate email using text features and evaluates false positives and false negatives.

## Features

- Text preprocessing
- TF-IDF feature extraction
- Multinomial Naive Bayes classifier
- Accuracy, precision, recall and F1-score
- Confusion matrix
- False Positive (FP) analysis
- False Negative (FN) analysis
- Streamlit web application for testing custom messages
- Automatic support for common spam CSV formats

## Project Structure

```text
spam-email-detection/
│
├── data/
│   └── spam.csv
│
├── model/
│   └── spam_classifier.joblib
│
├── train.py
├── app.py
├── requirements.txt
├── confusion_matrix.png
├── .gitignore
└── README.md
```

## Dataset

This project works with a CSV containing two fields representing:

- `label`: `spam` or `ham`
- `message`: email/message text

It also supports the common SMS Spam Collection format with columns:

```text
v1, v2
```

For example:

```csv
label,message
ham,"Hi, please attend the meeting at 10 AM."
spam,"Congratulations! You won a free prize. Click now!"
```

Place the dataset at:

```text
data/spam.csv
```

> Do not upload private or confidential emails to the repository.

## Installation

Create a virtual environment if desired:

```bash
python -m venv venv
```

Windows:

```bash
venv\Scripts\activate
```

Install dependencies:

```bash
pip install -r requirements.txt
```

## Train the Model

Run:

```bash
python train.py
```

The program will:

1. Load the dataset.
2. Split it into training and testing data.
3. Convert text into TF-IDF features.
4. Train a Multinomial Naive Bayes model.
5. Generate predictions.
6. Calculate performance metrics.
7. Calculate FP and FN.
8. Save the trained model.
9. Save a confusion matrix image.

Generated files:

```text
model/spam_classifier.joblib
confusion_matrix.png
```

## Run the Web Application

After training:

```bash
streamlit run app.py
```

A browser window will open. Paste an email/message and click **Check Email**.

## Evaluation

The project reports:

### Accuracy

Percentage of all correctly classified messages.

### Precision

Of the messages predicted as spam, how many were actually spam.

### Recall

Of all actual spam messages, how many were detected.

### F1 Score

Harmonic mean of precision and recall.

### False Positive

A legitimate email incorrectly classified as spam.

This is important because a false positive can cause an important legitimate email to be missed.

### False Negative

A spam email incorrectly classified as legitimate.

This is important because spam can reach the user's inbox.

## Confusion Matrix

The model produces:

```text
                    Predicted
                 Legitimate  Spam
Actual Legit.       TN       FP
Actual Spam         FN       TP
```

Where:

- TN = True Negative
- FP = False Positive
- FN = False Negative
- TP = True Positive

## Machine Learning Pipeline

```text
Email Text
    ↓
Text Cleaning / Normalization
    ↓
TF-IDF Vectorization
    ↓
Multinomial Naive Bayes
    ↓
Spam / Legitimate
    ↓
Performance Evaluation
    ↓
FP and FN Analysis
```

## Technologies

- Python
- Pandas
- Scikit-learn
- Matplotlib
- Joblib
- Streamlit

## GitHub Commands

Create a repository on GitHub, then run:

```bash
git init
git add .
git commit -m "Initial spam email detection project"
git branch -M main
git remote add origin YOUR_GITHUB_REPOSITORY_URL
git push -u origin main
```

## Important

Do not commit:

- private emails
- passwords
- API keys
- personal information
- large raw datasets if their license does not permit redistribution
- the `venv/` folder

## License

This project is intended for educational and academic use.
