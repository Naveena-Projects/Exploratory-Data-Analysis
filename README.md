# Exploratory Data Analysis Using Python
## Premier League Clubs Analysis for Investment
### Context
A renowned investment firm typically invests in top-tier sports teams with significant potential. The dataset in their possession contains crucial information about all the clubs that have participated in the Premier League, and it is assumed to include data for all the clubs. The dataset includes information on the number of goals scored by each team, the frequency of their finishes in the top two positions, and other relevant details.

### Data Set Description
The provided dataset encompasses comprehensive information on all football clubs that have participated in the English Premier League tournaments. Below is the data dictionary outlining the key parameters:
*	Club: Name of the football club
*	Matches: Number of matches played by the club in the Premier League.
*	Wins: Number of matches won by the club in the Premier League.
*	Loss: Number of matches lost by the club in the Premier League.
*	Draws: Number of matches drawn by the club in the Premier League.
*	Clean Sheets: Number of matches in which the club prevented the opposing side from scoring.
*	Team Launch: The year in which the club was founded.
*	Winners: Number of times the club has won the Premier League.
*	Runners-up: Number of times the club has finished as runner-up in the Premier League.
*	lastplayed_pl: The year in which the team last played in the Premier League.

> ##### Note
>   * *! Unauthorised use or distribution of this project is prohibited (@dataanalystduo).*
>   * *! The dataset has been acquired from multiple sources on the internet.*
>   * *! Credits for the dataset go to the original creator of the data.* 
>   * *! This data is updated as of March'23*

### Objective
The management of the firm aims to invest in one of the top-performing club in the English Premier League. To facilitate their decision-making process, a comprehensive report on the performance of various clubs can be created. However, some of the more established clubs have already been acquired by competitors. Consequently, the firm wishes to identify clubs they can approach and potentially invest in, ensuring a successful and profitable deal.

### Data Exploration 
Upon initial examination of the dataset using shape, head, and tail functions, it is observed that the dataset contains 11 columns providing information about 40 different football clubs and their performance in the English Premier League over the years. Inconsistencies noted during the observation of the columns are as follows:
1.	The 'club' column has numbers attached before the club names.
2.	Values in the 'Team launch' column are not consistent, displayed in two different date formats.
3.	'winners' and 'runners-up' columns contain missing values.
4.	Information about the month in which the team last played in the PL, given along with the year in the 'lastplayed_pl' column, seems unnecessary. The data need to be converted to the year-alone format in this column.
5.	The data type for the "Runners-up" column is non-numeric (object type). To perform numerical analysis on this column, it needs to be converted to a numeric data type.

### Data Cleaning
1.	Handling Null values: Premier league happens every year since 1992 and the dataset contains information till the year 2022. The 'Winners' column represents the number of times each club has won the Premier League over the past 30 years. Null values in this column indicate zero wins for those clubs. Similarly, null values in the 'Runners-up' column indicate zero runner-up positions.  
	Therefore, all null values in these columns are replaced with zeroes.
2.	Numerals attached to the names of the clubs in the 'club' column are removed using the 'lstrip()' function.
3.	Data type of the 'Runners-up' column is changed to int using the 'astype' function.
4.	The 'Team launch' column contains dates in two different formats. These formats are standardized, and the column is converted to a single standard format with only years mentioned.
5.	The 'lastplayed_pl' column, which initially indicated the month and year of each club's last appearance in the Premier League, is converted into a year-alone format for further analysis.
- These data cleaning steps are crucial for preparing the dataset for meaningful exploratory data analysis and subsequent decision-making by the investment firm.

