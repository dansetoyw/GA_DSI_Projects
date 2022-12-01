# ![](https://ga-dash.s3.amazonaws.com/production/assets/logo-9f88ae6c9c3871690e33280fcf557f33.png) Project 3: Web APIs & NLP on Subreddit (CatAdvice & DogAdvice)

### Problem Statement

An influx of inexperienced pets owners overly reliant on vets and pet store reduces work efficiency, how can we optimize it?

Our flagship product (Pet Companions), our highly-rated mobile application offering pet owners information through:
- AI-powered chatbot 
 - First level of customer inquiry
 - Source of information for pet owners
- Recommends articles based on classification of queries
- A knowledge-bank filled with information sourced from vets, pet experts and users

However, our chatbot requires an update to increase its effectiveness in order to meet higher demand.

Using web apis and NLP to create an improved classifier model to better classify posts to cats and dogs and recommend information to pet owners accordingly.

### Datasets

#### Data Source
Source: Pushshift Reddit API 

* [`pet_adv_cleaned.csv`](./data/pet_adv_cleaned.csv): Contains posts from r/CatAdvice and r/DogAdvice with and without cleaning

#### Data Dictionary

|Feature|Type|Dataset|Description|
|---|---|---|---|
|subreddit|*object*|pet_adv_cleaned|The name of the subreddit / data source (either r/CatAdvice or r/DogAdvice)|
|category|*object*|pet_adv_cleaned|The post's category tag obtained from the web subreddit|
|title_selftext|*object*|pet_adv_cleaned|The post's original text which includes the post's title and comment|
|cleaned_text|*object*|pet_adv_cleaned|The cleaned text of the post's title and comment|
|subreddit_target|*int*|pet_adv_cleaned|The numerical tag of the name of the subreddit/data source (1 refers to r/CatAdvice while 0 refers to r/DogAdvice)|

### Key Analysis

##### Comparing Multinomial Naive Bayes, Bernoulli Naive Bayes and Logistic Regression model with KKN as baseline model


|     Model                              | CountVectorizer | Accuracy Score for train | Accuracy Score for test | F1 score |
|-|-|-|-|-|
| KNN (Baseline)                         | Tf-idf          | 0.8655                   | 0.7815                  | 0.7895    |
| MultiNB                                | Tf-idf          | 0.9560                   | 0.8902                  | 0.8915    |
| MultiNB                                | unigram         | 0.9581                   | 0.9022                  | 0.9002    |
| MultiNB                                | bigram          | 0.9997                   | 0.8402                  | 0.8477    |
| BernNB                                 | Tf-idf          | 0.9636                   | 0.9000                  | 0.8978    |
| BernNB                                 | unigram         | 0.9636                   | 0.9000                  | 0.8978    |
| BernNB                                 | bigram          | 1.0                      | 0.8250                  | 0.8156    |
| Logistic Regression                    | Tf-idf          | 0.9601                   | 0.8859                  | 0.8805    |
| Logistic Regression                    | unigram         | 0.9997                   | 0.8804                  | 0.8786    |
| Logistic Regresion                     | bigram          | 1.0                      | 0.7815                  | 0.7599    |    
| **MultiNB with hyperparameter tuning** | **unigram**     | **0.9033**               |**0.9043**               |**0.9016** |


- Multinomial Naive Bayes model with unigram CountVectorizer gave the best performance with accuracy score for train and test datasets as well as F1 score above 90%. This model has also shown a lesser degree of overfitting on the train dataset because it has smaller gap between the train and test accuracy score.
- Further optimisation was conducted to the model by tuning the hyperparameters. It has closed the gap between the train and test's accuracy score as well as resulted in a slight increase in the test's accuracy score and F1 score. The model has achieved a high accuracy score of 90%, which is 12% higher than the current model using K_nearest neighbors.

Top 10 words for cats:
- meowing          
- meow             
- resident         
- litterbox        
- feliway          
- tabby            
- diffuser         
- galaxy           
- jackson          
- swat             

Top 10 words for dogs:
- bark            
- flea            
- diarrhea        
- infection       
- daycare         
- trainer         
- treatment       
- collie          
- poodle          
- terrier         

##### Interpretation
-- Cat
- The top 10 words for cats are mainly related to cat behaviours such as meowing and swat. Swat could be due to cat's redirect aggression, playfulness or them trying to get your attention. 
- Cats use litterbox whereas dogs may use potty or they do their business outdoor. 
- Jackson Galaxy is a famous Youtuber and an American cat behaviourist who is a specialist in managing the behavior of cats. 
- Feliway diffuser is a product that helps reduce signs of stress in cats.
- Tabby is a type of cat with a 'M'-shaped marking on its forehead. 

-- Dog
- As for the top 10 words for dogs, they are mainly related to behaviors and medical conditions. 
- Collie, poodle and terroer are unique words for dog types. 


From these top words, it is unexpected that resident and daycare are strong predictors of cat and dog respectively. These appear to be common words that can be used for both cats and dogs. Perhaps, it is because some dog owners are worried to leave their dogs home alone all day, while cat owners feel safe to leave their cats at home as their cats will cope on their own. 

In summary, these top words are relatively distinct to dogs and cats and hence, it has contributed to the high model accuracy. 

### Conclusion and recommendation:

- Multinomial Naive Bayes achieves 90% accuracy score and F1 score, which is 12% higher than the current KNN model. This will help to better meet the increasing demand. Recommend the upgrade of the application's chatbot from the current KNN model to Multinomial Naive Bayes.
- With the upgrade of the app, we can potentially implement options for customers to highlight if they have been directed to the wrong resources. At the same time, we can collect user's interaction data to further improve our application's accuracy and customer's satisfaction.
- As we build up the database with the increasing customer base, we will also like to recommend having analysis conducted on the commonly asked questions and build up resources to automate replies.
