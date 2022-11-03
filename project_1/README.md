# ![](https://ga-dash.s3.amazonaws.com/production/assets/logo-9f88ae6c9c3871690e33280fcf557f33.png) Project 1: Standardized Test Analysis

### Problem Statement

Should United States' (US) standardised college readiness tests' (i.e. American College Testing, ACT and SAT) results be included as the measures for the ranking of the best States for education?

ACT and SAT results are often included in the methodology to rank the States' education system. Some examples of the online publications on ranking of the best States for education are 'Education Rankings - Measuring how well states are educating their students' by USNew ([*source*](https://www.usnews.com/news/best-states/rankings/education/prek-12)), 'Best States for Education 2022' by World Population Review ([*source*](https://worldpopulationreview.com/state-rankings/best-states-for-education)) and 'States with Best & Worst Public School' by Scholaroo ([*source*](https://scholaroo.com/report/state-education-rankings/)).

It is important for media to provide accurate reports. Misinformation may lead to losing credibility from viewers as well as affecting wrong decision. 

The inclusion of standardised college readiness tests' results in the ranking methodology is of concern due to low and declining participation percentage of these tests which may affect the report's accuracy. In the this study, we explore the participation trend and correlation between the participation percentage and the test's score for ACT and SAT.

### Datasets

#### Data Source
* [`act_2017.csv`](./data/act_2017.csv): 2017 ACT Participation and Scores by State ([*source*](https://www.act.org/content/act/en/research/reports/act-publications/condition-of-college-and-career-readiness-2017.html))
* [`act_2018.csv`](./data/act_2018.csv): 2018 ACT Participation and Scores by State ([*source*](https://www.act.org/content/dam/act/unsecured/documents/cccr2018/National-CCCR-2018.pdf))
* [`act_2019.csv`](./data/act_2019.csv): 2019 ACT Participation and Scores by State ([*source*](https://www.act.org/content/dam/act/unsecured/documents/National-CCCR-2019.pdf))
* [`sat_2017.csv`](./data/sat_2017.csv): 2017 SAT Participation and Scores by State ([*source*](https://blog.collegevine.com/here-are-the-average-sat-scores-by-state/))
* [`sat_2018.csv`](./data/sat_2018.csv): 2018 SAT Participation and Scores by State ([*source*](https://blog.collegevine.com/here-are-the-average-sat-scores-by-state/))
* [`sat_2019.csv`](./data/sat_2019.csv): 2019 SAT Participation and Scores by State ([*source*](https://blog.collegevine.com/here-are-the-average-sat-scores-by-state/))

#### Data Dictionary

|Feature|Type|Dataset|Description|
|---|---|---|---|
|**state**|*object*|act_sat_pt_score|The names of the states and federal district in United States of America|
|**act17_participation**|*float*|act_sat_pt_score|The percentage of year 2017 high school graduates participated in ACT by state (units percentage in decimal to 2 decimal places. 0.98 means 98%|
|**act17_composite**|*float*|act_sat_pt_score|The average ACT composite score obtained by year 2017 high school graduates by state (values ranging from 1 to 36)|
|**act18_participation**|*float*|act_sat_pt_score|The percentage of year 2018 high school graduates participated in ACT by state (units percentage in decimal to 2 decimal places. 0.98 means 98%|
|**act18_composite**|*float*|act_sat_pt_score|The average ACT composite score obtained by year 2018 high school graduates by state (values ranging from 1 to 36)|
|**act19_participation**|*float*|act_sat_pt_score|The percentage of year 2019 high school graduates participated in ACT by state (units percentage in decimal to 2 decimal places. 0.98 means 98%|
|**act19_composite**|*float*|act_sat_pt_score|The average ACT composite score obtained by year 2019 high school graduates by state (values ranging from 1 to 36)|
|**sat17_participation**|*float*|act_sat_pt_score|The percentage of year 2017 high school graduates participated in SAT by state (units percentage in decimal to 2 decimal places. 0.98 means 98%|
|**sat17_total_score**|*int*|act_sat_pt_score|The average SAT total score obtained by year 2017 high school graduates by state (values ranging from 400 to 1600)|
|**sat18_participation**|*float*|act_sat_pt_score|The percentage of year 2018 high school graduates participated in SAT by state (units percentage in decimal to 2 decimal places. 0.98 means 98%|
|**sat18_total_score**|*int*|act_sat_pt_score|The average SAT total score obtained by year 2018 high school graduates by state (values ranging from 400 to 1600)|
|**sat19_participation**|*float*|act_sat_pt_score|The percentage of year 2019 high school graduates participated in SAT by state (units percentage in decimal to 2 decimal places. 0.98 means 98%|
|**sat19_total_score**|*int*|act_sat_pt_score|The average SAT total score obtained by year 2018 high school graduates by state (values ranging from 400 to 1600)|

### Key Analysis

- With the low average participation percentage of below 65% for both ACT and SAT, neither of the tests is a good representation of the high school graduate's performance for the respective states.
- The lower the participation for ACT, the higher the average ACT composite. The test result appeared to be skewed towards higher score with lower participation. This is shown in states such as Kentucky, Nebraska and Wisconsin. Could be due to only elite students taking the SAT examination for these states.  Hence, ACT scores might not be a good representation of the high school graduate's performance for state's with low ACT participation.
- The lower the participation for SAT, the higher the average SAT total score. The test result appeared to be skewed towards higher score with lower participation. This is shown in states such as Michigan, Rhode Islanda and Delware. Could be due to only elite students taking the ACT examination for these states.  Hence, SAT scores might not be a good representation of the high school graduate's performance for state's with low SAT participation.

### Conclusion and recommendation:
- Both ACT and SAT scores are not good representation of the high school graduate's performance for states. 
- With this, ACT and SAT should not be included as the measures for the ranking of the best States for education.
