# kidmedia-guardian
ADK-powered agent to flag high-arousal kids’ videos

KidMedia Guardian (Prototype)
This project is an early prototype of a simple tool that analyzes short clips from children’s YouTube channels and estimates whether the visual content appears high-arousal. The goal is to help parents identify fast, overstimulating media and explore calmer alternatives.
The current version focuses on building an end-to-end pipeline that works inside a Kaggle Notebook. The system extracts frames from a video, processes them with a pretrained CNN, models temporal patterns with an LSTM, and produces a basic prediction. This version does not include full evaluation metrics or audio analysis.

What the System Does?
  Loads a short video clip that you upload to the Kaggle working directory.
  Extracts frames using OpenCV.
  Uses a pretrained ResNet50 model to turn each frame into a feature vector.
  Feeds the sequence of frame features into an LSTM.
  Outputs a simple prediction indicating whether the clip seems visually intense.
  Saves results into results/analysis.json.

This notebook represents the core pipeline required for the course deliverables.

What Has Been Implemented?

Feature extraction

  OpenCV for frame sampling
  
  ResNet50 (pretrained on ImageNet) for visual feature extraction
  
  Basic normalization and resizing functions
  
Sequence modeling

  A lightweight LSTM model built with Keras
  
  Trained on sample clips manually added to the notebook

  Designed to classify clips into “high arousal” or “not high arousal”
  
Pipeline and orchestration

  A simple structured workflow placed inside src/tools/feature_extractor.py and src/tools/analyzer.py
  
  Final predictions saved in a JSON file for easy reference
  
Demonstration clips

  Short clips from children’s YouTube channels such as Cocomelon, Bluey, Ms Rachel, Lalafun, and a few high-movement or high-brightness examples
