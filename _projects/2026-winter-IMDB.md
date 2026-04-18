---
title: IMDb Team - Analyzing Posters' Relationship to Opening Weekend Revenue
semester: Winter, 2026
team:
- Sehej Brar
- Amarachi Ukoha
- Alec Zaiane
- Carlin Boyles
- Tanishq Sarkar

tags:
- Autoencoder
- Embeddings
- Vercel
- Django

repo_url: https://github.com/alec-zaiane/INTD491-IMDB
demo_url: https://intd491-vercel.vercel.app/
group_image: /assets/images/projects/2026-winter/IMDB_teams.jpg
short_abstract: A complete machine learning pipeline that combines movie metadata with its posters to generate predictions about a movie's opening weekend revenue. The model is hosted on Vercel with a Django backend that allows users to upload their own movie poster for a revenue prediciton.

---
## Problem
Movie datasets often contain structured information about the movie and its performance but fail to capture the visual information in a poster. This project investigates whether poster-level features like text, colour, body and face presence can be combined with the metadata to make more accurate predictions about a movie's opening weekend revenue.

## Data
The app uses the [IMDb dataset](https://www.kaggle.com/datasets/raedaddala/imdb-movies-from-1960-to-2023) and the [IMDb Movie Poster dataset](https://www.kaggle.com/datasets/rezaunderfit/48k-imdb-movies-with-posters). Both datasets were joined on their IMDb ID to produce a dataset with each movie mapped to its metadata and poster.

## Method
A Python data pipeline was used to remove incomplete rows, clean text fields to increase uniformity, and adjust financial figures for inflation. We also extracted poster-level features like dominant colours and HSV palettes using Pylette; face and body presence using YOLO models; and text statistics using OCR. Furthermore, an image encoding model was used to create learned poster representations. We used the resulting features for clustering and relationship analysis with features like genre, profit, and ROI.   

## Results
The result is a demo that is built using Next.js and is deployed on Vercel. The frontend communicates with a Django based backend API that serves model predictions and graphs. It allows users to view dataset statistics including basic EDA, correlations, and the poster embeddings map. Furthermore, users can upload their own poster onto the demo to view the expected opening weekend revenue of their film. Overall, the model demonstrates that the poster has an effect on predicting financial outcomes of movies, and the poster embedding map reveals distinct clusters associated with poster features and revenue. 


### How to run
1. Install `uv` as a [project manager](https://docs.astral.sh/uv/getting-started/installation/).
2. Clone `https://github.com/alec-zaiane/INTD491-IMDB`
3. Install dependencies with `uv sync`
4. Access deployment via `cd deployment`
5. Run `uv run python manage.py runserver` to start the backend server
6. Download [frontend server zip](https://drive.google.com/file/d/16xYHHmHm7jpV6eBlmeHuKawjAsM0ydCF/view?usp=drive_link) to a separate directory and unzip
7. in that directory, create a `.env` with `NEXT_PUBLIC_API_BASE_URL="http://localhost:8000"`
8. `bun install` and `bun run dev` to run the frontend server

### Links
- Repository: https://github.com/alec-zaiane/INTD491-IMDB
- Demo: https://intd491-vercel.vercel.app/