
# Dog Breed Popularity Analysis

![Kaggle Badge](https://img.shields.io/badge/Kaggle-20BEFF?logo=kaggle&logoColor=fff&style=for-the-badge) ![Jupyter Badge](https://img.shields.io/badge/Jupyter-F37626?logo=jupyter&logoColor=fff&style=for-the-badge) ![pandas Badge](https://img.shields.io/badge/pandas-150458?logo=pandas&logoColor=fff&style=for-the-badge) ![Microsoft Excel Badge](https://img.shields.io/badge/Microsoft%20Excel-217346?logo=microsoftexcel&logoColor=fff&style=for-the-badge)

For inquiries or feedback, please contact: 

[![INSTAGRAM](https://img.shields.io/badge/Instagram-E4405F?style=for-the-badge&logo=instagram&logoColor=white)](https://www.instagram.com/piyush.mujmule) ![Kaggle Badge](https://img.shields.io/badge/Kaggle-yellow?logo=kaggle&logoColor=fff&style=for-the-badge)

## Overview

This project analyzes and visualizes the popularity of dog breeds based on their occurrences in a dataset. The dataset includes information on various dog breeds, their ages, weights, colors, and genders. The primary goal is to determine and visualize the most and least popular dog breeds.

## Dataset

The dataset used for this analysis is named `dogs_dataset.csv` and includes the following columns:
- **Breed**: The breed of the dog.
- **Age (Years)**: The age of the dog in years.
- **Weight (kg)**: The weight of the dog in kilograms.
- **Color**: The color of the dog.
- **Gender**: The gender of the dog.

## Project Steps

### 1. Load the Dataset

Load the dataset into a Pandas DataFrame and inspect its structure.

```python
import pandas as pd

# Load the dataset
dogie = pd.read_csv('dogs_dataset.csv')  # Replace with your actual file path

# Inspect the first few rows and column names
print(dogie.head())
print(dogie.columns)
```

### 2. Clean Column Names

Ensure column names are free from leading or trailing spaces.

```python
# Remove any leading/trailing spaces from column names
dogie.columns = dogie.columns.str.strip()
```

### 3. Count Occurrences of Each Breed

Count how often each breed appears in the dataset to determine popularity.

```python
# Count occurrences of each breed
breed_counts = dogie['Breed'].value_counts().reset_index()
breed_counts.columns = ['Breed', 'Popularity']

# Display the result
print(breed_counts.head())
```

### 4. Visualize the Data

#### 4.1. Bar Chart

Create a bar chart to visualize the popularity of each breed.

```python
import matplotlib.pyplot as plt
import seaborn as sns

# Bar Chart
plt.figure(figsize=(12, 6))
sns.barplot(x='Breed', y='Popularity', data=breed_counts, palette='viridis')
plt.title('Dog Breed Popularity')
plt.xlabel('Breed')
plt.ylabel('Popularity')
plt.xticks(rotation=45)
plt.show()
```

#### 4.2. Pie Chart

Create a pie chart to show the distribution of breed popularity.

```python
# Pie Chart
plt.figure(figsize=(8, 8))
plt.pie(breed_counts['Popularity'], labels=breed_counts['Breed'], autopct='%1.1f%%', startangle=140, colors=sns.color_palette('viridis', len(breed_counts)))
plt.title('Dog Breed Popularity Distribution')
plt.show()
```

## Dependencies

- pandas
- matplotlib
- seaborn

You can install the required libraries using pip:

```bash
pip install pandas matplotlib seaborn
```

## Usage

1. Ensure you have the dataset `dogs_dataset.csv` in the correct directory.
2. Run the Python script to load the dataset, analyze breed popularity, and generate visualizations.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

## Acknowledgements

- Thanks to the dataset providers for making this analysis possible.
- Special thanks to the open-source community for the libraries used.

## Contact

For questions or comments, please contact 

[![INSTAGRAM](https://img.shields.io/badge/Instagram-E4405F?style=for-the-badge&logo=instagram&logoColor=white)](https://www.instagram.com/piyush.mujmule)

