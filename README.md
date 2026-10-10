# 🌐 Website Traffic Analysis: Exploratory Data Analysis

An EDA project on website analytics data, exploring when visitors arrive, which channels bring them, and how engaged they are, using Python, Pandas, Matplotlib, and Seaborn.

## 📌 Overview

This project analyzes hourly website traffic data to answer questions like:

- How do users and sessions change across the day?
- Which channel brings the most users?
- Which channels have the best engagement rate and engagement time?
- How do engaged and non-engaged sessions compare by channel?
- At what hours does each channel peak?

## 📊 Dataset

The dataset (`Website.csv`) contains **3,182 hourly records** across **7 traffic channels**: Direct, Organic Search, Organic Social, Organic Video, Referral, Email, and Unassigned.

| Column | Description |
|---|---|
| `channel group` | Source that brought the visitor |
| `Date-hour` | Date and hour of the record |
| `Users` | Number of users in that hour |
| `Sessions` | Number of visits in that hour |
| `Engaged_sessions` | Sessions that counted as engaged |
| `Average engagement time per session` | Average time per session (seconds) |
| `Engaged sessions per user` | Engaged sessions divided by users |
| `Events per session` | Average number of actions per session |
| `Engagement rate` | Engaged sessions divided by total sessions |
| `Event count` | Total number of events recorded |

**Cleaning steps applied:**
- Promoted the first row to the header and renamed all columns
- Converted `Date-hour` to datetime and the other columns to numeric
- Created `Hour` and `non_Engaged_sessions` columns
- No missing values or duplicate rows found

## 🛠️ Tools & Libraries

- **Python 3**
- **Pandas** & **NumPy**: data cleaning and aggregation
- **Matplotlib** & **Seaborn**: visualization

## 📁 Project Structure

```
Website_Analysis_project/
├── Website Analysis.ipynb   # Main analysis notebook
├── Website.csv              # Dataset
└── README.md                # Project documentation
```

## 🔍 Analysis Performed

1. Data cleaning (header fix, column renaming, data types)
2. Users and sessions by hour of day
3. Total users by channel
4. Average engagement time by channel
5. Engagement rate distribution by channel
6. Engaged vs. non-engaged sessions by channel
7. Traffic heatmap by channel and hour
8. Sessions and engagement rate over time

## 💡 Key Insights

**1. Daily Traffic Pattern**
Traffic is lowest at **5 AM (2,598 sessions)**, rises sharply from 6 AM to 11 AM, stays high through the afternoon, and peaks in the evening around **7-9 PM (~9,100 sessions)**. There is also a spike at **midnight (8,148 sessions)**.

**2. Channel Mix**
**Organic Social** drives the most traffic: **60,627 sessions (37.2%)**. Direct (22.8%), Organic Search (20.5%) and Referral (19.0%) share most of the rest. Organic Video, Email and Unassigned together make up under 1%.

**3. Engagement Rate by Channel**
Overall, **55.3%** of sessions were engaged (90,132 of 162,895).
- **Referral: 66.6%** (best among major channels)
- **Organic Search: 58.2%**
- **Organic Social: 53.9%**
- **Direct: 46.3%** (the only major channel with more non-engaged than engaged sessions)

**4. Engagement Time**
**Referral** visitors stay longest among channels with real traffic (~92 seconds per session), about **2x** Direct, Organic Search and Organic Social (~45-53 seconds). Organic Video shows ~180 seconds but has only 141 sessions, so it isn't reliable.

**5. Peak Hours by Channel**
- Direct: 11 PM
- Organic Search: 2 PM
- Organic Social: 12 AM
- Referral: plateau from 11 AM to 10 PM, peaking at 9 PM

**6. Data Quality Flags**
Email has only 3 sessions in total, Unassigned has just **0.7% engagement** (a likely tracking problem), and the maximum engagement time (4,525s) is an extreme outlier against a median of ~49s.

## 📌 Recommendations

1. **Grow Referral partnerships.** Best engagement (66.6%) but only 19% of traffic.
2. **Improve the Direct experience.** 53.7% of Direct sessions are non-engaged.
3. **Convert Organic Social traffic better.** Largest source, but engagement (53.9%) is below the site average (55.3%).
4. **Schedule content around peak hours.** Target 7-9 PM and midnight.
5. **Fix tracking gaps.** Add UTM parameters, especially for Email, and investigate Unassigned traffic.
6. **Collect more data** on Email and Organic Video before judging them.

## 🚀 How to Run

```bash
git clone https://github.com/Satyajeet745/Website_Analysis_project.git
cd Website_Analysis_project
pip install pandas numpy matplotlib seaborn jupyter
jupyter notebook "Website Analysis.ipynb"
```

## 📈 Sample Visuals

The notebook includes line charts, bar charts, a box plot and a heatmap for:
- Users vs. sessions by hour
- Users and engagement by channel
- Engaged vs. non-engaged sessions
- Traffic by channel and hour
- Sessions and engagement rate over time

## 🔮 Future Improvements

- Add day-of-week analysis (weekday vs. weekend traffic)
- Handle outliers in engagement time
- Add a correlation analysis between sessions, events and engagement
- Build an interactive dashboard (Plotly / Streamlit)

## 🙋‍♂️ Author

Made with 🌐 and Python by **Satyajeet**
GitHub: [Satyajeet745](https://github.com/Satyajeet745)

---
