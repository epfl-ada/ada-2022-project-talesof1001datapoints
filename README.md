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

**Step 1: Data scraping, pre-processing and dataset construction.**

* Dataset D1 : General dataset containing quotes of women authors
* Dataset D2 : MeToo dataset containing quotes linked to the movement, in which the movement is mentioned
  * D2.1 : Subsets by gender of speaker
  * D2.2 : Subsets by age of speaker
  * D2.3 : Subsets by political parties (for politician authors) of speaker\
    *These subsets are built later on during Step 4.*
* Dataset D3 : Dataset containing quotes in which a woman is mentioned
  * D3.1: Subset by gender of speaker

**Step 2: General preliminary analysis using Quotebank entire dataset**
Weekly percentage of quotes by author’s gender (men, women, other, unkown) from 2015 to 2020.

**Step 3: Generate annual word clouds based on dataset D1 with this [library.](https://github.com/amueller/word_cloud)**

**Step 4: Investigate gender, political and generational biases in MeToo coverage using NLP to answer question A).**
Train a [SpaCy NLP model](https://spacy.io/usage/training) with dataset AD3 to perform sentiment analysis. Classification thanks to trained model on the whole dataset D2. Subdivision of D2 into D2.1, D2.2 and D2.3 for biases investigation. Clustering trials with unsupervised different ML algorithms applied on the sentiment analysis classification probabilities.

**Step 5: Investigate general women perception via dataset D3 in medias to answer question B).**
Generate word clouds. Classification of quotes : Text Blob or Vader models for positive, negative or neutral. Train SpaCy model on AD2 for misogynistic or non misogynistic. Classification thanks to trained model on D3.

**Step 6: Correlate and investigate causation between MeToo general perception and women’s mediatic place to answer question C).**
Plot previously collected (step 5) data distributions according to time. Comparison with key turning points of MeToo. Investigation of the statistical significance of detected changes before and after MeToo.

**Step 7: Github site building and Datastory redaction.**

**Further details on the proposed data pipelines can be found in the notebook.**

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
