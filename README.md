# Accumulator Data Scraper

## 📖 Overview
**Accumulator Data Scraper** is a Python script that automates the collection of football match prediction data from [AccaGenerator.com](https://www.accagenerator.com/).  
It scrapes prediction details for multiple betting categories such as **1X2 results**, **Over/Under 2.5 goals**, and **Both Teams to Score (BTTS)**, processes them, and saves all the information into a single structured CSV file for daily analysis.

The script uses the **Requests** and **BeautifulSoup** libraries to fetch and parse HTML pages efficiently. It dynamically navigates through prediction links, extracts team names, match dates, times, leagues, tips, and confidence percentages. The scraped data is merged, cleaned, and stored using **Pandas** utilities defined in your `func.py` helper module.

---

## 🚀 Features
- Automatically scrapes **1X2**, **Over/Under 2.5**, and **BTTS** predictions from AccaGenerator.  
- Collects and organizes data for **date, time, teams, league, and confidence percentages**.  
- Dynamically fetches all prediction links from the main page.  
- Supports **daily data saving** using a custom date-based file structure.  
- Removes **duplicate records** after saving.  
- Saves all data into a single **CSV file** for further use in analytics or modeling.  
- Uses **Requests**, **BeautifulSoup**, and **LXML** for fast and clean scraping.

---

## 🧰 Requirements
Install the required Python packages before running the script:

```bash
pip install requests beautifulsoup4 lxml pandas


You also need a func.py file containing helper functions:

requests_init()

saving_files()

drop_duplicate()

sorting_values()

save_daily_csv()

match_day_date()

These are used internally for organizing, saving, and cleaning data.

⚙️ Setup

Clone this repository:

git clone https://github.com/<your-username>/accumulator-data-scraper.git
cd accumulator-data-scraper


Place the provided script and func.py in the same directory.

(Optional) Adjust paths in the script if you want to change the CSV saving location:

path = f'{full_path}/accumulator.csv'


Ensure that you have a stable internet connection for fetching live prediction data.

▶️ Usage

Run the script using:

python accumulator_scraper.py


When executed, the script:

Fetches the main prediction page from AccaGenerator.com.

Extracts all sub-links related to match predictions.

Iterates through each link and scrapes prediction details for:

1X2 outcomes

Over/Under 2.5 goals

Both Teams to Score (BTTS)

Organizes all extracted data into a dictionary.

Saves the information into a daily CSV file inside your output directory.

Removes duplicate rows for cleaner results.

The saved CSV file is automatically named by date and stored using your helper functions.

📂 Output Example

The resulting accumulator.csv file will look like this:

DATE	TIME	HOME TEAM	AWAY TEAM	HOME PER	DRAW PER	AWAY PER	UNDER 2.5	OVER 2.5	BTS	OTS	NAME
19/10/2025	18:30	Liverpool	Tottenham	48	27	25	60	40	55	45	ACC
19/10/2025	20:00	Barcelona	Real Madrid	42	33	25	58	42	63	37	ACC
🧠 Example Use Case

You can use the generated CSV file for:

Sports analytics – build insights from aggregated predictions.

Betting strategy modeling – combine prediction data with algorithms like the Kelly Criterion.

Machine learning – train predictive models using historical prediction data.

Daily tracking – automatically collect and compare prediction accuracy over time.

🧩 Tech Stack

Python 3.10+

Requests – HTTP data fetching

BeautifulSoup4 – HTML parsing

LXML – structure extraction for efficiency

Pandas – data storage and manipulation

Custom Helpers (func.py) – data cleaning, saving, and sorting

⚡ How It Works (Step-by-Step)

Fetch Main Page: The script requests https://www.accagenerator.com/football-predictions/.

Extract Links: It collects all relevant links pointing to daily match prediction pages.

Iterate and Scrape: For each link, it visits and scrapes prediction details for 1X2, Over/Under 2.5, and BTTS.

Parse Data: Uses BeautifulSoup and lxml to extract elements like team names, time, date, and confidence percentages.

Organize Data: Converts the scraped information into Python dictionaries.

Save & Clean: Calls saving_files() and drop_duplicate() to store and clean the final CSV file.

💡 Example Workflow

Suppose today’s predictions include:

Arsenal vs Manchester United – 1X2 tip: “1” (Home win 60%)

PSG vs Lyon – Over/Under 2.5 tip: “Over 2.5” (65%)

AC Milan vs Inter – BTTS: “Yes” (70%)

The script will automatically record this into your daily CSV file, ensuring that no duplicates exist, and the data remains clean for your betting analysis or research.

🧑‍💻 Author

Ezee Kits

YouTube: Ezee Kits

Focus: Python Programming, Web Automation, and Data Analysis

📜 License

This project is licensed under the MIT License — you are free to use, modify, and distribute it with proper credit.

❤️ Support

If you find this project helpful, support by:

⭐ Starring the repository on GitHub

📺 Subscribing to Ezee Kits
 on YouTube for more Python and automation tutorials
