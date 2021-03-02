  # Background on code files
  - Please consult FinalProject.ipynb for all sections and data for this project. Results, Interpretation, and Reflection are also included below and within the notebook
    - jupyter notebook using python and sklearn
  - Dataset from https://www.kaggle.com/jsphyg/weather-dataset-rattle-package (24 features, 8466 samples when only using 2017 data)
  - Models used:
    - Scikit Learn classifiers: Logistic Regression, SVC, Gaussian NB, Random Forest Classifier, Gradient Boosting Classifier

  # How to run
  Please see links below for installing the necessary dependencies for this notebook:
  - Dependencies:
    - Sklearn:  https://scikit-learn.org/stable/install.html
    - Pandas:   https://pandas.pydata.org/pandas-docs/stable/getting_started/install.html
    - Numpy:    https://numpy.org/install/
    - Seaborn:  https://seaborn.pydata.org/installing.html
    - Matplotlib: https://pypi.org/project/matplotlib/

  - Ensure the `weatherAUS2017.csv` is in the working directory of the notebook when running the notebook. *Available in the root directory of the repo*
  
  After those are installed, simply run all the cells in the order of the notebook and you should be good to go!

# Results

Below are the final scores for all three of the models after tuning them to their best hyperparameters and testing on the unseen test data:

### GradientBoostingClassifier
* Precision = 0.82
* Recall = 0.72
* F1-score = 0.75
* FP = 141
* FN = 44

### RandomForestClassifier
* Precision = 0.81
* Recall = 0.75
* F1-score = 0.78
* FP = 120
* FN = 59

### SVC
* Precision = 0.81
* Recall = 0.73
* F1-score = 0.76
* FP = 137
* FN = 47

# Interpretation
## Best model
It is clear from the results that all three of the best models yield very similar performance. Their F1 scores are only separated by 0.03 from the highest to the lowest score which is quite close to each other. In order to decide upon which model is the best out of these three, I am focussing in on how many false negative predictions each of the models are making. 

I am focussing on the false negatives as I think that this is the worse scenario out of the two potential false predictions, as it would be less than ideal if you are using this model to predict the weather and then it predicts there is no rain, so you leave all your rain gear at home, to only find that it has begun raining. Whereas it predicts that it will rain, and it doesn't, the only real harm is that now you brought your umbrella to work but do not have to end up using it. I think that I personally would prefer that to happen than be caught without my rain gear when the rain is coming. So, with that in mind, I feel the best of these three models should be the one that is making the least amount of mistakes. 

I could also tune them to have a higher threshold like we did in Lab 3 to reduce the amount of false negatives, but I feel this project is already quite long and I explored these models quite in depth, and I think I will leave experimenting with a higher threshold for future work. Furthermore, of the 1320 predictions made by each model, the ranges of false negatives are only 120-141, which is 9% - 11%. In this scenario since the absolute worst case scenario is the models thinks it wont rain and it does, the consequences really are not that dire, so I think that this is an acceptable performance, but like anything, there is always room for improvement.

So, based on that criteria, I conclude that the best model for this data set and predicting whether or not it will rain tomorrow is the *RandomForestClassifier* since it yields the highest f1-score of 0.78, alongside making the least amount of false negative predictions, which totalled 120. 


## Overall interpretation

Overall, I was quite surprised by how similar the performance is between the three models, this is quite interesting to me as it seems all of them generalize to roughly the same performance. Even more interesting was how despite whatever hyperparameters were selected for the RandomForestClassifier, the performance was almost identical to the default model. 

I am not quite sure what is causing this at this point, could potentially have something to do with how I pre-processed the data, or it could just be the way this data set is when used for machine learning. I think that this is something that I will have to re-visit in the future when I am more confident and have more experience with machine learning. 

My plan was to explore how machine learning can be used to make accurate weather predictions based on historical data. Of the 5 initial models I was exploring, I have found three models all within very close performance of one another that are up for the task of predicting whether or not it is going to rain in Australia tomorrow. 

Although they are not perfect, I believe that they could be used as a quick check in the morning if you need to pack an umbrella or not. After completing this project, I believe that it shows machine learning can be utilized on historical weather data to make some accurate predictions on unseen data. I am also sure that this is something that is actively being used around the globe today since there is such a vast amount of weather data that can be harvested for this task. 

I do find this fascinating that we can use historical labelled data, and these algorithms, to make quite accurate predictions about something that changes as often as the weather. I think that this project helped me gain some more confidence in exploring new areas to apply machine learning, as well as discover some other interesting facets that need to be investigated further!


# Reflection
In retrospect, I feel I learned quite a bit from this lab. Having the mixture of categorical and numerical data helped me get more of a feel for what is required when wrangling datasets, furthermore, dealing with data sets with many null values. I also feel much more comfortable grid searching and interpreting the results from those grid searches. I am still a bit perplexed as to why the RandomForestClassifier seems to reach almost the same levels of performance regardless of hyperparameter selection/tuning, but as mentioned previously, this is definitely a take away for me and will definitely circle back to try and determine an answer in the future!

With regards to the proposal, since I was using lab 3 as a roadmap, I followed the general structure/flow of that lab to explore this data and train machine learning models for the weather prediction. Where I deviated from the lab was during the grid searching portion, as in the lab, we only had to grid search once for each model where we ended up getting results that were in the middle of our grid search and yielded good performance. 

I ran into the issues of having models that were overfitting the data by quite a bit, and almost always having the grid searches end up selecting values that were right at the edge of the search - meaning I should expand it, however this led to almost identical results in the case of the RandomForestClassifier, and only a very marginal improvements in both SVC and the GradientBoostingClassifier. 

After experimenting with different hyperparameter's and ranges, I settled in on the performance of the models but then noticed that all of them were almost identical in their overall performance. Another very interesting facet. One that I also am not 100% sure on what would cause this to be the case, again, some more food for thought in the future. 

I also deviated a bit from the lab 3 at the end as I did not feel it was necessary in this case to fine tune the threshold since the consequences of the model making a mistake really are not that dire. Worst case scenario it is an inconvenience to get caught in the rain without your rain gear, but it certainly could put a damper on the day!

In summary, I feel I explored and created 3 models that have decent performance at predicting whether or not it will rain tomorrow in Australia. This was a great learning experience and I look forward to exploring more datasets and models in the future!

