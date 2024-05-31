# Movie Data Analysis

This repository contains Python scripts for loading, cleaning, merging, analyzing, and visualizing movie data. The data sources include box office mojo data from a CSV file and IMDb data from a SQLite database.
This project analyzes movie data from Box Office Mojo and IMDb to uncover insights about genre performance, correlations, and seasonal trends.
## Data Sources
- Box Office Mojo: `Data/bom.movie_gross.csv`
- IMDb: `Data/im.db`

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
- Dropped rows with missing values in `domestic_gross`.
- Converted `domestic_gross` to float after removing special characters.
- Split and exploded `genres` into separate rows.

## Data Merging

The `merge_imdb_data` function merges IMDb movie basics and ratings data based on the 'tconst' column.

## Data Analysis

The `analyze_genre_performance` function analyzes the genre performance by summing up the gross revenue for each genre.
- **Genre Performance**: Analyzed total gross revenue by genre.
- **Correlation Analysis**: Examined correlations between different attributes.
- **Seasonal Trends**: Investigated gross revenue trends across different months.

## Plotting

Three functions are provided for plotting:
- `plot_genre_performance`: Plots the total gross revenue by genre.
- `plot_correlation_matrix`: Plots the correlation matrix.
- `plot_seasonal_trends`: Plots the monthly gross revenue.

## Sample Data

Sample dataframes are provided for genre performance, correlation matrix, and seasonal trends.
## Visualizations
- Total Gross Revenue by Genre
- Correlation Matrix
- Monthly Gross Revenue

## Results
- Action and Comedy genres have the highest total gross revenues.
- Significant correlations were found between ratings and votes.
- Higher gross revenues observed during summer months.

## Recommendations
1. Invest in Action and Comedy movies for higher returns.
2. Focus on improving movie ratings to boost audience engagement.
3. Release blockbuster movies during summer for maximum revenue.

## Next Steps
- Further analyze individual genres for deeper insights.
- Explore other data sources for comprehensive analysis.

## Contact
For questions or collaborations, contact [Akoko Jim Alex] at [https://www.linkedin.com/in/jim-alex-b3aa322b1?utm_source=share&utm_campaign=share_via&utm_content=profile&utm_medium=ios_app].

## Usage

Ensure that the required CSV file (`bom.movie_gross.csv`) and SQLite database file (`im.db`) are located in the 'Data' directory. Run the scripts to perform data analysis and visualization.

### Prerequisites
- Python 3.x
- Jupyter Notebook
- Required Python packages: `pandas`, `matplotlib`, `sqlite3`

### Installation

1. **Clone the Repository:**
   ```sh
   git clone https://github.com/yourusername/your-repo.git
   cd your-repo
   
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



