# Rutgers Dining Hall Menu & Nutrition Analysis

This project scrapes daily menu and nutrition data from Rutgers University dining halls, stores it in a structured format, and provides analysis tools to help students make informed food choices based on calories, protein, sodium, and dietary preferences.

**Course:** CS 210 — Data Management for Data Science
**Author:** Mufaddal Diwan

---

## Motivation

Rutgers dining hall websites publish menu and nutrition information, but the data is scattered across multiple pages, refreshes daily, and isn't structured for comparison or long-term analysis. A student who wants to find a high-protein, low-sodium meal currently has to click through every dining hall and every meal period by hand.

This project turns that messy data into a clean dataset.

## Features

- **Daily scraping** of menu items and full nutrition facts from Livingston, Neilson, and The Atrium
- **Structured storage** of items by dining hall, meal period, and date
- **Nutrition extraction** including calories, sodium, fiber, and daily-value percentages
- **Visualizations** of nutritional trends and dining hall comparisons

## Tech Stack

- **Python 3.9+**
- `requests` + `beautifulsoup4` — web scraping
- `pandas`, `numpy` — data manipulation
- `matplotlib` — visualization
- Jupyter Notebook — analysis interface

## Setup

If you are running this from CodeBench:
No set up is required.

If you are using Github:

Clone the repo and install dependencies:

```bash
git clone https://github.com/<your-username>/<your-repo>.git
cd <your-repo>
pip install -r requirements.txt
```

If you don't have a `requirements.txt` yet, create one with:

```
requests
beautifulsoup4
pandas
numpy
matplotlib
jupyter
```

## How to Run

1. **Scrape today's menu data**
  Open `NutritionScrape.ipynb` and run the cell. This will hit the Rutgers dining portal and write the results to `output.json`.

2. **Run the analysis**
  Open `analysis.ipynb` and run all cells. It loads `output.json` and produces the comparison tables and plots.

> **Important:** `analysis.ipynb` depends on `output.json`, so `NutritionScrape.ipynb` must be run first.

## Data Source

All data is scraped from the publicly accessible Rutgers Dining menu portal:
`https://menuportal23.dining.rutgers.edu/FoodPronet/pickmenu.aspx`

The scraper collects three dining halls (Livingston, Neilson, The Atrium) across three meal periods (Breakfast, Lunch, Dinner) for the current date.

## Sample Output

Each menu item in `output.json` looks like:

```json
{
  "item_name": "Grilled Chicken Breast",
  "serving_size": "4 oz",
  "nutrition": {
    "Calories": "180",
    "Total Fat": "4g",
    "Protein": "32g",
    "Sodium": "320mg",
    "Percentage": { "Vitamin D": "0%", "Iron": "8%" }
  }
}
```

## Academic Integrity

Code in this repository is original work by Mufaddal Diwan. Third-party libraries (`requests`, `beautifulsoup4`, `pandas`, `numpy`, `matplotlib`) are used as documented dependencies. All scraped data comes from publicly accessible Rutgers dining menu pages.