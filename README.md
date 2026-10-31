# kaggle_titanic: independent implementation under Claude’s guidance

you gotta start with something..

My first Ml project: predicting which Titanic passangers survived[Kaggle competition](https://www.kaggle.com/competitions/titanic)
Goal: learn basics of pandas and scikit-learn. Don't chase the leaderboard. Implement 3 different models.

## What I did:
—EDA: Have found patternd in value-survival relations using columns one by one: "Sex", "Pclass", "Age"..) and multiple, created visualisation with diagrams.
—Feature engineering: filled in the missed data using median("Age"), most common values("Embarked"). Made "Sex" column using digits instead of male/female, using available data created columns: HasCabin, FamilySize, IsAlone. One-hot for "Title", "Embarked". Dropped columns before model learning: "Name", "Ticket", "Cabin".
—Models: Logistic Regression, Decision Tree, Random forest.

## Results:
| Model | Validation accuracy | Kaggle score |
|---|---|---|
| Baseline (all women survive) | 0.782 | — |
| Logistic Regression | 0.827 | 0.77511 |
| Decision Tree (depth 4) | 0.821 | 0.77990 |
| Random Forest | 0.832 | 0.77751 |

## Key finds: 
- Sex is the most impactful factor in survival rates.
- Pclass difference between 1st and 3rd is almost 3 times. Worst rates for men 3rd class, best for women 1st class.
- Age median by title is more accurate than by global median.
- PassengerId is pure noise, yet the random forest used it in splits.
- Family Size is not linear factor. Logistic Regression cannot take this into account.
- Is Alone don't add new data. Family Size is enough.

## What I learned:

- Basics of pandas, scikit-learn, Seaborn.
- How to analyze and build patterns using data. 
- How to fill in missed data.
- How to train and evaluate models.
- What information model need in order to predict most efficiently

## Possible impovements.

- Group passengers by ticket number in order to distinguish whole families.
- Use cross-validation instead of a single train/validation split.
- Use Gradient Busting
- Tune hyperparametes: max_depth and n_estimators were chosen by hand. A grid search with cross-validation would test the combination and pick the best option.
