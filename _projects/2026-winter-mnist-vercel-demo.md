---
title: MNIST Vercel Demo
semester: 2026 Winter
team:
  - Weijie Sun
tags:
  - Machine learning
  - Computer vision
  - Vercel
  - Next.js
repo_url: https://github.com/jeremykid/intd-491-Vercel-Demo
demo_url: https://intd-491-vercel-demo.vercel.app/
poster_image: /assets/images/2026-winter/projects/mnist-vercel-demo.svg
# group_image: /assets/images/2026-winter/projects/makerspace-intake-assistant-group.svg
short_abstract: A classroom-ready MNIST demo that combines dataset summaries, a browser drawing canvas, and a Vercel-hosted Python inference API backed by a small CNN exported to NumPy weights.
---
## Problem

Many machine-learning demos either hide the deployment path behind notebooks or oversimplify the end-to-end workflow. This project was built to show a compact but complete example that students can explain in class, from dataset inspection to browser prediction.

## Data

The app uses the MNIST handwritten digit dataset, plus generated metadata files that summarize class counts and provide lightweight preview samples for the frontend.

## Method

The frontend is built with Next.js and TypeScript. It presents a one-page walkthrough with dataset context, a Plotly class-distribution chart, and a drawing canvas that preprocesses user strokes into an MNIST-like 28x28 input. Prediction requests are sent to a Vercel-compatible Python API that loads exported CNN weights with NumPy only.

## Results

The result is a lightweight deployment demo that keeps both the user experience and the inference path easy to explain. Students can inspect the dataset, draw digits in the browser, and see probability outputs without needing a heavyweight notebook or training runtime in production.

## How to run

1. Clone `https://github.com/jeremykid/intd-491-Vercel-Demo`.
2. Install Node dependencies with `npm install`.
3. Install Python runtime dependencies with `pip3 install -r requirements.txt`.
4. Run `npm run dev` to start the Next.js frontend and the Vercel Python function together.

## Links

- Repository: https://github.com/jeremykid/intd-491-Vercel-Demo
- Demo: https://intd-491-vercel-demo.vercel.app/
