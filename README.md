# Representation on screen and its impact on a film's appreciation

___Study of the influence of the movement on women's mediatic representation___

## Abstract
CMU Movie Summary Corpus


## Research questions

* 

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
