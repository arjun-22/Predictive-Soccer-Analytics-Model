# Soccer Match Prediction Model

As part of my computer science research class during my junior year of high school, I created a machine learning model to predict the outcomes of soccer matches based on team lineup and formation data. At a high level, I endeavored to quantify team ability and formation in order to predict whether they would win, draw, or lose a match against another team. 

In order to quantify player ability, I utilized the videogame FIFA, which quantifies players through ratings based on their skill and physical attributes. I then created aggregated goalkeeper, defense, midfield, and offensive rating features for each team, which were calculated by averaging the player ratings within each position grouping. In order to quantify team formation, I created depth, defensive width, midfield width, and offensive width features for each team calculated based on each formation. For example, the formation 4-3-3, which consists of four defenders, three midfielders, and three attackers, would be represented by a depth feature of three as there are three discrete sections of players, a defensive width feature with of four as there are four defenders, a midfield width of three as there are three midfielders, and an offensive width of three as there are three attackers. 

In order to represent an individual soccer match, I created nine features between the two teams. 
1. NET DEPTH: calculated by subtracting the away team’s depth from the home team’s depth. 
2. NET DEFENSIVE RATING: calculated by subtracting the away team’s offensive rating from the home team’s offensive rating
3. NET MIDFIELD RATING: calculated by subtracting the away team’s midfield rating from the home team’s midfield rating
4. NET OFFENSIVE RATING: calculated by subtracting the away team’s defensive rating from the home team’s offensive rating
5. HOME GOALKEEPER RATING: the rating of the home team's goalkeeper rating
6. AWAY GOALKEEPER RATING: the rating of the away team's goalkeeper rating
7. NET DEFENSIVE WIDTH: calculated by subtracting the away team’s offensive width from the home team’s defensive width
8. NET MIDFIELD WIDTH: calculated by subtracting the away team’s midfield width from the home team’s midfield width
9. NET OFFENSIVE WIDTH: calculated by subtracting the away team’s defensive width from the home team’s offensive width

To create the nine features, I used a dataset of lineups and formations from 3040 Premier League matches between the 2008 to 2015 and a dataset of FIFA player ratings from FIFA 09 to FIFA 16. Subsequently, I created three classes: 0 to represent a loss from the home team’s perspective, 1 to represent a draw, and 2 to represent a win from the home team’s perspective. I then used a multinomial logistic regression classifier to predict match outcomes based on the feature set, initially achieving an overall accuracy of fifty percent, which is significantly greater than the expected thirty-three percent prediction accuracy for the three classes. After using recursive feature elimination, I ranked the features in order of impact on the match outcome prediction. The model revealed that the net midfield rating is the most impactful, which is in line with real-life soccer analytics that suggests that midfield is the most important aspect of a soccer team.

The dataset is linked here: https://www.kaggle.com/datasets/hugomathien/soccer