### Data Analysis
#### Observations from Overall Statistics 
![Picture2](https://github.com/Naveena-Projects/Exploratory-Data-Analysis/assets/156399143/ea7794e4-b466-4ec5-93f5-e66dd93159b0)

*	Utilizing the 'describe()' method to generate statistics for the entire dataset, it is observed that 75% of the clubs have neither won nor qualified for the finals, indicating a significant number of clubs with limited past success. However, analysing the performance of these clubs is crucial for two reasons: firstly, the top 25% of performers might already be owned by competitive firms, and secondly, one of these clubs might have the potential to succeed in future leagues after strategic investment.
*	The average number of goals scored by all the teams over the years is 769, while the median is 462, indicating some clubs have significantly higher goal-scoring records compared to others.
*	One team has remarkably won 13 times, and another team has been a runner-up 7 times, showcasing outstanding achievements. Upon further investigation, it is revealed that 'Manchester United' is the club with the highest number of wins and runner-up finishes.
*	Additionally, one team has played 1000+ matches, which is twice the average number of matches played by all the teams, indicating a club with extensive historical participation and experience.
*	These observations provide valuable insights into the distribution of success among Premier League clubs and highlight the dominance of certain clubs like Manchester United in terms of achievements. Further analysis can help in identifying possible investment opportunities among the clubs with untapped potential despite historical challenges.
#### Histogram of Total Matches played and its Frequency
![Picture1](https://github.com/Naveena-Projects/Exploratory-Data-Analysis/assets/156399143/c896d9d9-4ad1-43a6-be46-44f4a83d577a)
*	A histogram depicting the total number of matches played by teams along with their respective frequencies has been generated.
*	The histogram reveals that the majority of teams fall within the range of 200 to 400 matches played, indicating a concentration of clubs with a moderate level of historical participation.
*	A noticeable trend is observed where only a few teams have played more than 800 matches. These clubs, having extensive experience with 1000+ matches played, may be considered more established. However, it is crucial to acknowledge that they might probably be owned by competitors. As the investment firm is primarily interested in identifying untapped potential, these highly-experienced clubs can be filtered out for further analysis.

#### Box Plot of Result Rates and Analysis
  ![Picture3](https://github.com/Naveena-Projects/Exploratory-Data-Analysis/assets/156399143/f8296313-87e8-4d15-bc7a-0ed4013827cc)
* After excluding teams that have played more than 900 matches, the dataset is narrowed down to 29 teams. The objective is to identify teams with the potential to succeed in the future.
*	To compare the performances of these teams, average and percentage metrics were calculated.
*	Box plots of winning, losing, and drawn rates were generated to visualize the distribution of these metrics. Outliers in the box plots help identify better-performing teams among the selected 29.
*	Two teams with the highest and one with the lowest winning rates, as well as one team with the highest drawn rate, were identified by calculating quantile and interquartile range (IQR) values.
*	The standard deviation of the average goals in this reduced dataset is zero, indicating that all these teams have scored goals equally. Hence, this metric is of no use in further analysis.
*	Teams that have won or been runners-up were identified, highlighting better-performing teams. However, further analysis is needed to draw conclusive insights.
*	Notably, viewing the 'lastplayed_pl' column reveals that certain teams last played more than 20 years ago. Recommending such teams for investment might be inappropriate due to their prolonged absence from recent league competitions.
*	This analysis, supported by box plots, provides a clear picture of the performance distribution among the selected teams. Outliers and identified metrics contribute to the process of shortlisting potential candidates for investment based on their historical success rates.

#### Final Analysis with Customized Framework
*	To prioritize and give weightage to teams based on their percentage metrics and activeness in the tournaments over the years, a scoring framework is customised as follows:
1. Give a score of 10 if club has a relatively high experience in the Premier League above average
2. Give a score of 15 if club has a winning rate above Q3
3. Give a score of 15 if club has a losing rate below Q1
4. Give a score of 10 if club has a drawn rate below Q1 and a losing rate below Q1
5. Give a score of 10 if club has a clean sheet above Q3 and a winning rate above Q3
6. Give a score of 15 if club has won the premier league
7. Give a score of 10 if club has been a runner-up in the premier league
8. Give a score of 15 if club has been currently playing in the premier league
*	After scoring teams based on these criteria and storing their scores in a newly column created, a bar graph of teams with their scores is plotted.
*	This visualization allows for the identification of clubs with the highest scores, indicating their potential as investment-worthy candidates. The scoring framework considers various aspects of a club's historical performance, current status, and success in Premier League competitions, providing a comprehensive evaluation for the investment firm's decision-making process.
![Picture4](https://github.com/Naveena-Projects/Exploratory-Data-Analysis/assets/156399143/48b4d19d-c498-4a33-b484-2c325242b12e)
*	Upon examining the metrics of the shortlisted teams, it is observed that the highest-scored team, Blackburn Rovers, last played in the year 2012. Consequently, it cannot be recommended for investment due to the extended period of inactivity.
*	To refine the selection and focus on teams active in recent years (2021, 2022, and 2023), a bar graph of scores for these teams is plotted. Based on this analysis, the top scorer is Leicester City. 
![Picture5](https://github.com/Naveena-Projects/Exploratory-Data-Analysis/assets/156399143/86cd7d6f-4db0-4344-89ab-07d1219892f7)

### Recommendation
*	Therefore, the recommendation is to consider investing in Leicester City, as it emerges as the most promising option according to the customized scoring framework. 
*	According to the research, Blackburn Rovers were relegated to the Championship league (i.e., league below Premier League) in 2012 and further to League One (i.e., league below Championship league) in 2017. They were promoted back to the Championship in 2018 but have since finished in the middle of the table in recent years. Given their inconsistent performance and lack of presence in the Premier League since 2012, it would be inappropriate to recommend this club for investment.
*	On the other hand, Leicester City, the 2016 Premier League champions, has consistently finished in the top 10 in recent years. They placed 5th in both the 2019-2020 and 2020-2021 seasons and finished 8th in 2021-2022. Leicester City has the potential to achieve even greater success in the near future. Therefore, it would be reasonable to recommend the club Leicester City.
* ***Supportive Resources:***
  * *Source-1 Blackburn Rovers History:* https://www.transfermarkt.co.in/blackburn-rovers/platzierungen/verein/164
  * *Source 2-Leicester City History:* https://www.transfermarkt.co.in/leicester-city/platzierungen/verein/1003
* These sources provide additional details about the performance histories of Blackburn Rovers and Leicester City, aiding in the decision-making process for potential investment.

