# Music Genre Classification and Song Similarity Search

## Overview

This project involves the classification of music genres using audio data and the calculation of similarity between songs based on their audio features. The steps include:
1. Feature extraction from audio files.
2. Scaling the features.
3. Computing the cosine similarity between songs.
4. Finding the most similar songs to a given song using the computed similarity matrix.
5. Playing the selected song's audio.


## Dependencies
Before the working project, update general_path part accoring to your workplace.( Second cell in MusicGenreClassification.ipynb)  

The following libraries are required for this project:

- `pandas`: For data manipulation and creating DataFrame objects.
- `scikit-learn`: For scaling the features and calculating cosine similarity.
- `IPython`: For audio playback in Jupyter notebooks.
- `librosa`: For audio feature extraction (e.g., MFCC, Chroma).
- `numpy`: For numerical operations.
```bash
pip install pandas scikit-learn librosa numpy IPython






