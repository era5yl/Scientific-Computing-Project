# Scientific-Computing-Project
# 🎵 Mood-Based Music Recommendation System  
### Using PCA + Gaussian Mixture Models (GMM)

This project builds a **2D emotional space** for Spotify songs using  
**Principal Component Analysis (PCA)** and **Gaussian Mixture Models (GMM)**.  
The model discovers **8 distinct mood clusters**, such as:

- Exuberant / Happy–Energetic  
- Warm / Romantic / Positive  
- Calm / Chill  
- Sad / Depressed / Melancholic  
- Anxious / Tense  
- Energetic / Intense  
- Content / Calm–Happy  
- Moody / Dark / Emotional  

Based on this space, the project implements a **mood-aware music Recommendation System** that can filter songs by:

- Mood position  
- Genre  
- Popularity  
- Random sampling (to avoid repetition)

---

##  Features

-  Creates a **2D mood embedding** using PCA  
-  Fits an **8-component GMM** for soft emotional clustering  
-  Allows searching songs by **name and artist**  
-  User can select target mood coordinates  
-  Recommender returns nearest songs in mood space  
-  Includes clustering evaluation and recommendation testing  
-  Visualizations for PCA, cluster regions, and testing metrics  

---

## Project Structure

Below is a detailed explanation of each component in the repository:

---

### `dataset.csv`
The main Spotify dataset used for the project.  
It contains track metadata and audio features such as:

- danceability  
- energy  
- valence  
- tempo  
- loudness  
- acousticness  
- speechiness  
- instrumentalness  
- liveness  
- popularity  
- genre  
- track and artist information  

---

### `mood_model.ipynb`
The main Jupyter Notebook where the entire pipeline is implemented:

1. Loading and cleaning dataset  
2. Standardizing audio features  
3. PCA dimensionality reduction  
4. Mood space alignment (happy–sad, energetic–calm)  
5. GMM clustering (8 moods)  
6. Visualization of clusters  
7. Recommendation system implementation  
8. Model testing and evaluation  

---

## `src/` — Source Code Modules

### `preprocessing.py`
Handles:

- loading the CSV dataset  
- selecting relevant audio features  
- normalizing data with `StandardScaler`  
- preparing matrices for PCA and GMM  

This module ensures consistent preprocessing across the project.

---

### `pca_model.py`
Implements:

- PCA fitting  
- extracting principal components  
- correlating PCs with valence and energy  
- aligning PC directions to emotional axes  
- mapping PCA scores into the 2D mood space  

The logic that turns high-dimensional audio data into a continuous emotional map lives here.

---

### `gmm_model.py`
Responsible for:

- fitting an 8-component Gaussian Mixture Model  
- computing soft probabilities (`responsibilities`)  
- extracting cluster centers  
- assigning each song to a mood cluster  
- model evaluation metrics (log-likelihood, AIC, BIC, silhouette)

This module forms the core mood clustering engine.

---

### `recommender.py`
Contains the **mood-aware music recommendation system**:

- Finds nearest songs to a user-selected mood point `(x, y)`  
- Allows filtering by genre  
- Allows filtering by popularity  
- Random sampling to avoid repetition  
- Utility functions such as finding a song’s mood location  
  (e.g., `show_song_in_mood_space_by_name_artist`)

---

### `evaluation.py`
Includes all testing logic:

- GMM cluster quality evaluation  
- Intra-cluster vs inter-cluster distance analysis  
- Recommender vs random baseline comparison  
- Plotting evaluation results  

This module ensures the numerical model behaves correctly.

---

### `utils.py`
General-purpose utilities such as:

- distance computation  
- helper plotting functions  
- common mathematical helpers  

---

## `figures/`
Stores exported images used in the README and report:

- `mood_space.png`  
- `gmm_clusters.png`  
- `intra_inter_distances.png`  
- `recommender_vs_random.png`  
- any other diagrams or plots

These are automatically generated when running the notebook.

---

## `README.md`
Documentation providing:

- project overview  
- setup instructions  
- usage examples  
- visualizations  
- evaluation results  

---

## `requirements.txt`
List of Python packages required for full functionality:
- numpy
- pandas
- matplotlib
- scikit-learn


