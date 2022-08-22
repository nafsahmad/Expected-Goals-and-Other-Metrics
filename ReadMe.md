# THIS IS THE PREMIER PROJECT FOR THE MULTI - COLLINEARITY GROUP OF HDSC SUMMER 2022

## An Analysis of UEFA Leagues from 2014/2015 Season To 2019/2020 Season and Predicting Team's Qualification to the UEFA Champions League.

### Problem Statement:

How does the playing style of a team affect their performance in Europe?
## Data Summary:

The data had 684 observations for 24 features of teams in 6 leagues across Europe. These teams are part of leagues in European countries and the leagues are all members of the Union of European Football Associations (UEFA).

These observations reflected the performance of the teams across a period of 6 seasons beginning in the 2014/2015 season and ending in the 2019/2020 season.

Fortunately, there were no missing values in the dataset and so not much work was required in that aspect of the data cleaning process. Nevertheless, we had to label some unnamed columns and also change the names of certain columns to make them more descriptve of the values which they contain.

**Data Source:** [kaggle](https://www.kaggle.com/datasets/slehkyi/extended-football-stats-for-european-leagues-xg?select=understat.com.csv)

### Leagues Analyzed:

- La Liga
- EPL
- BundesLiga
- Serie A
- Ligue 1
- RFPL

### EDA:

It is worth noting that a higher ppda_coef implies a lower power of pressure. Some key insight from our data analysis include:


![alt text](/Visualizations/points_dist.jpg)

- **Insight:** Of the 33769 points picked up in this period, the EPL, La liga and Serie A contributed an equal equivalent of 19% each.

- **Insight:** The RPFL contributed the only 4000 points (12%) of the overall sum.

- **Insight:** __Serie_A__, __La_liga__ and __EPL__ has the highest participation over the period (30 teams), followed by __Ligue_1__ (29 teams), then __RFPL__ (25 teams) and __Bundesliga__ (24 teams). 

***Question:** Could the number of teams have contributed to the number of points won?*

![alt text](/Visualizations/avg_points_plot.jpg)

- **Insight:** On average, the RFPL teams won fewer points than those in other leagues.

- **Insight:** Leagues maintain the same range in total points won during the seasons. Also, we see RPFL falling behind in total number of points won.

![alt text](/Visualizations/goals_dist.jpg)

- **Insight:** All the leagues have comparable goal distributions among their teams. Except the RFPL which seems to fall behind on this parameter.

- **Insight:** Goal-loving football fans would be drawn away from the RFPL.

![alt text](/Visualizations/corr_ppda_pts.jpg)

- **Insight:** There is a positive correlation between the ppda_coef of a team and the number of deep passes they allow their oponents to make. There is also positive correlation between the number of deep passes a team allows to the the goals they get. Finally, there is a negative correlation between the goals a team concededs and the number of points they get.

- **Insight:** Finally, a negative correlation can be seen between the ppda_coef and the number of points a team gets. Since we know that applying higher pressure means a lower ppda_coef and the more points a team, the more lkely they are to be successful in Europe. It is safe to conclude that teams that do not apply higher pressure (which leads to higher ppda_coef) would end up less successful than their counterparts who do.

### Machine Learning Models:

We implemented a machine learning model to predict the if a team  would qualify for the UEFA Champions League by considering their style of play (if they are a high pressing side or not) and the league to which they belong.

Two models were used for this implementation. 

**Linear regression model:**

- *Accuracy Score:* 0.94 (on test data)

- *Confuson Matrix:* 
  ![alt text](/Visualizations/linear_model_ConfusionMatrix.png)

**Decision Tree Model:**

- *Accuracy Score:* 0.94 (on test data after hyperparameters tuning)

- *Confusion Matrix:* 
  ![alt text](/Visualizations/tuned_tree_model_ConfusionMatrix.png)

We deployed the models as two sepearate binary files using the "pickle" Python model. With this deployment, the model's can be loaded for use in any scenario using "pickle.load" function.

### Caveats:

- Analysis and the derived insights are only as accurate as the dataset would permit.
- Neither Hamoye nor any members of the Multi-collinearity group bear any liabity for decisions and/ or losses resulting from actions made based on this analysis.
