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

## 📌 Features

- 🎧 Creates a **2D mood embedding** using PCA  
- 🎛 Fits an **8-component GMM** for soft emotional clustering  
- 🔍 Allows searching songs by **name and artist**  
- 🎚 User can select target mood coordinates  
- 🎶 Recommender returns nearest songs in mood space  
- 📊 Includes clustering evaluation and recommendation testing  
- 📈 Visualizations for PCA, cluster regions, and testing metrics  

---

## 📂 Project Structure

