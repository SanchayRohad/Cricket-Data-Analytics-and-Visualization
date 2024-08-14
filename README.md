# 𝐂𝐫𝐚𝐟𝐭𝐢𝐧𝐠 𝐭𝐡𝐞 𝐔𝐥𝐭𝐢𝐦𝐚𝐭𝐞 𝐖𝐢𝐧𝐧𝐢𝐧𝐠 𝐗𝐈 𝐟𝐫𝐨𝐦 𝐈𝐂𝐂 𝐓𝟐𝟎 𝐖𝐨𝐫𝐥𝐝 𝐂𝐮𝐩 𝟐𝟎𝟐𝟒
Cricket Data Analytics and Visualization

# Problem Statement :

In this project, a Power BI Dashboard was developed to analyze and compare the performances of all players participating in the ICC T20 Men's Cricket World Cup 2024. The dashboard provides an interactive platform to evaluate player performances and facilitates the selection of the best 11 players of the tournament, based on specific performance criteria outlined in the problem statement.
# Datasource :
Scrapped all the data regarding match and world cup from www.espncricinfo.com and all details of player career performace and collect data on brightdata

# Data Collection:
Scrapped all the data regarding match and world cup and all details about players career from brightdata using Beautiful Soup library and Jupyter Notebook is used to convert the json files into the dataframes and then these dataframes into csv file for further data analysis on power bi.

# Data Transformation:
Performed initial data cleaning after scrapping such as player name correction, handle missing value, match id linking etc. using Pandas. Transformed the final data for dashboard using Power Query of Power BI.

# Data Modelling:
Connected all the datasets with based on some defined primary keys such as team and match ids. Also, created many measures, calculated columns and parameters for data analysis and dash boarding using DAX.

Data Analysis Expression (DAX)
# Measures used in visualization are:

Total Runs = SUM(t20_batting_summary[runs])

Total Innings Batted =COUNT(t20_batting_summary[matchID])

Total Innings Dismissed = SUM(t20_batting_summary[Out])

Batting Avg = DIVIDE([Total Runs],[Total Innings Dismissed],0)

Total balls faced =SUM(t20_batting_summary[balls])

Strike rate = DIVIDE([Total Runs],[total balls faced],0)*100

Batting Possition = ROUNDUP(AVERAGE(t20_batting_summary[battingPos]),0)

Boundary % = DIVIDE(SUM(t20_batting_summary[Boundary runs]),[Total Runs],0)*100

Avg. balls faced =  AVERAGE(t20_batting_summary[balls])

wickets = SUM(t20_bowling_summary[wickets])

Balls Bowled = SUM(t20_bowling_summary[balls])

Runs Conced = SUM(t20_bowling_summary[runs])

Economy = DIVIDE([Runs Conced],([Balls Bowled]/6),0)

Bowling Strike Rate =DIVIDE([Balls Bowled],[wickets],0)

Bowling Avrage = DIVIDE([Runs Conced],[wickets],0)

Total Innings Bowled = DISTINCTCOUNT(t20_bowling_summary[matchID])

Dot Ball % = DIVIDE(SUM(t20_bowling_summary[zeros]),SUM(t20_bowling_summary[balls]),0)

Player selection = if(ISFILTERED(t20_players_info[name]),"1","0")

Display Text = if([Player selection] = "1"," ","Select Player(s) by clicking the player's name to see their invidual or combined strength")

Color Callout Value =if([Player selection]="0","#E8D166","#1D1D2E")

boundary runs batting =t20_batting_summary[fours]*4 + t20_batting_summary[sixes]*6

boundary runs bowling =t20_bowling_summary[fours]*4+t20_bowling_summary[sixes]*6

# Reports:
Data visualization for the dataset was done using Microsoft Power BI Desktop:

Player Analysis
Openers
2022 T20 Cricket World Cup Dashboard- Best Final 11-2
Middle Order
2022 T20 Cricket World Cup Dashboard- Best Final 11-3
Finisher
2022 T20 Cricket World Cup Dashboard- Best Final 11-4
All Rounder
2022 T20 Cricket World Cup Dashboard- Best Final 11-5
Specilist Fast Bolwers
2022 T20 Cricket World Cup Dashboard- Best Final 11-6
Final Best 11 Players
2022 T20 Cricket World Cup Dashboard- Best Final 11-8
# Tools, Software and Libraries :
1.Jupyter Notebook

2.Python

3.Pandas

4.Webscraping

5.Beautifual Soup

6.Power Query Editor

7.Power BI

8.Anaconda Envirement

# References
https://codebasics.io/courses

https://2022.t20worldcup.com/

https://stats.espncricinfo.com/ci/engine/records/team/match_results.html?id=14450;type=tournament

https://www.espncricinfo.com/series/icc-men-s-t20-world-cup-2022-23-1298134/namibia-vs-sri-lanka-1st-match-first-round-group-a-1298135/full-scorecard

https://brightdata.com/cp/data_collector/collectors/c_lefxe7xf2rj3m5b1b3/code?draft_id=lefxeciy8d6v38d3d


ESPN Website- https://www.espncricinfo.com/series/icc-men-s-t20-world-cup-2024-1411166
powerBI Dashboard- https://app.powerbi.com/view?r=eyJrIjoiNjEyNDAyMjYtMTc4Ni00NjRmLThiOGEtODFmNzUzZjg4YTgwIiwidCI6ImM2ZTU0OWIzLTVmNDUtNDAzMi1hYWU5LWQ0MjQ0ZGM1YjJjNCJ9&pageName=ReportSection3a8cb23b814911c94608
