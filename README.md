# Fair document classification
## Task Overview
The task is straightforward: assign the correct category to a text. This is a multi-class classification task with **28 classes**.

## Classification Paradigm
The most adopted paradigm involves training a network `f`, mapping from the input space `X` to a `d`-dimensional real vector space. For a document `x` in `X`, it extracts a feature vector `z` in `R^d` that synthesizes the relevant characteristics of the document. The diagnostic phase then involves predicting the label of the document `x` based on the extracted features `z`. In this data challenge, the feature space dimensionality `d` is `768`.

## Data Provision
We directly provide you the embedding of each text, learned with **BERT**.

## Competition Goal
The goal of this competition is to design a solution that is both **accurate** in predicting the label and **fair** with respect to some sensitive attribute (e.g., gender). Fairness in this context means that the model should not be biased toward a certain minority group present in the data.

## Evaluation
We explain this paradigm further in the evaluation part.

# Evaluation
First of all, the accuracy of the solutions are evaluated according to the Macro F1 metric, The Macro F1 score is simply the arithmetic average of the F1 score for each class.

We will also analyse proposed solutions according to their fairness with respect to the provided sensitive attribute (S
). In other words, we want you to design a solution that is not biased towards one group in particular. To be specific, we will use (1-equal opportunity gap) between protected groups. A fair model is a model where this criteria is close to 1.

Overall, your model should satisfy both criteria so the evaluation metric is the average between the macro F1 and the fairness criteria.
