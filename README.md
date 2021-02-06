# FairCeptron notebooks

In this repo, the Jupyter notebooks are stored, that accompany the [FairCeptron web app](https://github.com/cssh-rwth/fairceptron) as part of an implementation of the FairCeptron framework. The framework consists of 3 parts, with _fairness scenario generation_ and _fairness perception analysis_ implemented in Python and stored in this repo, whereas _fairness scenario elicitation_ is implemented as a Nuxt.js universal web app.

## Fairness scenario generation

> Algorithmic ranking and
classification scenarios are generated that consist of personas
of two or more groups that can optionally have a second,
numeric attribute associated to them. The
scenarios are generated as all possible selections from / permutations
of n personas, in which personas within a group
are selected / ranked by qualification. The scenarios are clustered
along multiple measures of algorithmic fairness, ensuring
that each participants later receives a variety of scenarios,
while maximizing the total number of scenarios that are
tested.

After generating and exporting the scenarios in JSON format, they are used to populate the MongoDB database from which the web app (backend) randomly selects scenarios for each new survey participant.

## Fairness perception analysis

These notebooks represent examples of how data obtained from a FairCeptron survey could be analyzed. Beforehand, participants' responses must be exported from MongoDB in CSV (or JSON) format. This repo includes demo data and notebooks for the following analyses:

- **participant statistics**: general statistics on demographics of users who completed the survey
- **significance**: significant spearman correlations between user ratings and all features for selection and ranking questions
- **randomForest**: random forests with different accuracy (binning of user ratings), trained on selection and ranking data. Also includes feature importance analysis (RF feature importance and permutation importance).
- **heatmaps**: user ratings binned onto a 2d plane (accuracy - gender parity), compared for different groups and individuals
- **gender comparisons [ranking, selection]**: in-detail comparisons of fairness ratings by persona gender and various user attributes
- **linear regression**: Ridge regression models (with polynomial features) trained on selection and ranking tasks to estimate fairness perception.
- **individual preferences**: comparisons of fairness definition preferences as stated directly by users and fairness definition preferences infered from user ratings. Also includes random forest models for predicting fairness definition preferences from demographics.
- **theoretical models**: theoretical models from the landscape of possible fairness perceptions, built on synthetical data as well as on the actual questions that users answers. Includes comparisons to the actual results.
- **group sizes**: in-depth analysis of user ratings not only distinguishing by majority group gender, but particular group sizes
- **rating statistics**: Overall distributions of ratings, times to answer and answering uncertainty

![Heatmap comparing participants' ratings of ranking scenarios](heatmap%20ranking.png)
