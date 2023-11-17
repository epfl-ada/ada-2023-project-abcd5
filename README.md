# *Cheat sheat for a perfect movie*

# Abstract

In an age where TV popularity is rapidly increasing, what would compel a viewer to sit down after a long day of work and enthusiastically watch a film instead of just having a tv show episode playing in the background as noise? We aim to find out what makes a movie desirable and what factors are effective in determining the IMDB rating as well as the popularity of a movie. 
We also hope that our findings will inspire creative minds in the industry when making decisions for new projects. What subjects should film writers focus on? What type of actors should directors be casting? Which types of films should producers invest their money in? 

# Research questions
In this project, we are trying to find what features affect a movie's rating, and to do so we have decided to focus on the following questions:

* What makes a good movie plot? 
* Does release date have an influence? If yes, when is it best to release a movie? Does it have a link with the genre? 
* Can we make a successful movie with a low budget? Or is budget a relevant factor of success?
* Could the availability of a movie in mutliple languages impact its success? What about its availability in English?
* Does the apparition of a character name more than once affect how much a viewer will get attached to a movie and thus rate it higher?


# Proposed additional datasets

In addition to our main CMU movies dataset, we decided to use others in order to be able to properly answer our questions:

* A dataset from Kaggle for the [budgets](https://www.kaggle.com/datasets/rounakbanik/the-movies-dataset?resource=download&select=movies_metadata.csv) : we merge our dataset the movie_metadata.csv file that contains the budgets

* A dataset from IMDB for the ratings [IMDB Ratings](https://developer.imdb.com/non-commercial-datasets/) : we merge our dataset with the title.ratings.tsv file

* A dataset of a mapping from [Freebase ID to IMDB ID](https://query.wikidata.org/#PREFIX%20wd%3A%20%3Chttp%3A%2F%2Fwww.wikidata.org%2Fentity%2F%3E%0APREFIX%20wdt%3A%20%3Chttp%3A%2F%2Fwww.wikidata.org%2Fprop%2Fdirect%2F%3E%0APREFIX%20wikibase%3A%20%3Chttp%3A%2F%2Fwikiba.se%2Fontology%23%3E%0A%0ASELECT%20%3Fitem%20%3FfreebaseID%20%3FimdbID%0AWHERE%20%7B%0A%20%20%3Fitem%20wdt%3AP31%2Fwdt%3AP279%2a%20wd%3AQ11424.%0A%20%20%3Fitem%20wdt%3AP646%20%3FfreebaseID.%0A%20%20%3Fitem%20wdt%3AP345%20%3FimdbID.%0A%20%20%7D) : we needed that dataset in order to merge IMDB ratings with our Freebase ID identified movies
[Kaggle](https://query.wikidata.org/#PREFIX%20wd%3A%20%3Chttp%3A%2F%2Fwww.wikidata.org%2Fentity%2F%3E%0APREFIX%20wdt%3A%20%3Chttp%3A%2F%2Fwww.wikidata.org%2Fprop%2Fdirect%2F%3E%0APREFIX%20wikibase%3A%20%3Chttp%3A%2F%2Fwikiba.se%2Fontology%23%3E%0A%0ASELECT%20%3Fitem%20%3FfreebaseID%20%3FimdbID%0AWHERE%20%7B%0A%20%20%3Fitem%20wdt%3AP31%2Fwdt%3AP279%2a%20wd%3AQ11424.%0A%20%20%3Fitem%20wdt%3AP646%20%3FfreebaseID.%0A%20%20%3Fitem%20wdt%3AP345%20%3FimdbID.%0A%20%20%7D)


# Methods

#### 1. Load and clean
First, load our dataset.
First look at the data: checking for NaN values percentage, removing useless columns.
Basic cleaning of the data 

#### 2. Create datasets
movie_rating : creating our base final dataset by merging movie_metadata with a cleaned version of IMDB ratings
movie_ratings_budgets : also created a dataset that will be used to run the analysis on movies' budgets: merging movie_rating with a cleaned version of Kaggle movie_metadata.csv
name_cluster_analysis : dataset that will be used to compare character names and the ratings of the movies these characters appear in

#### 3. Data visualization
After having cleaned the data, initial plotting of the features which each potentially alter the movie ratings: checking to see if the research questions are feasible, checking for trends, deciding what further analysis is necessary to conduct for our research questions.

#### 4. Linear Regression
Check for the correlation between the features chosen in in the research questions and see how the movie ratings are consequentially affected.

#### 5. Natural Process Learning (NLP)
We use NLP techniques to analyze the movie plots to determine what makes a good plot in terms of predicting a good average rating. We start by preproccessing the plots by removing special characters, removing stop words and lemmatizing/stemming words. We then created a bag-of-words matrix and trained a linear-regression model with average movie rating as target. We then looked at the cooeficient for each word to determine the importance of each words in regards to the average movie rating. Next steps are to use more data, more complex models like introducing regression or training neural nets. We will also explore word embeddings as an alternative to bag-of-words and then finally properly test the models and see if it is possible to determine if a plot can predict a movie rating.




# Proposed timeline

- `21.11.23` - Perform deeper data visualizations
- `23.11.23` - Further analysis of the data
- `28.11.23` - Pause project work
- `01.12.23` - Homework 2 deadline
- `05.12.23` - Perform final analysis
- `07.12.23` - Clean the code
- `09.12.23` - Clean the comments and the analysis
- `12.12.23` - Start the data story with the website
- `15.12.23` - Finish code implementations and visualizations
- `18.12.23` - Finalize data story
- `22.12.23` - Milestone 3 deadline

# Organization within the team
<table class="tg" style="undefined;table-layout: fixed; width: 342px">
<colgroup>
<col style="width: 164px">
<col style="width: 178px">
</colgroup>
<thead>
  <tr>
    <th class="tg-0lax"></th>
    <th class="tg-0lax">Tasks</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td class="tg-0lax">Camille Valat</td>
    <td class="tg-0lax">Language and Country Analysis<br><br>Visualizations<br><br>Develop Web Interface</td>
  </tr>
  <tr>
    <td class="tg-0lax">Victoria Arduini</td>
    <td class="tg-0lax">Budget Analysis<br><br>Visualizations<br><br>Develop Web Interface</td>
  </tr>
  <tr>
    <td class="tg-0lax">Ilyaas Shousha</td>
    <td class="tg-0lax">Release Date Analysis<br><br>Visualizations<br><br>Develop Web Interface</td>
  </tr>
  <tr>
    <td class="tg-0lax">Asama Hayder</td>
    <td class="tg-0lax">Plot Summary Analysis<br><br>Visualizations<br><br>Develop Web Interface</td>
  </tr>
  <tr>
    <td class="tg-0lax">Anna Yildiran</td>
    <td class="tg-0lax">Character Name Analysis<br><br>Visualizations<br><br>Develop Web Interface</td>
  </tr>
</tbody>
</table>


