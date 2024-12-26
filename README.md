# used_car_eda 
EDA(Exploratory Data Analysis) on Used Car Dataset

## Project Overview
This project aims to perform an Exploratory Data Analysis (EDA) on a synthetic used car dataset to uncover insights into factors affecting vehicle prices, such as mileage, year of manufacturing, and accident history. The analysis includes data preprocessing, visualization, and summary statistics, providing a foundation for predictive modeling or pricing strategies in used car markets.


## Data

### Source
The dataset used in this project comes from the [Kaggle Playground Series - Season 4, Episode 9](https://www.kaggle.com/competitions/playground-series-s4e9/data). The data is **synthetically generated** for the competition and does not represent real-world car data.

### Description
- **Train Dataset Only**: For this analysis, we only used the `train.csv` file provided by Kaggle.
- **Number of Rows**: 188,533
- **Number of Columns**: 13 features (after preprocessing, additional features were added).

### Features
| Feature Name    | Description                                     |
|-----------------|-------------------------------------------------|
| `id`            | Unique identifier for each vehicle              |
| `brand`         | Manufacturer (e.g., Toyota, Ford)               |
| `model`         | Model name                                      |
| `model_year`    | Year of manufacturing                          |
| `mileage`       | Mileage driven (in miles)                      |
| `fuel_type`     | Type of fuel (e.g., Gasoline, Diesel)           |
| `engine`        | Engine specifications                          |
| `transmission`  | Transmission type (e.g., Automatic, Manual)    |
| `ext_col`       | Exterior color                                 |
| `int_col`       | Interior color                                 |
| `accident`      | Accident history (Yes/No)                      |
| `clean_title`   | Legal title status (Yes/No)                    |
| `price`         | Vehicle price (USD)                            |

> Note: The dataset is synthetically generated and used solely for educational and exploratory purposes.

---

### **Sample Dataset**
Due to file size limitations, this repository includes a **10% random sample** of the original `train.csv` dataset.

#### Sample Data Generation
The sample dataset was created by randomly selecting 10% of the rows from the original `train.csv` using the following Python code:

```python
import pandas as pd

# Load original dataset
data = pd.read_csv('train.csv')

# Create a 10% sample
sample_data = data.sample(frac=0.1, random_state=42)

# Save sample data
sample_data.to_csv('sample_data.csv', index=False)

- **Original Dataset**: 188,533 rows, 13 features.
- **Sample Dataset**: 18,853 rows, same features.

## **Key Insights from EDA**

### 1. Price vs. Year
- Newer cars generally have higher prices, with a noticeable drop in value for cars older than 5 years.
![Price vs Year](https://github.com/son9806/used_car_eda/raw/main/images/average_price_by_year.PNG)

### 2. Price vs. Mileage
- There is a negative correlation between price and mileage, indicating that cars with higher mileage are generally cheaper.
![Price vs Mileage](https://github.com/son9806/used_car_eda/raw/main/images/price_vs_mileage.PNG)

### 3. Accident History
- Cars with accident history tend to have significantly lower prices.
![Accident History](https://github.com/son9806/used_car_eda/raw/main/images/price_vs_accident_status.PNG)

### 4. Vehicle Type
- SUVs and sports cars are priced higher on average compared to compact and subcompact vehicles.
![Vehicle Type](https://github.com/son9806/used_car_eda/raw/main/images/price_by_vehicle_type.PNG)


## Repository Structure
used_car_eda/
├── data/
│   └── sample_data.csv            # 10% sampled dataset from Kaggle's train.csv
├── images/
│   ├── average_price_by_year.png  # Visualization: Price vs. Year
│   ├── price_by_vehicle_type.png  # Visualization: Price by Vehicle Type
│   └── ...                        # Additional visualizations
├── notebooks/
│   └── used_car_data_analysis.ipynb # Jupyter Notebook for EDA
└── README.md                      # Project overview and details
