# Movie Data Analysis

This repository contains Python scripts for loading, cleaning, merging, analyzing, and visualizing movie data. The data sources include box office mojo data from a CSV file and IMDb data from a SQLite database.

## Contents

1. [Data Loading](#data-loading)
2. [Data Cleaning](#data-cleaning)
3. [Data Merging](#data-merging)
4. [Data Analysis](#data-analysis)
5. [Plotting](#plotting)
6. [Sample Data](#sample-data)

## Data Loading

The `load_box_office_mojo_data` function loads box office mojo data from a CSV file, while the `load_imdb_data` function loads IMDb data from a SQLite database.

## Data Cleaning

The `clean_box_office_data` function cleans the box office data by dropping rows with missing values in the 'domestic_gross' column and converting the values to float.

## Data Merging

The `merge_imdb_data` function merges IMDb movie basics and ratings data based on the 'tconst' column.

## Data Analysis

The `analyze_genre_performance` function analyzes the genre performance by summing up the gross revenue for each genre.

## Plotting

Three functions are provided for plotting:
- `plot_genre_performance`: Plots the total gross revenue by genre.
- `plot_correlation_matrix`: Plots the correlation matrix.
- `plot_seasonal_trends`: Plots the monthly gross revenue.

## Sample Data

Sample dataframes are provided for genre performance, correlation matrix, and seasonal trends.

## Usage

Ensure that the required CSV file (`bom.movie_gross.csv`) and SQLite database file (`im.db`) are located in the 'Data' directory. Run the scripts to perform data analysis and visualization.

```python
# Example usage
import pandas as pd
from data_loading import load_box_office_mojo_data, load_imdb_data
from data_cleaning import clean_box_office_data
from data_merging import merge_imdb_data
from data_analysis import analyze_genre_performance
from plotting import plot_genre_performance

# Load data
bom_data = load_box_office_mojo_data('Data/bom.movie_gross.csv')
movie_basics, movie_ratings = load_imdb_data('Data/im.db')

# Clean data
cleaned_bom_data = clean_box_office_data(bom_data)
imdb_data = merge_imdb_data(movie_basics, movie_ratings)

# Analyze genre performance
genre_performance = analyze_genre_performance(cleaned_bom_data)

# Plot genre performance
plot_genre_performance(genre_performance)



