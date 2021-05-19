# NLP Project Proposal

## Question: 
Continuing my music journey in my classification project, I would like to explore the capabilities of NLP in regards to music album reviews. Pitchfork, an online music publication, is well known for their reviews -- they are notorious for their unpredictable and finnicky reviews scaled to dispense 1/10th of a point at a time for a maximum of 10 points. Many would agree that Pitchfork has held considerable influence and regard in the music world at one point or another, particularly with independent music. 

I would like to see if I am able to see if there are any particular words or topics that indicate whether or not an album will receive a positive review from Pitchfork. In addition, I would like to explore if genre, artist, record label, or the review author plays a part in the scoring. Lastly, I would like to build a predictor to see if I am able to train my data to accurately mirror Pitchfork's scores. 


## Data: 
Kaggle has a comprehensive dataset of ~18,000 reviews from Pitchfork starting from 1999 to 2017 that I plan on using for this project. The data is divided into a series of sql files that include: 

1. Artist
2. Album Title
3. Label
4. Year Album Released
5. Genre
6. Date Review Published
7. Review Author
8. Editorial Position of Review Author
9. Review Score
10. Review Content

## Tools:
* NLTK, Numpy, Pandas for processing data, EDA
* Scikit-learn for modelling and analysis
* Matplotlib, Tableau for visualization
* SQL for db storage

## MVP:
I plan to have all of my text pre-processed with topic modelling and sentiment analysis almost completed. Ideally, I would be exploring supervised models to see how a machine would score these albums in comparison to Pitchfork's scoresat this time as well. 
