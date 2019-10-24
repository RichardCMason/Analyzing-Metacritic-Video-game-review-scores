# Analyzing-Metacritic-Video-game-review-scores
### Problem Statement
The goal of this project was to analyze the aggregate review site, metacritic.com. <https://www.metacritic.com/>.  As someone whos always been interested in video games, I thought it would be interesting to see how game review scores had varied over time, and if there was any difference between "Critic Scores," and "User Scores".  

Critic Scores are scores given by professional video game journalist and review sites, and a combination of critic scores (proprietary formula) is the overall score reported by metacritic.  However, the site also allows users with an account to also leave a review.  So a combined "user score" is also reported.  

### Process
The first step in this project was to scrap the metacritic website to acquire their database of review scores.  After building a scraper and several hours later, and after appropriate data cleaning, my dataframe looked like this: 
![Metacritic Dataframe](https://github.com/RichardCMason/Analyzing-Metacritic-Video-game-review-scores/blob/master/Images/Full_dataframe.png)

During my analysis I made an interesting discovery: That while review scores had been declining steadily since the mid-90s for both users and critics, critic scores had stabilized around 2007, whereast user scores continued to decline(and still are).
![Critic scores time](https://github.com/RichardCMason/Analyzing-Metacritic-Video-game-review-scores/blob/master/Images/critic_score_time.png)

![User scores time](https://github.com/RichardCMason/Analyzing-Metacritic-Video-game-review-scores/blob/master/Images/user_score_time.png)

### Regression to predict review scores
I found this apparent discrepancy very interesting, so I focused the rest of my analysis on why this difference was occuring.  At first I ran both a linear regression with Lasso regularization and random forest regression with critic scores and user scores the targets.  Here are the coefficients of important features from those analyses:

![Critic regression](

![User Regression](

### NLP analysis to provide insight into "interesting words" 
