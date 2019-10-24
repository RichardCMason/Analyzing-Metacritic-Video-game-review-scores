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

The features that had the biggest *positive* impact on critic review score
<img src = https://github.com/RichardCMason/Analyzing-Metacritic-Video-game-review-scores/blob/master/Images/Top_Critic_features.png width = 400>

And the features that had the biggest *negative* impact on user review score
<img src = https://github.com/RichardCMason/Analyzing-Metacritic-Video-game-review-scores/blob/master/Images/Worst_User_features.png width = 400>

I realized the key insights for this project were hidden in the actual text of the critic and user reviews.  So I went about extracting the words that had the most impact on critic scores and user scores, respectively.

### NLP analysis to provide insight into "interesting words" 
After running a bag of words model with regularization, here were the words most indicative of a positive critic or user review:

<img src = https://github.com/RichardCMason/Analyzing-Metacritic-Video-game-review-scores/blob/master/Images/Top_critic_words.png width = 400>

<img src = https://github.com/RichardCMason/Analyzing-Metacritic-Video-game-review-scores/blob/master/Images/Top_User_words.png width = 400>

I decided to make another feature, called "interesting words," which are the words whose coefficients were *most* different between critics and users, i.e. their points of disagreement:

<img src = https://github.com/RichardCMason/Analyzing-Metacritic-Video-game-review-scores/blob/master/Images/Interesting_words.png width = 400>
