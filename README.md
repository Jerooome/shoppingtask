# README: Online Shopping Purchase Prediction

## Project Overview
This project uses machine learning to predict whether a user browsing an online shopping website will make a purchase. Using data from about 12,000 user sessions, the program applies a k-nearest neighbor (k-NN) classifier to make these predictions. The goal is to optimize sensitivity (true positive rate) and specificity (true negative rate) for meaningful results.

## Files Included
1. **shopping.py**: The main Python script containing:
   - Functions to load data, train a model, and evaluate its performance.
   - The main execution logic for predicting user purchasing intent.

2. **shopping.csv**: The dataset with 12,000 rows of user session data, each row representing:
   - Details about page visits, durations, bounce rates, exit rates, and user demographics.
   - A label (`Revenue`) indicating if the user made a purchase (`TRUE` or `FALSE`).

## Requirements
### Dependencies
- Python 3.7+
- Required libraries:
  - `scikit-learn`

Install dependencies using:
```bash
pip install scikit-learn
```

### Dataset
Ensure the `shopping.csv` file is present in the same directory as `shopping.py` before running the script.

## Usage
### Running the Program
To execute the program:
```bash
python shopping.py shopping.csv
```

### Output
The program will:
1. Load the data from `shopping.csv`.
2. Split the dataset into training and testing sets.
3. Train a k-nearest neighbor (k-NN) classifier with k=1.
4. Predict purchase intent on the testing set.
5. Print the following metrics:
   - Number of correct and incorrect predictions.
   - Sensitivity (True Positive Rate).
   - Specificity (True Negative Rate).

### Example Output
```text
Correct: 8400
Incorrect: 3600
True Positive Rate: 75.00%
True Negative Rate: 85.00%
```

## Functionality
### `load_data(filename)`
- **Input:** CSV file path.
- **Output:** A tuple `(evidence, labels)` where:
  - `evidence`: List of features for each session.
  - `labels`: List of labels (1 for purchase, 0 otherwise).

### `train_model(evidence, labels)`
- **Input:**
  - `evidence`: List of features.
  - `labels`: List of labels.
- **Output:** Trained k-NN model.

### `evaluate(labels, predictions)`
- **Input:**
  - `labels`: Actual labels from the test set.
  - `predictions`: Model's predicted labels.
- **Output:** Tuple `(sensitivity, specificity)`.

## Testing and Validation
### Expected Behavior
- Sensitivity and specificity are balanced to ensure reasonable predictions.
- Model performance should exceed random guessing.

### Additional Testing
To evaluate correctness:
- Ensure that the dataset is clean and formatted correctly.
- Validate the program using subsets of data.

## Future Enhancements
1. Allow the user to specify the value of `k` for the k-NN model.
2. Provide additional metrics like F1-score or precision.
3. Enable support for additional datasets with dynamic preprocessing steps.

## Author
This project was developed as part of a machine learning exercise to explore nearest-neighbor classification in real-world scenarios.

