# Car-Prices-analysis

Exploratory data analysis project on used car sales data using **Python, Pandas, Matplotlib, and Seaborn** to uncover **pricing, sales, and market insights**.

---

## 📌 Project Overview

This project analyzes a used car sales dataset to understand:

- Sales performance by **manufacturer**
- Top-performing **models**
- Sales distribution by **state** and **seller**
- Vehicle characteristics such as:
  - **transmission**
  - **condition**
  - **odometer**
  - **color**
  - **year**
- Relationship between **odometer** and **selling price**

The project focuses on **data cleaning, preprocessing, exploratory data analysis (EDA), and business insights extraction**.

---

## 🎯 Objectives

- Clean and prepare the dataset for analysis
- Handle missing and inconsistent values
- Explore car sales trends and patterns
- Identify top-performing brands, models, and sellers
- Analyze factors affecting selling price

---

## 🛠️ Tools & Libraries

- **Python**
- **Pandas**
- **NumPy**
- **Matplotlib**
- **Seaborn**

---

## 📂 Dataset

**File used:** `car_prices.csv`

The dataset contains used car sales records with features such as:

- `year`
- `make`
- `model`
- `trim`
- `body`
- `transmission`
- `vin`
- `state`
- `condition`
- `odometer`
- `color`
- `interior`
- `seller`
- `mmr`
- `sellingprice`
- `saledate`

---

## 🧹 Data Cleaning & Preprocessing

### ✔️ Steps performed:

- Checked dataset structure using:
```python
df.info()
```

- Checked duplicate rows:
```python
df.duplicated().sum()
```

- Checked missing values:
```python
df.isnull().sum()
```

### ✔️ Missing values handling:

- Dropped rows with missing important identifiers:
  - `make`
  - `model`
  - `vin`
  - `saledate`

- Filled missing values in numerical columns using **mean**:
  - `condition`
  - `odometer`
  - `mmr`
  - `sellingprice`

- Filled missing values in categorical columns using **mode**:
  - `trim`
  - `color`
  - `interior`
  - `body`

### ✔️ Data consistency correction:

The `transmission` column had incorrect values, so it was cleaned:

```python
df["transmission"] = df["transmission"].replace({
    'Sedan': 'automatic',
    'sedan': 'manual'
})
```

Then rows with missing transmission values were removed.

---

## 📊 Exploratory Data Analysis (EDA)

The project answers several business questions through analysis and visualization.

---

## 🔍 Business Questions

### 1. Top 10 manufacturers by number of sales
Identify which car brands sold the highest number of vehicles.

### 2. Top 10 manufacturers by total sales amount
Find which brands generated the highest total revenue.

### 3. Top 10 models by total sales amount
Determine the most financially successful car models.

### 4. Top 5 models for a specific manufacturer
Example analysis was done for **Ford**, and this can be repeated for all manufacturers.

### 5. Top 10 states by total sales amount
Identify the strongest markets by location.

### 6. Top 10 sellers by total sales amount
Show which sellers generated the highest sales.

### 7. Top seller-state combinations by total sales
Useful for deeper regional seller performance analysis.

### 8. Top 5 years by total sales amount
Understand which manufacturing years performed best.

### 9. Top 5 colors by total sales amount
Explore popular vehicle color preferences.

### 10. Transmission ratio
Analyze the proportion of **automatic** vs **manual** cars.

### 11. Correlation between odometer and selling price
Measure whether mileage has an effect on selling price.

---

## 📈 Example Visualization

### Top 10 manufacturers by number of sales

```python
df.pivot_table(
    values='sellingprice',
    index='make',
    aggfunc='count'
).sort_values(by='sellingprice', ascending=False).head(10).plot(kind='bar')

plt.title("Top 10 Maker in Number of Sales")
plt.ylabel("Number of Items")
plt.xlabel("Maker")
plt.show()
```

---

## 📌 Key Insights

Some insights that can be extracted from this project include:

- The manufacturers with the highest number of sold vehicles
- The manufacturers generating the highest sales value
- The most profitable car models
- Regional sales concentration by state
- Seller performance comparison
- Market preference for automatic vs manual transmission
- Relationship between mileage and selling price

> Final insights depend on the cleaned dataset and analysis output.

---

## 🚀 Future Improvements

Possible next steps for this project:

- Clean inconsistent values in `color` more deeply
- Convert `saledate` to datetime format for time-series analysis
- Detect and handle outliers
- Build a **car price prediction model**
- Create an interactive dashboard using:
  - **Power BI**
  - **Tableau**
  - **Streamlit**

---

## ▶️ How to Run the Project

### 1. Clone the repository
```bash
git clone https://github.com/your-username/car-price-analysis.git
```

### 2. Open the project folder
```bash
cd car-price-analysis
```

### 3. Install required libraries
```bash
pip install pandas numpy matplotlib seaborn
```

### 4. Run the analysis
You can run the project using:

- **Jupyter Notebook**
- **VS Code**
- **Spyder**
- **Google Colab**

---

## 📁 Project Structure

```bash
car-price-analysis/
│
├── car_prices.csv
├── car_price_analysis.ipynb
├── README.md
└── images/
```

---

## 💡 Skills Demonstrated

- Data Cleaning
- Data Preprocessing
- Exploratory Data Analysis (EDA)
- Business Insight Extraction
- Data Visualization
- Python for Data Analysis

---

## 👩‍💻 Author

**Marina**  
Aspiring **Data Analyst** interested in transforming raw data into meaningful insights.

---

## ⭐ If you like this project, feel free to star the repository!
