#  Task 6: Customer Segmentation – Mall Customer Dataset

> Synent Technologies Data Science Internship

---

##  Problem Statement

Businesses need to understand their customers to target them effectively. This project uses unsupervised machine learning (K-Means Clustering) to group mall customers based on their annual income and spending behavior — revealing distinct customer segments that can drive smarter marketing strategies.

---

##  Dataset Details

| Property | Details |
|----------|---------|
| **Name** | Mall Customer Segmentation Dataset |
| **Source** | [Kaggle – Customer Segmentation](https://www.kaggle.com/datasets/vjchoudhary7/customer-segmentation-tutorial-in-python) |
| **Rows** | 200 |
| **Columns** | 5 |

### Key Columns
| Column | Description |
|--------|-------------|
| `CustomerID` | Unique customer identifier |
| `Genre` | Gender (Male / Female) |
| `Age` | Customer age |
| `Annual Income (k$)` | Annual income in thousands of dollars |
| `Spending Score (1-100)` | Score assigned based on spending behavior |

---

##  Approach

### Step 1 – Data Preprocessing
- Loaded dataset and inspected shape, dtypes, and statistics
- Checked for missing values and duplicates (none found)
- Renamed columns to clean snake_case format
- Encoded gender as numeric (Male=0, Female=1)
- Scaled features using `StandardScaler` before clustering

### Step 2 – Exploratory Data Analysis
- Gender distribution (pie chart)
- Age distribution (histogram)
- Annual Income vs Spending Score scatter (colored by gender)
- Correlation heatmap across all numeric features

### Step 3 – Finding Optimal k (Elbow Method + Silhouette Score)
- Tested k values from 2 to 10
- Plotted WCSS (Within-Cluster Sum of Squares) — Elbow Method
- Computed Silhouette Score for each k
- Selected **k = 5** as optimal based on both methods

### Step 4 – K-Means Clustering
- Trained K-Means with `k=5`, `init='k-means++'`, `random_state=42`
- Assigned cluster labels to each customer
- Inverse-transformed centroids back to original scale for interpretation

### Step 5 – Visualize & Interpret Clusters
- Color-coded scatter plot with centroids marked
- Bar charts comparing average income and spending per cluster
- Named each cluster based on behavioral profile

---

## 📊 Results & Key Findings

### Customer Segments Identified

| Cluster | Segment Label | Avg Income | Avg Spending | Business Strategy |
|---------|--------------|------------|--------------|-------------------|
| 0 | High Income, Low Spenders | High | Low | Premium loyalty programs, exclusive offers |
| 1 | Average Income, Average Spenders | Medium | Medium | General promotions, seasonal discounts |
| 2 | Low Income, High Spenders | Low | High | Budget-friendly deals, EMI options |
| 3 | High Income, High Spenders ⭐ | High | High | VIP treatment, new product launches |
| 4 | Low Income, Low Spenders | Low | Low | Value packs, clearance sales |

- **Cluster 3** (High Income + High Spending) is the most valuable customer segment
- **Cluster 0** (High Income + Low Spending) represents untapped potential
- **Cluster 2** (Low Income + High Spending) are impulsive buyers — easy to engage
- Final Silhouette Score confirms well-separated, meaningful clusters

### Visualizations Generated
- Gender distribution pie chart
- Age distribution histogram
- Income vs Spending Score scatter (by gender)
- Correlation heatmap
- Elbow Method plot
- Silhouette Score plot
- Customer cluster scatter with centroids
- Avg income & spending bar charts per cluster

---

##  Repository Structure

```
synent-task6-customersegmentation-yourname/
│
├── task6_customer_segmentation.ipynb   # Main notebook
├── Mall_Customers.csv                  # Raw dataset (or link below)
├── mall_customers_segmented.csv        # Output: labeled customer segments
└── README.md                           # This file
```

---

##  How to Run

1. Clone this repository
   ```bash
   git clone https://github.com/yourusername/synent-task6-customersegmentation-yourname.git
   ```
2. Install dependencies
   ```bash
   pip install pandas numpy matplotlib seaborn scikit-learn
   ```
3. Open the notebook
   ```bash
   jupyter notebook task6_customer_segmentation.ipynb
   ```
4. Run all cells top to bottom

---

##  Tools & Libraries

| Tool | Purpose |
|------|---------|
| Python 3.x | Programming language |
| Pandas | Data manipulation |
| NumPy | Numerical operations |
| Matplotlib | Visualizations |
| Seaborn | Statistical visualizations |
| Scikit-learn | K-Means clustering & StandardScaler |
| Jupyter Notebook | Development environment |

---

##  Author

Megh Chauhan

Data Science Intern – Synent Technologies  
