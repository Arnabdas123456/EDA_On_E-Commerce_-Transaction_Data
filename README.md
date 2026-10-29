# 🛒 E-Commerce Transaction Data Analysis (EDA)

## 📌 Project Overview

This project performs **Exploratory Data Analysis (EDA)** on an e-commerce transaction dataset using Python. It explores transaction records, product quantities, revenue by country, monthly revenue trends, customer spending, hourly order patterns, and relationships between numerical variables.

The analysis uses **Pandas**, **NumPy**, and **Plotly Express** to inspect, clean, summarize, and visualize the data.

## 🎯 Objectives

- Understand the structure and quality of the transaction dataset.
- Identify missing values and duplicate records.
- Clean the data and prepare it for analysis.
- Calculate transaction revenue using quantity and unit price.
- Explore product sales, country revenue, and monthly revenue.
- Analyze customer spending and order activity by hour.
- Examine correlations between quantity, unit price, and revenue.
- Summarize key business metrics (KPIs).

## 🧰 Tools & Technologies

- **Python** — programming language
- **Pandas** — data cleaning, grouping, aggregation, and analysis
- **NumPy** — numerical computing library
- **Plotly Express** — interactive charts and visualizations
- **Jupyter Notebook** — interactive development environment

## 📂 Dataset

The notebook loads a CSV file named `data.csv` using Latin-1 encoding.

The original dataset contains **541,909 rows and 8 columns**.

| Column | Description |
|---|---|
| `InvoiceNo` | Invoice or transaction identifier |
| `StockCode` | Product stock code |
| `Description` | Product description |
| `Quantity` | Quantity recorded in the transaction row |
| `InvoiceDate` | Date and time of the invoice |
| `UnitPrice` | Price per unit |
| `CustomerID` | Customer identifier |
| `Country` | Customer's country |

**Note:** Place `data.csv` in the same directory as the notebook before running it. The dataset itself may need to be obtained separately if it is not included in the repository.

## 🔄 Analysis Workflow

### 1. Load and inspect the data

- Load `data.csv` into a Pandas DataFrame.
- Review the first rows and dataset dimensions.
- Inspect column data types and non-null counts.
- Count missing values and duplicate rows.

### 2. Missing-value analysis

The notebook checks missing values in each column and creates a Plotly bar chart for columns that contain missing data.

In the original dataset, missing values were found in:
- `Description`: **1,454**
- `CustomerID`: **135,080**

The notebook also identified **5,268 duplicate rows** before cleaning.

### 3. Data cleaning and feature engineering

The notebook:
- Removes rows without a `CustomerID`.
- Removes duplicate rows.
- Converts `InvoiceDate` to a datetime data type.
- Creates a `Revenue` column using:

```python
df["Revenue"] = df["Quantity"] * df["UnitPrice"]
```

After these cleaning steps, the dataset contains **401,604 rows and 9 columns**.

### 4. Product sales analysis

Groups the data by `Description`, sums `Quantity`, and visualizes the **top 10 products by total quantity** using a horizontal bar chart.

### 5. Revenue by country

Groups transactions by `Country`, sums `Revenue`, and plots the **top 10 countries by revenue**.

### 6. Monthly revenue trend

Extracts the month from `InvoiceDate`, groups revenue by month, and displays a line chart to explore how revenue changes over time.

### 7. Customer spending distribution

Calculates total revenue per `CustomerID` and uses a histogram to examine the distribution of customer spending.

### 8. Top 10 customers

Aggregates revenue by customer, sorts the totals in descending order, and visualizes the **10 customers with the highest recorded revenue**.

### 9. Orders by hour

Extracts the hour from `InvoiceDate`, counts transaction rows for each hour, and plots the hourly activity.

### 10. Correlation analysis

Calculates and visualizes a correlation matrix for:
- `Quantity`
- `UnitPrice`
- `Revenue`

The heatmap helps inspect linear relationships between these numerical variables.

### 11. KPI summary

The notebook calculates total revenue, unique invoice count, unique customer count, and unique product-description count after cleaning.

## 📊 Key Results

The notebook's KPI output after cleaning is:

| Metric | Result |
|---|---:|
| Total revenue | 8,278,519.42 |
| Unique invoices (orders, as counted by `InvoiceNo`) | 22,190 |
| Unique customers | 4,372 |
| Unique product descriptions | 3,896 |
| Rows after cleaning | 401,604 |

**Interpretation note:** The notebook calculates revenue as `Quantity × UnitPrice` and sums it across the cleaned rows. The reported total is in the dataset's price units; the notebook does not explicitly define a currency symbol.

## 🚀 How to Run the Project

### Prerequisites

Install Python and Jupyter Notebook or JupyterLab.

### 1. Clone the repository

```bash
git clone https://github.com/Arnabdas123456/EDA_On_E-Commerce_-Transaction_Data.git
cd EDA_On_E-Commerce_-Transaction_Data
```

### 2. Install dependencies

```bash
pip install numpy pandas plotly jupyter
```

### 3. Add the dataset

Ensure `data.csv` is in the same directory as `e_commerce.ipynb`.

### 4. Launch Jupyter Notebook

```bash
jupyter notebook
```

Open `e_commerce.ipynb` and run the cells in order.

## 📁 Project Structure

```text
EDA_On_E-Commerce_-Transaction_Data/
├── e_commerce.ipynb    # EDA notebook
├── data.csv            # Input dataset (provide separately if not in repo)
└── README.md           # Project documentation
```

## 💡 Skills Demonstrated

- Exploratory Data Analysis (EDA)
- Data quality inspection and cleaning
- Missing-value and duplicate detection
- Pandas grouping and aggregation
- Datetime feature extraction
- Revenue and KPI calculations
- Interactive data visualization with Plotly Express
- Correlation analysis

## 🔮 Possible Future Improvements

- Investigate returns or cancelled invoices and negative quantities, if present.
- Add more robust validation for missing product descriptions and unusual prices.
- Compare sales volume with revenue to identify high-volume and high-revenue products.
- Add a dashboard for interactive business exploration.
- Document additional findings from the generated charts.

## 👨‍💻 Author

**Arnab Das**

- GitHub: [@Arnabdas123456](https://github.com/Arnabdas123456)
- Repository: [EDA on E-Commerce Transaction Data](https://github.com/Arnabdas123456/EDA_On_E-Commerce_-Transaction_Data)

---

If you find this project useful, feel free to ⭐ the repository.
