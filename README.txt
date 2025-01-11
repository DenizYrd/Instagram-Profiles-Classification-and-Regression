Please include the necessary datasets, inputs in the same folder as the given notebook. The datasets used in the project sadly couldn't be uploaded here as they are a property of Sabancı University.

There is a section in regression part where the model requires the TF-IDF vectorizers to be downloaded onto your computer. This isn't an large file if the dataset isn't above 250k+ account. However, in our dataset, 2 of the tf-idf vectorizers were empty as their "combined text" was only stop words which were deleted.

That's why we added 2 additional vectorizers with the notebook. After the part where the code says to put the vectorizers in the tfidf_vectorizers folder, please put them so.

The code has been commented to ensure the understanding and easy use. The code is divided into two subsections, one utilizing profile and the other using the posts dataframe given.

In our classification code, some certain things can be observed such as:

Given some accounts with unusual categories (for our instance, this was gaming), since their appearence was around %2, there weren't enough data to train and test it much more, comparing with other categories.

Generally, the categories which were most predominant were the easiest to categorize. 

In regression, no model can be perfect as the Instagram algorithm is an extremely complicated algorithm where a post may be trending or not show up in any feed of the users by a very complex process.

However, we still tried to look at the data and our model adjusts itself into a more correct value reading the inputted captions, comments counts etc. to find an accurate predicted like count, similarly to the categorization (classification) problem.

In our classification part of the code, we were able to divide the data into distinct test and training datas, test and find an accuracy score as there are a limited number of categories. In our regression part though, we have created many matrices with the username of the user as its name (as many as the dataset has). 

However, instead of calculating the like count on the entire column and testing it (unlike classification), our model only looks at the last row of the certain matrix, which can be at most 35 rows long. 

Our code makes the non existant like count to be NaN and tries to predict the like count without deleting the other posts like counts, as they are extremely vital for our code to work and give the most information gain (as expected) of all the data in the posts. Since this is the case, we cannot distinctly split our data into training and testing, we had to resort to manual checks whether our model works good or not. 

If the user has no previous posts, we don't have anything to compare the likes or captions to any other thing, so we just predict like count = 0 for these. However, this was rarely the case in our dataset.

Both regression and classification tasks utilize data manipulation using pandas first. They are fitted together with the datasets dataframe and joint together, where the model makes their calculations.

We used different models in regression and classification. While we trained a lot of models, these options gave us the best results according to our precision, recall, accuracies and we finalized on these.

Also, some of the classification data predicted finally has some changes from the model. These were found via observation, where if an account has a government association (mainly, in our case, since the accounts belonged to Turkish people, they had city council accounts, any account usernames that contained "belediye" or "bld" were converted to their correct categories, as all of them should be in the same category, and the model had a hard time fitting them into the correct place, as they are a bit far from the categories given. This is like a manual intervention and many are possible, since these were a lot more and effected our models accuracy, we decided to use this approach to find the solution to the identified problem.

Please contact us if you have further questions.
