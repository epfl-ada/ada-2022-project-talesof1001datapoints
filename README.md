# Representation on screen and its impact on a film's appreciation

___ ___

## Abstract

A survey conducted on two thousand British adults showed that people watch TV for 78’000 hours on average in their lifetime. This number shows that movies have a significant role in our society. We also think that representativity is a crucial factor to achieve an inclusive society. For example, main characters of movies can act as role models and inspire young generations. We believe that representativity has been neglected in the past but interestingly, people seem to be more and more concerned about this issue. 
Therefore, we want to characterize the distribution of gender and ethnicity across movie characters. We also want to analyze the evolution of representativity in time to understand if the movie industry is going in the right direction. Finally, we will infer how the public and critics react to diversity by analyzing the critics review and box office revenue of movies. 



## Research questions

We will focus our analysis on three main interrogations:

### How is representativity distributed across type of movies and countries of production
 
We think that the representativity will not be the same among types of movies and maybe countries of production.. For example: we might see that there is a good gender representativity in French romantic movies. Whereas we have a very bad one in American action movies. The idea of this research question is to find these discrepancies. 

### How has representativity in movies evolved?

With the characters dataframe and the year of release of the movies, we will see if an evolution has occurred with time. This analysis will be segmented on the gender as well as the ethnicity.

### How does representativity impact a movie’s critical and commercial success?

We will use the box office revenue as a metric of commercial success. As a metric of critical success we extend our dataset with the Rotten Tomatoes score of movies [cf. Added data section]. We will then be able to see if certain type of representation impact negatively one or the other success.


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
### 1. Get gender score

We want to create 2 scores to represent gender diversity. 

1. *Actor score*: this will be based on the ratio between the number of female and male actors who played in the movie.
2. *Synopsis score*: we will use the Empath library to analyze the synopsis of the movies. As we can find on its  [Github page](https://github.com/Ejhfast/empath-client): Empath is a tool for analyzing text across lexical categories (similar to LIWC), and also generating new lexical categories to use for analysis. Therefore, we will analyze the presence of the categories "masculine" and "feminine" in the synopsis.   

### 2. Get ethnicity score

Firstly, we need to regroup specific ethnicities into broader categories. One telling example is that in our dataset, one actor has the ethnicity: "Sri Lankan living in Switzerland". This specific ethnicity would be re-classified into the more general "Asian" category. As we have 479 different ethnicities, we can class them by hand into a fewer number of "general ethnicities".
Then, we will create two scores to represent ethnicity representativity.
Rough score: this score will be equal to the number of actors of a specific ethnicity who played in a movie. As a basic example, the rough score of "black people" in the movie "men in black" is equal to 1 because there is one African American actor in the movie.
Precise score: this score is equivalent to the previous one, but we will weigh the Rough score with the importance of characters in the movies. To assess the importance of every character, we will run a frequency analysis on the number of times that the character's name appears in the synopsis.


### 3. Look at the evolution of these score through time

In order to do this, we will plot the gender and ethnicity scores in function of the year of release of the movies. We will then do linear regressions to extract general trends of the evolution of diversity. 

### 4. Fined-grained analysis of representativity (across type and country of production of the movies)

As we can not analyze all the types and countries of production of movies, we will only keep the most represented movie genres, and we will cherry-pick the countries that we find interesting. 

For every “interesting” country, we will present scatter plots on the X-axis: the genres of movies. And on the Y-axis: the previously computed gender and ethnicity scores.
 

### 5. Regression between representativity and commercial/critical success

The Rotten Tomatoes scores represent the success of the movies among critics. Whereas, the box office revenue represents the commercial success. 
We will do a regression over these two success metrics. The input features for these regressions will be the previously computed ethnicity and gender scores. 

### 6. Creation of the data story’s website

The final step will be to create a cohesive story and to format it on a GitHub webpage. 


## Proposed timeline

* Step 1: 02-dec-2022
* Step 2: 02-dec-2022
* Step 3: 09-dec-2022
* Step 4: 09-dec-2022
* Step 5: 13-dec-2022
* Step 6: 19-dec-2022

## Organization within the team

* Step 1: Malek
* Step 2: Henry
* Step 3: Nico
* Step 4: Baptiste 
* Step 5: Malek
* Step 6: Everybody 


