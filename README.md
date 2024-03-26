# deep-learning-challenge
## Overview
Alphabet Soup is looking for a better way to determine whether or not their applicants will be successful. The purpose of this analysis is to build a model that will be able to predict whether or not an applicant will be successful if funded by Alphabet Soup. We looked at Alphabet Soup's previous list of customers to create our model. The goal is to be able to predict with reasonable accuracy whether or not an applicant will be successful based on the given parameters. To start this analysis we read in the past applicant history data. We then performed some data client to help with our model. We dropped a few datapoints that weren't helpful for predictive purposes. Some of our datapoints included information that wasn't helpful to our model's performance so we cutoff the data at certain thresholds to create better predictions. We converted our categorical values into numeric representations to allow us to quantify the differences. We then split our data into a features array that held our datapoints we were using to predict, and our target array that held the datapoints to compare our model's performance to. We scaled the data and applied a neural network model using TensorFlow to create our model. We then reviewed our model's results and attempted to optimize the model by implementing various adjustments to the data. 

## Results
1. Target Variables
    - The target variable for this dataset was the is_successful column. 
    - This column let us know whether or not the application was successful and allowed us to compare our model against real data.
2. Feature Variables 
    - That left our features as name, application_type, affiliation, classification, use_case, organization, status, income_amt, special_considerations, and ask_amt as the features we use to create our model.
    - The assignment had me first remove the NAME column, but I found adding it back substantially increased the model's performance. 
    - This would hopefully give us the variables we needed to create our model.
3. Variable(s) to Remove
    - I excluded the EIN and STATUS columns from the dataset as they were mostly names that had little effect on our model and helped improve the model's accuracy.
4. How many neurons, layers, and activation functions did you select for your neural network model, and why?
    - After several attempts 
5. Were you able to achieve the target model performance?
    - I wasn't originally able to achieve the target model performance even after having kerastuner pick the best hyperparameters to use. I had to try a bunch of different feature combinations in order to get it above 75%. Eventually, I figured out that if I added back the NAME column into the features and filtered out the small portion of applications, then I was able to achieve the model performance. 
6. What steps did you take in your attempts to increase model performance?
    - I used several methods to try to increase my model's performance. 
        1. I went throughs several different feature combinations to try and find the features that had a big or no impact. This eventually led to me adding back the NAME feature we had originally removed. 
        2. I tried multiple different neurons combinations to try and figure out if increasing or decreasing did the trick. 
        3. I tried to add and remove different bins to create different groups to look at the data. 
        4. I added multiple hidden layers to try to improve the model's performance. 
        5. Finally, I tried using kerastuner to pick the optimal number of neurons and hidden layers. 

## Summary
In the end, there were several different variables that impacted the model's results. Given the starter instructions the highest accuracy I was able to get was just over 73%. The target for this assignment was 75% so this was still below the target. The first thing I looked into was dropping some of our other features we had in the data. This didn't yield any large results so I added back some features that we had initially removed. Adding the NAME feature back ended up netting me the highest accuracy. Once I figured out the optimal feature set I adjusted the number of neurons and hidden layers in the model to try and impact the performance. I didn't see any large increases or decreases in performance so I had the kerastuner pick the optimal set of hyperparameters for me. This gave me the best parameters to use which were: relu as the activation, 5 hidden layers, with 220 neurons total (1st layer = 11, 2nd layer = 26, 3rd layer = 16, 4th layer = 151, 5th layer = 16). The final accuracy score with these hyperparameters was roughly 78.38%.

