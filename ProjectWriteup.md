# Looking at Linguistic Markers in Pitchfork Album Reviews 
Caroline Shi

## Abstract
I explore the capabilities of NLP in regards to music album reviews. Pitchfork, an online music publication, is well known for their reviews -- they are notorious for their unpredictable and finnicky reviews scaled for a maximum of 10 points. Many would agree that Pitchfork has held considerable influence and regard in the music world at one point or another, particularly with independent music. 

After performing some topic modeling on my entire dataset of 18,000 reviews, I built a Random Forest regressive model to see if I am able to train my data to accurately mirror Pitchfork's scores. I set out to see if there are any particular words or topics that indicate whether or not an album will receive a positive or negative review from Pitchfork or if there were any particular topics or words that were unique to specific music genres. 

## Design 
The goal of this project was to build an unsupervised learning model that looked to find structure and topics within Pitchfork album reviews. I tried topic modeling three ways: TF-IDF Vectorizer with NMF, Count Vectorizer with LDA, and CorEx-- TF-IDF/NMF gave me the clearer, more interpretable topics. I collected a total of 10 topics; the topics I got addressed music genres, type of album release, sentiments and emotions, and specific artists or bands that were reviewed a significant # of times. I tried using the topics as features in a regressive model to predict album review score. Incorporating a few more features such as album release date, review release date, and dummified genre columns along with my 10 topics, I got a relatively high R-Squared score of 0.87 with a RMSE of 0.47 using Random Forest on my val set but a drastic drop to 0.12 for my R-Squared when testing my test set. The extreme overfitting of my model is something interesting to look into further. 

I also did some topic modeling on just Rock genre reviews to see if I was able to draw out more nuanced topics. When running TF-IDF/NMF on Rock reviews, the topics seemed to be compromised of sub-genres of rock. I ran a Random Forest regressor on this dataset and got similar results. 

Lastly, I compared topics and common parts of speech for positive vs negative reviews to draw out more analysis in my text. Topics for positive and negative reviews focused more on specific artists or bands while parts of speech reflected the sentiment of the review. I quantified positive reviews as receiving a score of 8.0 or higher and negative reviews as scores of 6.0 or lower.  

## Data
I downloaded a dataset from Kaggle that compromised of ~18,000 music reviews from Pitchfork spanning from 1999 to 2017. 

After merging all of the data together into one dataframe, these were the features included in my dataframe:

1. Review
2. Processed Review
3. Album Title
4. Artist
5. Album Score
6. Best New Music
6. Author
7. Author Type
8. Publish Date
9. Publish Weekday
10. Publish Day
11. Publish Month
12. Publish Year
13. Genre
14. Label 
15. Year Album Released 

## Algorithms
* _Cleaning, Preprocessing Data_
	* Used NLTK to tokenize, stem, lemm, and remove stopwords from my text 
	* Used both Count Vectorizer and TF-IDF 

* _Modelling_
	* Tried CorEx, CV/LDA, and TF-IDF/NMF topic modeling on my entire dataset, rock genre, postive, and negative reviews. 
	* Ran a Random Forest and Elastic Net regressor model on my data to try to build a model based off of my topics -- looking at feature importance and model metrics to determine the strengths and weaknesses of my preliminary model 
	* Looked at parts of speech importance when analyzing positive vs negative reviews 
		
* _Visualizing Data_
	* Used Matplotlib to create visualizations looking at model accuracy 

## Tools
* Numpy, Pandas for EDA
* Matplotlib for data visualization
* Scikit-learn, CorEx for modelling and analysis
* NLTK for text preprocessing and cleaning
* SQLite for loading my data in 

