# Ford GoBike System Data Analysis (San Francisco Bay Area, 2019)
## by Alankrit Agarwal

## Project Overview
This project explores and visualizes individual ride data from the Ford GoBike bike-sharing system covering the greater San Francisco Bay Area in 2019. Using Python data science and visualization libraries, the analysis progresses systematically from univariate distributions to bivariate and multivariate relationships to uncover key demographic and behavioral drivers of bike-share usage.

---

## Dataset
The dataset used for this project is the **Ford GoBike System Data** (`201902-fordgobike-tripdata.csv`), which includes information about individual rides made in a bike-sharing system covering the greater San Francisco Bay Area in 2019. After preliminary data wrangling, the dataset contains over **160,000 observations**.

During the cleaning process:
* **Missing Values:** Rows with missing values were dropped to ensure visual integrity.
* **Feature Engineering:** A new feature, `member_age`, was calculated by subtracting `member_birth_year` from the year of data collection (`2019`).
* **Outlier Removal:** Extreme outliers were filtered out to focus on standard usage; the dataset was restricted to trips lasting **3,600 seconds (1 hour) or less**, and riders aged **80 and under**.

---

## Summary of Findings
* **Univariate Exploration (Trip Duration):** The distribution of bike trip durations is heavily right-skewed. The vast majority of trips are very short (under 1,000 seconds, or roughly 15 minutes), indicating the service is primarily used for quick commutes rather than long-term rentals.
* **Bivariate Exploration (User Type):** `user_type` emerged as a strong indicator of trip behavior. While annual **Subscribers** make up the overwhelming majority of total trips, casual **Customers** actually take significantly longer rides on average.
* **Multivariate Exploration (Age, Duration & User Type):** Rider age (`member_age`) creates a natural ceiling on trip duration. Younger riders show a wide variance in ride times (taking both short and long trips), whereas riders over the age of 60 adhere almost exclusively to short trips.

---

## Key Insights for Presentation
For the explanatory presentation, the analysis focuses on the primary demographic drivers of trip duration: **User Type** and **Rider Age**. 
1. **Baseline Usage:** Starts by establishing the baseline distribution of trip durations to highlight the system's primary use case (short commutes).
2. **Customer vs. Subscriber Behavior:** Uses a box plot to contrast the differing trip lengths between casual Customers and annual Subscribers.
3. **Combined Demographic Impact:** Culminates in a multivariate scatter plot that combines age, duration, and user type to provide a complete picture of rider habits.

**Explanatory Design Enhancements:**
* Implemented a custom helper function to ensure all plots have bold, descriptive titles summarizing the main takeaway.
* Labeled all x and y axes clearly with appropriate units (e.g., `Seconds`, `Years`).
* Utilized distinct color palettes (`Set2` and `viridis`) and added legends to clearly separate the categorical user types and improve audience readability.

---

## Repository Structure

```text
ford-gobike-data-analysis/
├── data/
│   └── README.md                                  # Dataset download instructions
├── notebooks/
│   ├── 01_exploratory_analysis.ipynb              # Part I: Exploratory Data Analysis
│   └── 02_explanatory_analysis.ipynb              # Part II: Explanatory Visualizations
├── reports/
│   ├── Part_I_exploration_template.html           # Exported HTML Report (Part I)
│   └── Part_II_explanatory_template.html          # Exported HTML Report (Part II)
├── .gitignore                                     # Ignored files and checkpoints
├── requirements.txt                               # Python dependencies
└── README.md                                      # Project documentation
```

---

## View Reports
* **Notebooks:**
  * [Part I: Exploratory Data Analysis Notebook](notebooks/01_exploratory_analysis.ipynb)
  * [Part II: Explanatory Data Analysis Notebook](notebooks/02_explanatory_analysis.ipynb)
* **Rendered HTML Reports:**
  * [Part I: Exploratory HTML Report](https://htmlpreview.github.io/?https://github.com/alankrit98/ford-gobike-data-analysis/blob/main/reports/Part_I_exploration_template.html)
  * [Part II: Explanatory HTML Report](https://htmlpreview.github.io/?https://github.com/alankrit98/ford-gobike-data-analysis/blob/main/reports/Part_II_exploration_template.html)

---

## Tech Stack & Local Setup
* **Python 3:** `numpy`, `pandas`, `matplotlib`, `seaborn`, `jupyter`

```
git clone https://github.com/alankrit98/ford-gobike-data-analysis.git
cd ford-gobike-data-analysis
pip install -r requirements.txt
jupyter notebook
```
