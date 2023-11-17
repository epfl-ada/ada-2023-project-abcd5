# *Movie Cheat*

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

#### 1. Reading and cleaning
Loaded our dataset (small enough  to be able to simply read it on our computer)
First look at the data: checking for NaN values percentage, removing useless columns (we decided to not use the revenue columns that had  90% of NaN values). Instead, use of IMDB ratings as n indicator of movie success.
Basic cleaning of the data 

#### 2. Clean and merges
movie_rating : creating our base final dataset by merging movie_metadata with a cleaned version of IMDB ratings
movie_ratings_budgets : also created a dataset that will be used to run the analysis on movies' budgets: merging movie_rating with a cleaned version of Kaggle movie_metadata.csv
name_cluster_analysis : dataset that will be used to compare character names and the ratings of the movies these characters appear in

#### 4. Data visualization
After having cleaned the data, initial plotting of the features which each potentially alter the movie ratings: checking to see if the research questions are feasible, checking for trends, deciding what further analysis is necessary to conduct for our research questions.

#### 5. Linear Regression
Check for the correlation between the features chosen in in the research questions and see how the movie ratings are consequentially affected.

#### 6. Natural Process Learning
  #Maybe Asama can describe how he'll use this method or how it works




# Proposed timeline

- `21.11.22` - Perform deeper data visualizations
- `23.11.22` - Further analysis of the data
- `28.11.22` - Pause project work
- `01.12.23` - Homework 2 deadline
- `05.12.22` - Perform final analysis
- `07.12.22` - Clean the code
- `09.12.22` - Clean the comments and the analysis
- `12.12.22` - Start the data story with the website
- `15.12.22` - Finish code implementations and visualizations
- `18.12.22` - Finalize data story
- `22.12.22` - Milestone 3 deadline

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
    <td class="tg-0lax">Asama Hyder</td>
    <td class="tg-0lax">Plot Summary Analysis<br><br>Visualizations<br><br>Develop Web Interface</td>
  </tr>
  <tr>
    <td class="tg-0lax">Anna Yildiran</td>
    <td class="tg-0lax">Character Name Analysis<br><br>Visualizations<br><br>Develop Web Interface</td>
  </tr>
</tbody>
</table>


