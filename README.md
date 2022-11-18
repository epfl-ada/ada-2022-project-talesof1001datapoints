# Representation on screen and its impact on a film's appreciation

___ ___

## Abstract

A survey conducted on two thousand British adults showed that people watch TV for 78’000 hours on average in their lifetime. This number shows that movies have a significant role in our society. We also think that representativity is a crucial factor to achieve an inclusive society. For example, main characters of movies can act as role models and inspire young generations. We believe that representativity has been neglected in the past but interestingly, people seem to be more and more concerned about this issue. 
Therefore, we want to characterize the distribution of gender and ethnicity across movie characters. We also want to analyze the evolution of representativity in time to understand if the movie industry is going in the right direction. Finally, we will infer how the public and critics react to diversity by analyzing the critics review and box office revenue of movies. 



## Research questions

We will focus our analysis on two main interrogations:


* **How has representativity in movies evolved?** 

With the characters dataframe and the year of release of the movies we will see if an evolution has occurred with time. This analysis will be segmented on the gender as well as the ethnicity.

* **How does representativity impact a movie’s critical and commercial success?**

We will use the box office revenue as a metric of commercial success. As a metric of critical success we extend our dataset with the Rotten Tomatoes score of movies [cf. Added data section]. We will then be able to see if certain type of representation impact negatively one or the other success.


## Proposed additional datasets

* **AD1 : [Tomatometer score from Wikidata](https://www.rottentomatoes.com/)**: we extand our dataset by queerying the Tomatometer score from Wikidata. Rotten Tomatoes is an American website which aggregates reviews from professional critics. 
If a review is generally positive, it is simplified to a “fresh” rating. On the opposite, if it is considered negative, it is categorised as “rotten”. The Tomatometer score is then the percentage of “fresh” reviews given to a movie. 
We query this data from the Wikidata page of each movie. We also querry the number of reviews which were used for said Tomatometer score.

<p align="center">
  <img src="https://github.com/epfl-ada/ada-2022-homework-1-talesof1001datapoints/blob/main/tomatometer_score.png" width="500">
</p>
<p align="center">
  <em>Tomatometer score claim on wikidata for the movie Avatar</em>
</p>

* **AD2 : Ethnicity from Wikidata**: We also used Wikidata to retrieve the ethnicities given their freebase IDs. [...%] of the IDs were matched to the ethnicities. This allows us to have [...%] of the actor's ehtnicities.


## Methods
* **Get genre score**

We want to create 2 scores to represent gender diversity. 

1. *Actor score*: this will be based on the ratio between the number of female and male actors who played in the movie.
2. *Synopsis score*: we will use the tool "Empath" to analyze the synopsis of the movies. As we can find on its Github page: Empath is a tool for analyzing text across lexical categories (similar to LIWC), and also generating new lexical categories to use for an analysis. Therefore, we will analyze the presence of the categories "masculine" and "feminine" in the synopsis.   

* **Get ethnicity score**

Firstly, we need to regroup specific ethnicities into big categories. Let me give an example to illustrate this point. In our dataset, one actor has the etnhicity: "Sri Lankan living in Switzerland". This specific ethnicity would be classed into the big category :"Asian". As we have 479 different ethnicities, we can class them by hand into a fewer number of "general ethnicities".

Then, we will create 2 scores to represent ethniciteis representativity. 
1. *Rough score*: this score will be equal to the number of actors of a specific ethnicity who played in a movie. For example: the rough score of "black people" in the movie "men in black" is equal to 1 because there is one black actor in the movie. 
2. *Precise score*: this score is equivalent to the previous one, but we will weight the Rough score with the importance of characters in the movies. To assess the importance of every character, we will run a frequence analysis on the number of time that the character name's appear in the synopsis. 

* **Look at the evolution of these score through time**

In order to do this, we will plot the gender and etnicity scores in fonction of the year of release of the movies. We will then do linear regressions to exctract general trends of the evolution of diversity. 

* **Fined grained analysis of representativity (across movie types and country of production of the movie)**
* **Regression between representativity and commercial/critical success**


## Proposed timeline

* Step 2: 22/11/21
* Step 3, 4: 29/11/21
* Step 5: 06/12/21
* Step 6, 7: 13/12/21

## Organization within the team

* SpaCy Training on AD2 and AD3: Teammate 1
* Datastory: Teammate 2
* Website: Teammate 3 and 4
* Steps: Teammate 1,2,3,4
