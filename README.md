# Spotify Song Ranking Using Multi-Criteria Decision Making (MCDM)

[![Python](https://img.shields.io/badge/Python-3.8%2B-blue)](https://www.python.org/)
[![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-orange)](https://jupyter.org/)

This project applies Multi-Criteria Decision Making (MCDM) techniques to rank the **200 oldest tracks** from Spotify's 2023 dataset. It compares **objective (Entropy)** and **subjective (AHP)** weighting methods across five ranking algorithms to identify optimal combinations for music recommendation systems.

## 📌 Key Features
- **Weighting Methods**:  
  - **Entropy Method**: Data-driven weights based on criterion variability.  
  - **AHP**: Expert-judgment weights using pairwise comparisons.  
- **MCDM Techniques**:  
  - Linear Methods: Weighted Sum (WSM), Weighted Product (WPM), WASPAS  
  - Distance-Based: TOPSIS, PROMETHEE II  
- **Dataset**: 200 historical tracks analyzed using 7 popularity metrics (playlists, streams, chart positions).

## 🔍 Methodology  
### Data Preparation  
- **Criteria**:  
  - *Maximization*: Spotify/Apple/Deezer playlists, streams.  
  - *Minimization*: Spotify/Apple/Shazam chart positions (lower = better).  
- **Preprocessing**: Missing value handling, outlier removal, and normalization.  

### Weight Distributions  
| Criterion          | Entropy Weight | AHP Weight |  
|---------------------|----------------|------------|  
| Spotify Playlists   | 0.065          | 0.124      |  
| Spotify Charts      | 0.244          | 0.053      |  
| **Streams**         | 0.043          | **0.440**  |  
| Apple Playlists     | 0.092          | 0.085      |  
| Apple Charts        | 0.102          | 0.053      |  
| Deezer Playlists    | 0.110          | 0.220      |  
| **Shazam Charts**   | **0.344**      | 0.026      |  

## 📊 Key Findings  
1. **Entropy Weights** favor seasonal tracks (e.g., *Christmas songs*) due to high Shazam chart variability.  
2. **AHP Weights** prioritize modern pop tracks (e.g., *Sunflower - Post Malone*) through stream count dominance.  
3. **Method Performance**:  
   - *WASPAS* showed 80% ranking consistency across weighting approaches.  
   - *PROMETHEE II* handled criterion conflicts most effectively.  

## 🚀 Recommendations  
| Use Case               | Best Combination          |  
|------------------------|---------------------------|  
| Multi-platform analysis| Entropy + WASPAS (λ=0.6)  |  
| Streaming trend prediction | AHP + PROMETHEE II    |  
| New artist discovery   | Entropy + TOPSIS          |  

## ▶️ Usage  
Run the Jupyter Notebook `Individual_Project_MCDM(Spotify_songs).ipynb` to:  
- **Replicate the weight calculations**: Compare Entropy (objective) and AHP (subjective) weighting.  
- **Generate rankings**: Apply all five MCDM methods (WSM, WPM, WASPAS, TOPSIS, PROMETHEE II).  
- **Visualize comparative results**: Explore ranking differences through interactive charts and tables.  

## 📜 Report  
For detailed analysis, refer to the [**Project Report**](MCDM_Project_Report.pdf), which includes:  
- Full methodological breakdown  
- Weight sensitivity analysis  
- Cross-method ranking comparisons  
- Industry implementation guidelines  
