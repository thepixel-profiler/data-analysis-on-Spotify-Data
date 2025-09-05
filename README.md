# Spotify Data Analysis

This project analyzes a dataset of Spotify songs to understand various song attributes and identify trends in popularity. The analysis is performed using Python in a Jupyter Notebook environment, leveraging libraries like pandas, matplotlib, and seaborn.

## Dataset

The dataset used in this analysis is a CSV file named `dataset.csv`. It contains 114,000 songs with 21 different features, including:

  * **`track_id`**: The Spotify ID for the track.
  * **`artists`**: The artist(s) of the track.
  * **`album_name`**: The album the track belongs to.
  * **`track_name`**: The name of the track.
  * **`popularity`**: A popularity score from 0 to 100, where a higher score is more popular.
  * **`duration_ms`**: The length of the track in milliseconds.
  * **`explicit`**: A boolean indicating if the track contains explicit content.
  * **`danceability`**: A measure of how suitable a track is for dancing (0.0 to 1.0).
  * **`energy`**: A measure of intensity and activity (0.0 to 1.0).
  * **`key`**: The key the track is in.
  * **`loudness`**: The overall loudness of the track in decibels (dB).
  * **`mode`**: The modality (major or minor) of a track.
  * **`speechiness`**: Detects the presence of spoken words in a track.
  * **`acousticness`**: A confidence measure of whether the track is acoustic (0.0 to 1.0).
  * **`instrumentalness`**: Predicts whether a track contains no vocals.
  * **`liveness`**: Detects the presence of an audience in the recording.
  * **`valence`**: A measure from 0.0 to 1.0 describing the musical positiveness conveyed by the track.
  * **`tempo`**: The tempo of the track in beats per minute (BPM).
  * **`time_signature`**: An estimated overall time signature of a track.
  * **`track_genre`**: The genre of the track.

## Project Structure

The analysis is contained within the `spotify_data_analysis.ipynb` Jupyter Notebook. The key steps of the analysis include:

1.  **Loading Data**: The notebook starts by importing the necessary libraries (`pandas`, `matplotlib`, and `seaborn`) and loading the `dataset.csv` file into a pandas DataFrame.
2.  **Data Exploration and Cleaning**:
      * The `spotify_data.head()` function is used to display the first few rows of the DataFrame to ensure the data was loaded correctly.
      * `spotify_data.info()` provides a summary of the DataFrame, including the data types of each column and the number of non-null values.
      * Null values are identified using `spotify_data.isnull().sum()`.
      * Duplicate rows are checked for with `spotify_data.duplicated().sum()`.
      * Irrelevant columns (`danceability`, `loudness`, `speechiness`, and `instrumentalness`) are dropped to simplify the DataFrame.
3.  **Descriptive Statistics and Correlation Analysis**:
      * `spotify_data.describe()` generates descriptive statistics for the numerical columns.
      * A new DataFrame containing only numerical data is created.
      * A correlation matrix is generated for the numerical features using `spotify_data_numeric.corr()`.
      * A heatmap is created with seaborn to visualize the correlations between the different song features.
4.  **Popularity Analysis**:
      * The mean popularity for each genre is calculated, and a bar plot is generated to show the top 10 most popular genres based on their average popularity score.
      * The analysis focuses on the "k-pop" genre, creating a new DataFrame specifically for these songs.
      * The top 10 K-pop artists are identified by calculating the average popularity of their tracks, and a bar plot is created to visualize these results.
5.  **Saving Cleaned Data**: The final, cleaned DataFrame is saved to a new CSV file named `cleaned_spotify_data.csv`. This file can be used for further analysis or for creating a visualization dashboard in a tool like Google Looker Studio.

## How to Run the Notebook

1.  Ensure you have a Python environment with Jupyter Notebook installed.
2.  Install the required libraries:
    ```
    pip install pandas matplotlib seaborn
    ```
3.  Download the `dataset.csv` file and place it in the same directory as the notebook.
4.  Open the `spotify_data_analysis.ipynb` file in Jupyter Notebook.
5.  Run all the cells in the notebook to reproduce the analysis and visualizations.

## Visualizations

The notebook generates three main visualizations:

  * **Correlation Heatmap**: This shows the relationships between various numerical song features.
    <Figure size 1200x1000 with 2 Axes><img width="1006" height="923" alt="image" src="https://github.com/user-attachments/assets/d60bdea0-fcca-448b-87e5-c9f2df1f6c63" />

  * **Top 10 Genres by Average Popularity**: A bar plot displaying the genres with the highest average popularity scores.
    <Figure size 1200x600 with 1 Axes><img width="1044" height="545" alt="image" src="https://github.com/user-attachments/assets/d088819d-3fbf-4cf8-94fa-ea3ad9faf0c8" />

  * **Top 10 K-pop Artists by Average Popularity**: A bar plot highlighting the most popular artists within the K-pop genre.
    <Figure size 1200x600 with 1 Axes><img width="1270" height="545" alt="image" src="https://github.com/user-attachments/assets/2ec5150f-ad91-45b1-bf2f-35b0ae34e48a" />

The final Dashboard created using Google Looker Studio:
<img width="1616" height="1204" alt="Screenshot 2025-09-05 173535" src="https://github.com/user-attachments/assets/d249d44c-73be-4192-b884-39d7f0046d40" />

This project provides a clear, step-by-step example of how to perform exploratory data analysis on a musical dataset.
