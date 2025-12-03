# Kaggle-Titanic-Notebooks

Titanic (and the space variant) competitions are beginner-friendly, meant to introduce prediction modelling to participants on top of encouraging good data science practices. The notebook on Titanic is guided (Based off an existing notebook that introduces the challenge and unfortunately, spoon-fed the solution) whereas Space Titanic is done blind without any external references. The best submissions for the titanic and space titanic challenges are 0.789 and 0.791 respectively. Both challenges' best submissions came from the gradient boosted algorithm from the YDF library.

## Space Titanic
# Exploratory Data Analysis
Since response variable (Transported) is categorical, we used Seaborn's count plot and box plot to compare it against categorical and quantitative explanatory variables respectively. For cabin number, we note that there are 3 different numbers/letters separated by "/", so we decided to split them up and investigate if there could be potentially any relationship with it and the response variable. VIP and Destination contain NaN values, so we change the Nan values to false by default. After performing EDA, we chose to use CryoSleep, Spa, RoomService, VRDeck, FoodCourt, ShoppingMall, Age and first number of the cabin number in our model. We do note that the the correlation between the chosen explanatory variables and the response variables are weak (less than 0.2). This strongly suggest that we cannot use linear modelling to capture the relationship between the explanatory variables and the response variable and non-linear methods are preferred.


# Models
We start off using YDF library's gradient boosted model since it is the most convenient to set up. Accuracy reported by YDF is 0.791, which lined up exactly with the submission result. Since YDF gives less control for the programmer to change certain parameters with the model, we also set up random forest and gradient boosted model from sklearn. After playing around with the different parameters, we found that the default parameters still gave the best results. Only notable thing that improved the model is decreasing the max height of the trees to 5. Both models gave a prediction accuracy of 0.788 by Kaggle, which suggests that there are still room for improvement with the parameters chosen. Since random forest performed just as well as gradient boosted which the latter is supposed to be more accurate, we can infer that something can still be improved to boost performance. 


# Future Exploration
Definitely gain more confidence to play more complex Kaggle chalenges (Likely more repositories containing notebook submissions for Kaggle to come)

YDF and even SKLearn does the tree model creation and training on their own, giving very little insights into how these models even work in the first place and if so, how to modify them to fit specific needs. Since decision trees are still unchallenged in ML algoritms as of writing, a deeper look into decision tree algorithms and how they work will be insightful.

Polars is Pandas 'replacement' and can consider learning Polars instead. 
