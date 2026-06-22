# Football Event Detection

## Overview

This project builds a machine learning model to detect football events such as goals, substitutions, and cards using the SoccerNet dataset. It uses deep learning models to process video embeddings and learn event patterns.

Future work includes adding player tracking data for tactical analysis.

---

## Dataset

- SoccerNet dataset  
- Event annotations  
- Precomputed video embeddings  

---

## Method

- Preprocess embeddings and labels  
- Train deep learning models (TCN / Transformers)  
- Perform event classification  
- Evaluate using Precision, Recall, F1-score, and mAP  

---

## Project Structure
data/
models/
preprocessing/
training/
evaluation/


---

---

## Installation & Setup

git clone https://github.com/ShrugalVinod/matchmind-ai
cd football-ai-project

pip install -r requirements.txt

downloader = SoccerNetDownloader(LocalDirectory="data/")
downloader.password = "your_password"
downloader.downloadDataTask(task="spotting")

python training/train.py

python evaluation/evaluate.py
