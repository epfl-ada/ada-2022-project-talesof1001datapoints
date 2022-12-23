# Representativity on screen and its impact on a film's appreciation

___ ___
# **[Website link](https://nmuenger.github.io/2022_ada_datastory/)**
___ ___

## Abstract

Television and especially films play a crucial role in our modern society. The main characters in films serve as role models and inspire the younger generation, who may spend up to 78,000 hours watching television in their lifetime, as a survey of 2,000 British adults has shown.
Furthermore, the growing public interest in the issue of representativeness has led us to study it through the cinema, believing that it plays a crucial role in achieving a more inclusive society.
To do this, we use a large database of films, and construct two indicators to measure gender and ethnic representation within a film. We then look at the evolution of the latter over time, across the main film genres, as well as across the different countries of the world. Finally, we will try to show how representativeness is perceived by the general public, by analysing the reviews and the box-office revenues of films.

## Research questions

We will focus our analysis on two main interrogations:

### How is representativity distributed across cinematography genre, countries of production and time ?
The theme of representativeness has become increasingly important in the public sphere in recent years, but can this trend be seen in film? Are there regional anomalies? Are there discrepancies between film genres? We will try to answer these questions. In this section we will take a descriptive approach in order to highlight the different aspects of representativeness in the cinema.


### How does representativity impact a movie’s critical and commercial success?
Our first question looks at differences in representation within the film industry, but how are they perceived? Do they affect public opinion? Does this affect the box-office scores of the films? These are the questions we will try to answer in this second part. With an analytical approach this time, we will try to measure the impact that representativeness can have on the cinema and on the public.

## Proposed additional datasets

* **AD1 : [Tomatometer score from Wikidata](https://www.rottentomatoes.com/)**: we extend our dataset by querying the Tomatometer score from Wikidata. Rotten Tomatoes is an American website that aggregates reviews from professional critics. 
If a review is generally positive, it is simplified to a “fresh” rating. On the other hand, if it is considered negative, it is categorized as “rotten”. The Tomatometer score is then the percentage of “fresh” reviews given to a movie. 
We query this data from the Wikidata page of each movie. We also query the number of reviews that were used for said Tomatometer score.


<p align="center">
  <img src="https://github.com/epfl-ada/ada-2022-homework-1-talesof1001datapoints/blob/main/tomatometer_score.png" width="500">
</p>
<p align="center">
  <em>Tomatometer score claim on wikidata for the movie Avatar</em>
</p>

* **AD2 : Ethnicity from Wikidata**: We also used Wikidata to retrieve the ethnicities given their freebase IDs. [...%] of the IDs were matched to the ethnicities. This allows us to have [...%] of the actor's ethnicities.


## Methods

### 1. Get the importance of the characters in a movie

To assess the importance of every character in a movie, we will firstly do a correference resolution with the name of the characters in the synopsis. And then run a frequency analysis on the number of times that the character's name appears in the synopsis.
We give more points to the characters that appear sonner in the synopsis.

### 2. Get gender score

The gender score takes into account 3 things:
1. Ratio between the number of female and male actors who played in the movie.
2. The repartition if the importance of roles among males and females actors. 
3. We will use the Empath library to analyze the synopsis of the movies. As we can find on its  [Github page](https://github.com/Ejhfast/empath-client): Empath is a tool for analyzing text across lexical categories (similar to LIWC), and also generating new lexical categories to use for analysis. Therefore, we will analyze the presence of the categories "masculine" and "feminine" in the synopsis.   


### 3. Get ethnicity score

Firstly, we need to regroup specific ethnicities into broader categories. One telling example is that in our dataset, one actor has the ethnicity: "Sri Lankan living in Switzerland". This specific ethnicity would be re-classified into the more general "South Asian" category. As we have 479 different ethnicities, we can class them by hand into a fewer number of "general ethnicities".

Once this is done, we will only take into account these "broader ethnicities". 
The ethnicity score takes into account 3 things:
1. The number of ethnicites that are reprenseted in total in the movie 
2. The relative importance of the ethnicity (i.e. you get more points if you have an ethnicty that is not much represented already)
3. The repartition of character importances among ethnicities

### 4. How is representativity distributed across cinematography genre, countries of production and time. 

Once our metrics are computed, we want to analyze their distribution among: cinematography genre, countries of production and time.
And see if we can get some interestign trends. 

### 5. Observationnal study

The Rotten Tomatoes scores represent the success of the movies among critics. Whereas, the box office revenue represents the commercial success. 
The idea is to understand how the diversity in movies impact their succes. 

Therefore, we will do an observationnal to eliminate cofonders: year of production, country of production and genre of the movie with exact matching and propensity score matching.

We will then be able to analyze if movies have a higger success if they have a low or high diversity.

### 6. Creation of the data story’s website

The final step will be to create a cohesive story and to format it on a GitHub webpage. 

## Organization within the team

* Step 1: Malek
* Step 2: Baptiste
* Step 3: Baptiste
* Step 4: Nicolas 
* Step 5: Henry
* Step 6: Nicolas, Baptiste, Henry 
