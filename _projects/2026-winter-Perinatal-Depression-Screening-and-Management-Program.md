---
title: Perinatal Depression Screening Vercel Demo
semester: 2026 Winter
team:
  - Hooriya Kazmi
  - Sharon Wong
  - Rafiul Alam Khan
  - Linh Le
  - Katrina Alejo
tags:
  - Machine learning
  - Vercel
  - HTML
  - CSS
  - JavaScript
  - Python
repo_url: https://github.com/codebylinh/INTD-491_Perinatal-Depression-Screening-and-Management-Program
demo_url: https://intd-491-perinatal-depression-scree-phi.vercel.app/
poster_image: /assets/images/projects/2026-winter/Perinatal_poster.png
group_image: /assets/images/projects/2026-winter/Perinatal_teams.jpg
short_abstract: A cloud-deployed web application that predicts postpartum depression risk using logistic regression (for flagging high-risk individuals) and ElasticNet (for estimating the severity of postpartum symptoms on a continuous scale) models trained on first-trimester, second-trimester and third-trimester clinical data.
---
## Problem

Postpartum depression (PPD) affects 10–20% of new mothers globally, yet many cases go undetected until symptoms become severe. This gap contributes to worse maternal and infant outcomes and increases the overall healthcare burden, while most clinical settings still lack a scalable early-warning system for timely detection. This project was built to predict which individuals are likely to develop PPD before it occurs, using routinely collected screening data.

## Data

The app uses longitudinal data collected during early pregnancy, the second and third trimesters, and the postpartum period to predict PPD. Each participant is described by 61 variables spanning demographic, health, psychosocial, and mental health assessment data. The result model is validated by an external dataset of women from Bangladesh with similar features (including single postpartum EPDS, PHQ-9, and PHQ-2 measures).

## Method

The frontend is built with HTML, CSS, and JavaScript. It presents a trajectory-based postpartum depression risk assessment framework, including dataset context, interactive Plotly visualizations for exploratory data analysis (EDA) and model performance comparison, analysis insights, and a structured input form covering demographic, clinical, and longitudinal screening variables across pregnancy. User inputs are sent to a Vercel-compatible Python API, where a model trained on longitudinal data applies both classification and regression pipelines to estimate PPD risk and return results for real-time display in the browser.

## Results

The result is a lightweight deployment demo that allow users to explore dataset context and analysis insights, input longitudinal screening data across pregnancy, and receive real-time postpartum depression risk predictions—without requiring a heavy clinical system or offline analysis workflow.

## How to run

1. Clone `https://github.com/codebylinh/INTD-491_Perinatal-Depression-Screening-and-Management-Program`.
2. Install Node dependencies with `npm install`.
3. Install Python runtime dependencies with `pip3 install -r requirements.txt`.
4. Run `npx serve public` to start the HTML frontend and the Vercel Python function together.


## Links

- Repository: https://github.com/codebylinh/INTD-491_Perinatal-Depression-Screening-and-Management-Program
- Demo: https://intd-491-perinatal-depression-scree-phi.vercel.app/

