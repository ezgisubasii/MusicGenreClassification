Music Genre Classification and Song Similarity Search Overview This
project involves the classification of music genres using audio data and
the calculation of similarity between songs based on their audio
features. The steps include: 1. Feature extraction from audio files. 2.
Scaling the features. 3. Computing the cosine similarity between songs.
4. Finding the most similar songs to a given song using the computed
similarity matrix. 5. Playing the selected song\'s audio. Project
Structure . ├── data/ │ └── genres_original/ \# Folder containing the
original audio files categorized by genre │ ├── blues/ │ ├── classical/
│ ├── country/ │ └── \... ├── notebooks/ │ └──
music_genre_classification.ipynb \# Jupyter notebook for genre
classification ├── src/ │ ├── feature_extraction.py \# Code for
extracting features from audio files │ ├── similarity_search.py \# Code
for calculating cosine similarity and finding similar songs │ └──
utils.py \# Helper functions ├── requirements.txt \# Python dependencies
└── README.md \# This file Dependencies The following libraries are
required for this project: \* pandas: For data manipulation and creating
DataFrame objects. \* scikit-learn: For scaling the features and
calculating cosine similarity. \* IPython: For audio playback in Jupyter
notebooks. \* librosa: For audio feature extraction (e.g., MFCC,
Chroma). \* numpy: For numerical operations. You can install the
required dependencies by running: pip install -r requirements.txt
Alternatively, install each library individually: pip install pandas
scikit-learn librosa numpy IPython Steps and Code Explanation 1. Feature
Extraction In the feature extraction part, audio files are loaded, and
relevant features are extracted (such as Mel-Frequency Cepstral
Coefficients (MFCC), Chromagram, Spectral Contrast, etc.). This is done
using the librosa library. The extracted features are then scaled for
use in similarity calculations. 2. Cosine Similarity Calculation The
cosine_similarity function from scikit-learn is used to calculate the
similarity between each pair of songs based on their extracted features.
The similarity matrix is then stored in a pandas DataFrame for easy
access. similarity = cosine_similarity(data_scaled) sim_df =
pd.DataFrame(similarity, index=labels.index, columns=labels.index) 3.
Finding Most Similar Songs The function get_similar_songs allows the
user to find the top N most similar songs to a given song based on
cosine similarity. It takes the song name and the number of top similar
songs (top_n) as input. def get_similar_songs(song_name, top_n=10):
similarity_series = sim_df\[song_name\].sort_values(ascending=False)
similarity_series = similarity_series.drop(song_name) \# Remove the song
itself print(f\"\\n\*\*\*\*\*\*\*\\nTop {top_n} similar songs to
\'{song_name}\':\") print(similarity_series.head(top_n)) The function
sorts the songs by their similarity, removes the original song (which
has a similarity of 1 with itself), and displays the top N similar
songs. 4. Audio Playback Once the similar songs are identified, the
IPython.display.Audio function is used to play the audio of the selected
song directly within a Jupyter notebook.
ipd.Audio(f\'{general_path}/genres_original/blues/blues.00069.wav\')
Make sure to update general_path to point to the correct directory
containing the audio files. Example Here\'s how you can use the function
to find similar songs: get_similar_songs(\'blues.00069.wav\', top_n=10)
This will display the top 10 similar songs to \'blues.00069.wav\'. Audio
Playback After identifying the similar songs, you can play the original
audio file:
ipd.Audio(f\'{general_path}/genres_original/blues/blues.00069.wav\')
This will allow you to listen to the song within the notebook.
Conclusion This project demonstrates how to classify music genres using
audio features and compute the similarity between songs. The system
allows the user to find similar songs and play them using a simple,
intuitive interface. License This project is licensed under the MIT
License.

This README file should help guide users in understanding and running
the project. Make sure to replace placeholders like general_path with
the actual paths used in your project.
