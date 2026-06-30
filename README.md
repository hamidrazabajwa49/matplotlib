# Matplotlib Practice & Data Visualization Projects

A collection of seven Jupyter notebooks covering Matplotlib fundamentals and applied exploratory data analysis (EDA) on real and synthetic datasets. Built as hands-on practice for data visualization, pandas data wrangling, and chart design — from basic chart types to multi-step analysis pipelines.

## Repository Structure

```
matplotlib/
├── 01_matplotlib_basics_chart_types.ipynb
├── 02_sales_revenue_analysis.ipynb
├── 03_weather_data_analysis.ipynb
├── 04_student_scores_analysis.ipynb
├── 05_synthetic_dataset_visualization.ipynb
├── 06_covid_dataset_eda.ipynb
├── 07_matplotlib_chart_gallery.ipynb
├── data/
│   ├── corona_dataset.csv
│   └── practice_dataset.xlsx
├── requirements.txt
└── README.md
```

All notebooks load data using relative paths (`data/<filename>`), so they will run correctly as long as the notebook is executed from the repository root with the `data/` folder alongside it.

## Notebooks Overview

### 01. Matplotlib Basics: Chart Types
A foundational gallery of core chart types with minimal styling: line plots, labeled and styled line plots, horizontal bar charts, pie charts, histograms, multi-group scatter plots, and three different approaches to subplots (`plt.subplot`, `plt.subplots`, and stacked layouts). Each section is self-contained with synthetic in-notebook data, making it a good starting reference for Matplotlib syntax.

### 02. Sales Revenue Analysis
Uses the `SalesData` sheet of `practice_dataset.xlsx` to compute per-transaction revenue (`Quantity × Price`), aggregate revenue by product with percentage share, identify the top 3 products, and visualize a daily revenue trend (line chart) and total revenue by product (bar chart).

- **Data**: `data/practice_dataset.xlsx` → sheet `SalesData`
- **Columns**: `Date`, `Product`, `Quantity`, `Price`

### 03. Weather Data Analysis
Works with the `WeatherData` sheet to demonstrate a typical light-cleaning workflow: inspecting data with `.info()` and `.describe()`, imputing missing temperature values with the column mean, converting Celsius to Fahrenheit, and visualizing the temperature distribution (histogram), the temperature–humidity relationship (scatter plot with correlation coefficient), and humidity spread (box plot).

- **Data**: `data/practice_dataset.xlsx` → sheet `WeatherData`
- **Columns**: `Date`, `Temp`, `Humidity`, `WindSpeed`

### 04. Student Scores Analysis
Analyzes the `StudentScores` sheet to compute total and average scores per student, rank the top 5 performers, classify students as Pass/Fail against a configurable threshold, and visualize the pass/fail split (pie chart), subject-wise averages (bar chart), and a grouped bar chart comparing the top 5 students across subjects.

- **Data**: `data/practice_dataset.xlsx` → sheet `StudentScores`
- **Columns**: `Name`, `Math`, `Science`, `English`

### 05. Synthetic Dataset Visualization
Generates a 100-row synthetic dataset (dates, sales, region, customer satisfaction, product category) with NumPy and walks through the four foundational Matplotlib plot types — line, scatter, bar, and histogram — followed by grouped aggregation views: average sales by region and average customer satisfaction by product category.

- **Data**: generated in-notebook (no external file required)

### 06. COVID-19 Dataset: Exploratory Data Analysis
A real-world time-series EDA on daily new confirmed COVID-19 cases per million people (7-day rolling average) for Pakistan. Covers structural inspection (`.info()`, `.describe()`, missing-value checks), the full daily trend, identifying the peak day, year-over-year summary statistics, a resampled monthly average trend, and the overall distribution of daily case rates.

- **Data**: `data/corona_dataset.csv`
- **Columns**: `Entity`, `Day`, `Daily new confirmed cases of COVID-19 per million people (rolling 7-day average, right-aligned)`

### 07. Matplotlib Chart Gallery
A reference gallery of 20 self-contained exercises, each demonstrating one chart type or technique: line, scatter, bar, histogram, pie, 2×2 subplot grids, stacked bar, horizontal bar, area/fill plots, annotated scatter, box plot, violin plot, heatmap (`imshow`), multi-line overlays, twin-axis plots, step plots, error bars, histogram with a fitted Gaussian curve, polar plots, and custom style sheets (`ggplot`).

## Setup & Usage

1. **Clone the repository**
   ```bash
   git clone https://github.com/<your-username>/matplotlib.git
   cd matplotlib
   ```

2. **Create a virtual environment (recommended)**
   ```bash
   python -m venv venv
   source venv/bin/activate      # On Windows: venv\Scripts\activate
   ```

3. **Install dependencies**
   ```bash
   pip install -r requirements.txt
   ```

4. **Launch Jupyter**
   ```bash
   jupyter notebook
   ```

5. **Run notebooks from the repository root** so that the relative `data/` paths resolve correctly. Each notebook can be run independently — there are no cross-notebook dependencies.

## Datasets

| File | Used By | Description |
|---|---|---|
| `data/practice_dataset.xlsx` | 02, 03, 04 | Multi-sheet workbook with `SalesData`, `WeatherData`, and `StudentScores` sheets |
| `data/corona_dataset.csv` | 06 | Daily COVID-19 case rates per million people (Pakistan), rolling 7-day average |

## Key Skills Demonstrated

- Core Matplotlib chart types: line, bar, horizontal bar, stacked bar, pie, histogram, scatter, box plot, violin plot, heatmap, area/fill, step, polar, and error bar plots
- Multi-panel layouts using `plt.subplot`, `plt.subplots`, and twin axes
- Pandas data loading from CSV and multi-sheet Excel files
- Data cleaning: missing-value detection and imputation, unit conversion
- Feature engineering: derived columns (e.g., revenue, totals, averages, pass/fail status)
- Aggregation and grouping with `groupby`, `resample`, and ranking operations
- Time-series handling: date parsing, monthly resampling, year-over-year summaries
- Descriptive statistics and correlation analysis
- Chart styling: colors, markers, legends, gridlines, annotations, and built-in style sheets

## Notes

- Notebooks are written to run top-to-bottom without manual intervention.
- Plots are rendered inline using `plt.show()`; no special Jupyter magic (e.g. `%matplotlib inline`) is required in recent Jupyter versions, but you may add it if plots do not render automatically in your environment.
- All code is written at an intermediate practitioner level using standard libraries (`pandas`, `numpy`, `matplotlib`) — no external visualization frameworks.

## License

This repository is intended for educational and portfolio purposes. Feel free to fork, adapt, and reuse for your own learning.
