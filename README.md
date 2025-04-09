# T20-World-Cup-Data-Analytics-Project
In this end-to-end data analytics project, we have used cricket T20 world cup (2022) data to build insights on a best 11 players team. We used bright data web scraping to collect data from ESPNcricinfo website then we performed some data transformation and cleaning in pandas, followed by building dashboards in power bi.

1. Project Aim
"The aim of my project was to extract, clean, and organize T20 World Cup cricket data from JSON files into structured CSV files.
The final output is clean datasets that can be used for further analysis, dashboards, or machine learning models."

2. Steps I Followed
Step 1: Loading and Preparing Match Summary Data
First, I imported necessary libraries like pandas for data handling and json to read JSON files.

Then, I loaded the match summary JSON file (t20_wc_match_results.json) and converted it into a pandas DataFrame called df_match.

I checked the shape and previewed the data to understand the structure.

Step 2: Creating Match ID Dictionary
I noticed that the batting and bowling data only mentions the teams playing (not match IDs directly).

So, I created a dictionary (match_ids_dict) mapping each team1 vs team2 (and vice-versa) combination to the correct match ID.

This mapping is important to later connect batting and bowling data to the correct match.

Step 3: Saving Match Summary
After preparing the match summary data, I saved it as a CSV file (dim_match_summary.csv) for future use.

Step 4: Processing Batting Summary
I then loaded the batting summary JSON file (t20_wc_batting_summary.json).

Since the data was nested inside each match, I flattened it by collecting all battingSummary records into a single list.

I converted this list into a DataFrame (df_batting) and checked its structure.

Step 5: Cleaning Batting Data
I created a new column called out/not_out, based on whether the dismissal field was empty or not.

I used the previously created match_ids_dict to map match names to their respective match IDs.

I removed unnecessary columns like dismissal.

I also cleaned batsman names by removing unwanted characters like â€ and \xa0, ensuring the names are consistent.

Step 6: Saving Batting Data
After cleaning, I saved the final batting summary data into a CSV file (fact_bating_summary.csv).

3. What I learned
How to extract and transform nested JSON data into clean tabular formats.

Importance of data cleaning, especially handling messy text characters and missing links between datasets.

How to build relationships between different pieces of data (batting, bowling, match summary) through keys like match IDs.
