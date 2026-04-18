---
title: Interpretable and Fair Recidivism Prediction
semester: 2026 Winter
team:
   - Khanh Bui
   - Fehintola Disu
   - Juan Joseph
   - Sevryn Robinson
   - Koyinsola Titiloye
   - Nelson Wong
tags:
  - Machine learning
  - Fairness
  - Interpretability
  - Criminal justice
  - Vercel
  - Next.js
repo_url: https://github.com/INTD491/COMPASW26
demo_repo_url: https://github.com/khanheric2003/intd491_cloud_deploy
demo_url: https://intd491-cloud-deploy.vercel.app/
poster_image: /assets/images/posters/2026-winter/posters/COMPAS_poster.png
group_image: /assets/images/projects/2026-winter/projects/COMPAS_teams.jpg
short_abstract: A cloud-deployed dashboard that analyzes recidivism prediction performance across jurisdictions, highlighting fairness trade-offs, interpretability with SHAP, and model generalization.
---
## Problem

Recidivism risk models can introduce or amplify bias when deployed in high-stakes settings. This project examines how predictive performance, fairness, and interpretability interact, and provides a transparent cloud dashboard for evaluating those trade-offs.

## Data

The dashboard compares two jurisdictions:

- Florida COMPAS dataset: 7,214 records
- Georgia NIJ dataset: 25,835 records
- Combined analysis: 33,049 total records

The analysis focuses on recidivism outcomes, demographic patterns, and cross-jurisdiction generalization.

## Method

We trained and compared multiple models, including COMPAS baseline scoring, Logistic Regression, Random Forest, and Decision Tree approaches. The system emphasizes:

- Accuracy and AUC benchmarking
- Fairness metrics, including disparate impact
- SHAP-based feature contribution explanations
- Cross-jurisdiction model transfer and robustness checks

The app is deployed on Vercel with a Next.js/React frontend and Python-based analytics services.

## Results

Among the baseline models, Logistic Regression and Random Forest achieve the strongest overall performance. Logistic Regression obtains the highest AUC-ROC (0.7312) and F1 score (0.6572), while Random Forest achieves the highest accuracy (0.6874) and precision (0.6600). Both models outperform the COMPAS baseline across all reported metrics.


The end product is an instructional, production-style demo for responsible ML deployment in criminal justice contexts.

## How to run

1. Open the live deployment: https://intd491-cloud-deploy.vercel.app/
2. Explore the Home, Fairness, Generalization, Models, EDA, and Diagnostic pages.
3. Use the Prediction page to test model outputs and inspect SHAP explanations.

## Links

- Dashboard: https://intd491-cloud-deploy.vercel.app/
- Prediction Tool: https://intd491-cloud-deploy.vercel.app/prediction
- Fairness Analysis: https://intd491-cloud-deploy.vercel.app/fairness
- Generalization: https://intd491-cloud-deploy.vercel.app/generalization
- About: https://intd491-cloud-deploy.vercel.app/about
