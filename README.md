# Income classification on the Adult dataset

> Course assignment from 2023, kept as it was written. The notes under "Reading the result" were added in November 2026.

Predicts whether a person earns more than $50K a year from census attributes (32,561 people,
24% above $50K) with logistic regression.

## Result

Test set of 9,769 people (30%):

| Measure | Value |
|---|---|
| Accuracy | 0.82 |
| Precision for ">50K" | 0.71 |
| Recall for ">50K" | 0.47 |
| F1 for ">50K" | 0.56 |

## Reading the result

- Predicting "<=50K" for everyone scores 0.758 on this test set, so the model adds 6 points of
  accuracy and finds fewer than half of the high earners.
- Categorical columns were label-encoded, which gives a linear model an arbitrary order for
  occupation or country. One-hot encoding, or a tree model, is the usual fix and reaches about
  0.85-0.87 on this dataset.
- The dataset includes sex and race. The notebook does not look at how errors differ by group.

## Newer work on the same topic

- [credit-risk-scorecard](https://github.com/faiqrasulov/credit-risk-scorecard): includes a fairness audit by age and sex with confidence intervals.

## Files

| File | Content |
|---|---|
| `Income Classification.ipynb` | Analysis |
| `Income Classification.html` | Rendered copy |
| `income_evaluation.csv` | The dataset |
| `About.txt` | Original brief and column descriptions |
