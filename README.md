# 🏏 IPL Analysis Dashboard (2008–2025) – Power BI Interactive Report

This project is an **interactive Power BI dashboard** that provides a **dynamic, season-wise analysis** of the Indian Premier League (IPL) from **2008 to 2025**. Users can **select any season** from the dropdown, and **all visualizations update automatically** to reflect the chosen year's statistics.

---

## 📌 Features & Functionality

### 🎯 Season-Wise Dynamic Filtering
- A slicer/dropdown lets users select a season (e.g., 2025).
- **Every KPI, table, and chart updates dynamically** based on the selected season.
- Enables users to explore **year-over-year trends and changes**.

---

### 📈 Key Functional Modules

#### 1. **Championship Summary**
- Displays the **Champion and Runner-Up** for the selected season.
- Derived by identifying the team with the highest points or by match date filtering (final match logic).

#### 2. **KPI Cards**
- **Total Matches**: Count of unique matches played that season.
- **Total Teams**: Count of unique teams that played that season.
- **Total Venues**: Count of unique stadiums used.
- **Total 6s & 4s**: SUM of 6s and 4s hit from ball-by-ball data.
- **Centuries & Half-Centuries**: Count of players scoring 100+ or 50–99 runs in a match.

#### 3. **Orange & Purple Cap**
- **Orange Cap (Most Runs)**:
  - Aggregates `total_runs` from ball-by-ball data grouped by batsman.
  - Filters to highest scorer per season.
- **Purple Cap (Most Wickets)**:
  - Counts wickets (excluding run-outs) per bowler.
  - Uses conditional filters to remove invalid dismissals.

#### 4. **Advanced Player Stats**
- **Best Strike Rate**:
  - `Strike Rate = (Total Runs / Balls Faced) * 100`, filtered for players with a minimum threshold.
- **Best Individual Score**:
  - Top individual match score for any player that season.
- **Best Bowling Average**:
  - `Average = Total Runs Conceded / Total Wickets`, with minimum overs or wickets as qualifying criteria.
- **Best Bowling Figure**:
  - Best single-match bowling performance (e.g., 5/35), calculated using match-level filters.

#### 5. **Points Table**
- Dynamically calculated based on:
  - **Matches Played (Pld)**: Total matches per team.
  - **Won, Lost, Tie, NR (No Result)**: Count of match results.
  - **Total Points**: Typically `2 × Wins + 1 × Tie`.
  - Ranks teams accordingly.

---

## 🧮 Calculation Logic Overview (DAX/Power Query)

### Example Calculations:
- **Total 6s**: `SUM('ball_by_ball_data'[is_six])`
- **Orange Cap Runs**: `CALCULATE(SUM('ball_by_ball_data'[total_runs]), ALLEXCEPT('ball_by_ball_data', 'ball_by_ball_data'[batsman]))`
- **Points Table**: Aggregated from match results using groupings on team and match outcome.

### Dynamic Relationships:
- Power BI's data model links tables like:
  - `matches`, `ball_by_ball`, `players`, `teams`, and `venues`
- Uses `RELATED`, `LOOKUPVALUE`, and DAX expressions to connect and derive contextual insights per season.

---

## 📊 Purpose & Applications

- **Explore IPL trends**: Yearly winners, player performance, and league growth.
- **Compare player dominance**: View top performers across formats and years.
- **Evaluate team consistency**: Check performance through points tables over years.
- **Data storytelling tool**: Ideal for sports analysts, journalists, fans, and students.

---

## 🖼️ Screenshots

### 🔹 2025 Season Selected
<img width="1454" height="800" alt="image" src="https://github.com/user-attachments/assets/7f90c979-65f4-40d3-9d14-835e11f40b17" />

### 🔹 2016 Season Selected (Example)
<img width="1452" height="795" alt="image" src="https://github.com/user-attachments/assets/9c64a503-95ac-49e5-bdfb-c60535fb1184" />

> Notice how all KPIs, stats, and tables automatically change based on the selected season, showcasing the dashboard’s **dynamic behavior**.

---
## 🔄 How to Use

1. **Clone or download** the repository.
2. Open the `.pbix` file using [Power BI Desktop](https://powerbi.microsoft.com/desktop/).
3. Use the **season dropdown** to explore dynamic reports across IPL history.
4. Hover over charts for tooltips and deeper insights.

---

## 🛠 Tech Stack

- **Power BI Desktop**
- **DAX** (Data Analysis Expressions)
- **Power Query** (ETL Logic)
- **IPL Dataset**: Includes matches, ball-by-ball events, player details.

---

## 📬 Contact

For any suggestions or contributions, feel free to raise an issue or contact:

**Sudhanshu Kadam**  
[LinkedIn](https://www.linkedin.com/in/sudhanshu-kadam/) | [GitHub](https://github.com/SUDHANSHUKADAM)
