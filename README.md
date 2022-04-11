# Automate-project-approvalApply Multinomial NB on these feature sets
Features that need to be considered
essay
while encoding essay, try to experiment with the max_features and n_grams parameter of vectorizers and see if it increases AUC score.
categorical features
- teacher_prefix
- project_grade_category
- school_state
- clean_categories
- clean_subcategories
numerical features
- price
- teacher_number_of_previously_posted_projects
while encoding the numerical features check this and this

Set 1: categorical, numerical features + preprocessed_eassay (BOW)

Set 2: categorical, numerical features + preprocessed_eassay (TFIDF)

The hyper paramter tuning(find best alpha:smoothing parameter)
Consider alpha values in range: 10^-5 to 10^2 like [0.00001,0.0005, 0.0001,0.005,0.001,0.05,0.01,0.1,0.5,1,5,10,50,100]
Explore class_prior = [0.5, 0.5] parameter which can be present in MultinomialNB function(go through this ) then check how results might change.
Find the best hyper parameter which will give the maximum AUC value
For hyper parameter tuning using k-fold cross validation(use GridsearchCV or RandomsearchCV)/simple cross validation data (write for loop to iterate over hyper parameter values)
You need to plot the performance of model both on train data and cross validation data for each hyper parameter
