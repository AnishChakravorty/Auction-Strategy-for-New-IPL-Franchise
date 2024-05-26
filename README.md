# Auction-Strategy-for-New-IPL-Franchise
To develop an effective auction strategy for a new IPL franchise by analyzing past IPL data to create a strong and balanced squad. 

## Table of Contents

1. [Project Title](#project-title)
2. [Objective](#objective)
3. [Background](#background)
4. [Data Collection and Preprocessing](#data-collection-and-preprocessing)
5. [Analyzing Batsmen](#analyzing-batsmen)
6. [Analyzing Bowlers](#analyzing-bowlers)
7. [Analyzing All-Rounders](#analyzing-all-rounders)
8. [Analyzing Wicketkeepers](#analyzing-wicketkeepers)
9. [Auction Strategy Development](#auction-strategy-development)
10. [SQL Queries and Data Analysis](#sql-queries-and-data-analysis)
11. [Visualization and Presentation](#visualization-and-presentation)
12. [Conclusion](#conclusion)
13. [Appendices](#appendices)
    
## Project Title

Developing Auction Strategy for New IPL Franchise

## Objective

To develop an effective auction strategy for a new IPL franchise by analyzing past IPL data to create a strong and balanced squad. The strategy will focus on acquiring key players, including aggressive batters, anchor batsmen, hard-hitters, economical bowlers, wicket-taking bowlers, all-rounders, and wicketkeepers, based on performance metrics and budget constraints.

## Background

The Indian Premier League (IPL) is a professional Twenty20 cricket league in India. Founded by the Board of Control for Cricket in India (BCCI) in 2007, it has become one of the most popular and valuable sports leagues in the world. The league involves eight teams representing different cities or states in India. The competition format includes a double round-robin followed by playoffs, culminating in a final match to determine the champion.

A new team is being added to the IPL, and a mega auction is being held to build the team's squad. The team management needs to analyze past IPL data to make informed decisions during the auction, balancing player performance, team needs, and budget constraints.

## Data Collection and Preprocessing

- **Data Sources:** IPL match data from various seasons
- **Data Cleaning and Preparation:** Removing duplicates, handling missing values, and ensuring consistency in data formats
- **Loading Data into SQL Server:** Storing and managing the data for efficient querying and analysis

## Analyzing Batsmen

### Identifying Aggressive Batsmen

- **Criteria:** High strike rate, minimum balls faced
- **Top 10 Target Players**

### Identifying Anchor Batsmen

- **Criteria:** Good average, minimum IPL seasons played
- **Top 10 Target Players**

### Identifying Hard-Hitters

- **Criteria:** Runs scored in boundaries, minimum IPL seasons played
- **Top 10 Target Players**

## Analyzing Bowlers

### Identifying Economical Bowlers

- **Criteria:** Good economy rate, minimum balls bowled
- **Top 10 Target Players**

### Identifying Wicket-Taking Bowlers

- **Criteria:** Best strike rate, minimum balls bowled
- **Top 10 Target Players**

## Analyzing All-Rounders

- **Criteria:** Best batting and bowling strike rates, minimum balls faced and bowled
- **Top 10 Target Players**

## Analyzing Wicketkeepers

- **Criteria:** Consistent performance, batting and keeping skills
- **Top 10 Target Players**

## Auction Strategy Development

- **Budget Allocation**
- **Target Player Profiles and Rankings**
- **Bidding Strategies**
- **Retention and Right to Match Options**

## SQL Queries and Data Analysis

### Count of Cities Hosting IPL Matches

```sql
SELECT city, COUNT(DISTINCT match_id) AS matches_hosted
FROM matches
GROUP BY city;
```

### Creating and Analyzing Deliveries_v02 Table

```sql
CREATE TABLE deliveries_v02 AS
SELECT match_id, inning, batting_team, bowling_team, over, ball, batsman, bowler, wide_runs, bye_runs, 
legbye_runs, noball_runs, penalty_runs, batsman_runs, extra_runs, total_runs, player_dismissed, dismissal_kind, fielder
FROM deliveries;
```

### Boundary and Dot Ball Analysis

```sql
SELECT batting_team, COUNT(*) AS boundary_count
FROM deliveries_v02
WHERE batsman_runs = 4 OR batsman_runs = 6
GROUP BY batting_team;

SELECT bowling_team, COUNT(*) AS dot_ball_count
FROM deliveries_v02
WHERE total_runs = 0
GROUP BY bowling_team;
```

### Dismissal Analysis

```sql
SELECT dismissal_kind, COUNT(*) AS dismissal_count
FROM deliveries_v02
WHERE player_dismissed IS NOT NULL
GROUP BY dismissal_kind;
```

### Extra Runs Conceded Analysis

```sql
SELECT bowling_team, SUM(extra_runs) AS total_extras
FROM deliveries_v02
GROUP BY bowling_team;
```

# Visualization and Presentation

## Graphs, Tables, and Charts

- Batting Performance: Bar charts for strike rates and averages
- Bowling Performance: Line graphs for economy rates and strike rates
- Team Analysis: Pie charts for win percentages
- Dismissals: Bar charts for types of dismissals
- Extras Analysis: Heat maps for extra runs conceded by teams

# Conclusion

### Summary of Findings

- Identified key players based on performance metrics
- Developed a balanced and strategic auction plan

### Recommendations for Auction Strategy

- Focus on acquiring identified top performers
- Allocate budget efficiently to cover all key roles

### Future Work

- Continuous data analysis for future seasons
- Advanced metrics and predictive modeling for player performance

# Appendices

### SQL Queries

- Detailed SQL queries used for analysis

### Data Tables

- Raw and processed data tables

### Additional Resources

- References and additional reading materials

# How to Access this Document 

1. Open the following link from here: [SQL Project](https://trainings.internshala.com/uploads/sql-ds-pgc/uploads/projects/v_1/3839755/65bf8bc354313.rar)
2. Download the Zip File `Final Project` which contains all the files.
3. Open the file in Microsoft Excel and Open the PPT in Microsoft Powerpoint or any compatible software to view analysis.




























