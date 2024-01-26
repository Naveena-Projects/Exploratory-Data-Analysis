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
> *Unauthorised use or distribution of this project is prohibited (@dataanalystduo).*
> *The dataset has been acquired from multiple sources on the internet.*
> *Credits for the dataset go to the original creator of the data.* 
> *This data is updated as of March'23*

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
1.	Handling Null values
-	Premier league happens every year since 1992 and the dataset contains information till the year 2022. The 'Winners' column represents the number of times each club has won the Premier League over the past 30 years. Null values in this column indicate zero wins for those clubs. Similarly, null values in the 'Runners-up' column indicate zero runner-up positions.  
-	Therefore, all null values in these columns are replaced with zeroes.
2.	Removing Numerals from Club Names:
-	Numerals attached to the names of the clubs in the 'club' column are removed using the 'lstrip()' function.
3.	Converting data type
-	 Data type of the 'Runners-up' column is changed to int using the 'astype' function.
4.	Standardizing 'Team Launch' Column:
-	The 'Team launch' column contains dates in two different formats. These formats are standardized, and the column is converted to a single standard format with only years mentioned.
5.	Converting 'lastplayed_pl' to Year-Only Format:
-	The 'lastplayed_pl' column, which initially indicated the month and year of each club's last appearance in the Premier League, is converted into a year-alone format for further analysis.
These data cleaning steps are crucial for preparing the dataset for meaningful exploratory data analysis and subsequent decision-making by the investment firm.
Data Analysis
Observation from overall Statistics 


