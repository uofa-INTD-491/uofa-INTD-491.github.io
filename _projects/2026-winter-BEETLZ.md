---
title: BEETLZ Vercel Demo
semester: 2026 Winter
team:
- Animesh Mittal  
- Anurag Jain  
- Danielle Hopfe  
- Erza Tamon  
- Gareth Kumar  
- Sanskar Singh

tags:
- Machine learning
- Computer vision
- Vercel
- Next.js

repo_url: https://github.com/animeshm19/beetlz-ui
demo_url: https://beetlz-ui.vercel.app/
# poster_image: src/assets/Poster.svg
group_image: /assets/images/projects/2026-winter/BEETLZ_teams.jpg
short_abstract: A classroom-ready Tree Damage Detection demo that combines dataset summaries, a
browser drawing canvas, and a Vercel-hosted Python inference API backed by a small
CNN exported to NumPy weights.
---

## Abstract

A forest pest detection demo that combines dataset analysis, a React frontend, and a Cloud Run-hosted RetinaNet inference API for prediction on input images.

## Problem

Bark beetle outbreaks are devastating forests, and the industry still relies on slow, expensive ground surveys to find damaged trees. We wanted to see if drone imagery and deep learning could replace that like flagging damage automatically, before the infestation spreads.

We also asked a harder question: once a model works on one tree species, can it transfer to another without starting over? If yes, forestry managers could cover more species without collecting thousands of new labeled images each time.

The main obstacle is class imbalance. In our dataset, only 1.8% of annotated trees are damaged i.e. a 50:1 ratio of healthy to sick. Most standard object detectors collapse under that skew, so the loss function and architecture had to be chosen carefully.

## Data

We worked with UAV aerial imagery of two tree species: Larch and Spruce. Spruce data came from three Swedish sites namely Lidhem, Viken, and Backsjon giving us geographic variety within the species. Each tree is annotated as healthy, lightly damaged (LD), or heavily damaged (HD).

To make the most of the limited damaged-tree samples, we applied four augmentations: horizontal/vertical flip, rotation at ±90° and ±180° (safe for top-down aerial shots), mild brightness/contrast jitter, and an HD-centric crop that zooms into a damage bounding box and resizes it as a new training sample.

We also computed pixel-intensity histograms for each species and site, then used a chi-square test to measure how visually different Larch and Spruce actually look. Those chi-square values end up explaining a lot about whether transfer learning will work.

## Method

The task is object detection with bounding boxes around damaged trees. We compared two detectors:

- **YOLO** — anchor-free, fast, popular baseline
- **ResNet + RetinaNet** — anchor-based, uses focal loss to handle class imbalance

RetinaNet won clearly. Focal loss lets us tune gamma and alpha directly for the 50:1 imbalance, whereas YOLO handles this automatically and less effectively. RetinaNet's anchor-based design also detects more damage per grid cell, which matters when damaged trees cluster together.

For the transfer learning question, we used a two-phase training setup:

- **Phase 1**: train on Larch for 50 epochs, early stopping at 15
- **Phase 2**: take that Larch-trained model and fine-tune on Spruce for 20 epochs, early stopping at 10

The deployed model runs on Google Cloud Run as a FastAPI service. The frontend sends an image, the backend returns it with bounding boxes drawn on.

## Results

**Baselines (trained and tested on Spruce only):**

| Model                  | Test F2 |
| :--------------------- | :------ |
| YOLO                   | 0.75    |
| ResNet + RetinaNet     | 0.86    |

**Transfer learning (Larch → Spruce):**

| Phase                  | Larch F2 | Spruce F2 |
| :--------------------- | :------- | :-------- |
| Phase 1 (Larch train)  | 0.6632   | 0.0820    |
| Phase 2 (Spruce tune)  | —        | 0.8100    |

Two takeaways:

1. **Zero-shot transfer does not work.** A Larch-trained model scored 0.08 on Spruce - essentially blind. The chi-square tests explain why: the pixel distributions of damage look meaningfully different across species.
2. **Fine-tuning closes the gap.** After a short Spruce fine-tune, the model hit 0.81 F2 — about 94% of the Spruce-only baseline of 0.86. So transfer works, but it still needs some target-species data.

The practical upshot for forestry: you don't have to collect thousands of new labeled images every time you move to a new species. Pretrain on whatever species you have the most data for, then fine-tune with a modest Spruce set.

## How to run

1. Clone `https://github.com/animeshm19/beetlz-ui`.
2. Install Node dependencies with `npm install`.
3. Create a `.env` file at the repo root with `VITE_API_URL=https://my-model-service-aj5ulugt3a-uc.a.run.app` (the Cloud Run backend). See `env.example` for reference.
4. Run `npm run dev` — the Vite + React frontend starts at `http://localhost:5173`.

The inference backend runs on Google Cloud Run, so no Python setup is needed locally. If you want to run the backend yourself, see `beetlz-api/` for the FastAPI service and Dockerfile.

## Links

- Repository: https://github.com/animeshm19/beetlz-ui
- Demo: https://beetlz-ui.vercel.app/
