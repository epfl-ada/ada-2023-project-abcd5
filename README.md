# *TITLE*
one line description

# Abstract

In an age where TV popularity is rapidly increasing, what would compel a viewer to sit down after a long day of work and enthusiastically watch a film instead of just having a tv show episode playing in the background as noise? We aim to find out what makes a movie desirable and what factors are effective in determining the IMDB rating as well as the popularity of a movie. 
We also hope that our findings will inspire creative minds in the industry when making decisions for new projects. What subjects should film writers focus on? What type of actors should directors be casting? Which types of films should producers invest their money in? 

# Research questions

* What makes a good movie plot? 
* Does release date have an influence? If yes, when is it best to release a movie? Does it have a link with the genre? 
* Can we make a successful movie with a low budget? Or is budget a relevant factor of success?
* Could the availability of a movie in mutliple languages impact its success? What about its country of origin?
* Do peole enjoy sequels? Do film with more sequels have bettter popularity than others with no or less sequels?


# Proposed additional datasets
how to make the link just be a word??

In addition to our main CMU movies dataset, we decided to use tohers in order to be able to properly answer our questions:

* A dataset from Kaggle for the budgets https://www.kaggle.com/datasets/rounakbanik/the-movies-dataset?resource=download&select=movies_metadata.csv : we merge our dataset the movie_metadata.csv file that contains the budgets

* A dataset from IMDB for the ratings https://developer.imdb.com/non-commercial-datasets/ : we merge our dataset with the title.ratings.tsv file

* A dataset of a mapping from Freebase ID to IMDB ID https://query.wikidata.org/#PREFIX%20wd%3A%20%3Chttp%3A%2F%2Fwww.wikidata.org%2Fentity%2F%3E%0APREFIX%20wdt%3A%20%3Chttp%3A%2F%2Fwww.wikidata.org%2Fprop%2Fdirect%2F%3E%0APREFIX%20wikibase%3A%20%3Chttp%3A%2F%2Fwikiba.se%2Fontology%23%3E%0A%0ASELECT%20%3Fitem%20%3FfreebaseID%20%3FimdbID%0AWHERE%20%7B%0A%20%20%3Fitem%20wdt%3AP31%2Fwdt%3AP279%2a%20wd%3AQ11424.%0A%20%20%3Fitem%20wdt%3AP646%20%3FfreebaseID.%0A%20%20%3Fitem%20wdt%3AP345%20%3FimdbID.%0A%20%20%7D : we needed that dataset in order to merge IMDB ratings with our Freebase ID identified movies

# Methods

1. Reading and cleaning
Loaded our dataset (enough small to be able to simply read it on oiyr computer)
First look at the data: checking for NaN values percentage, removing useless columns (we decided to not use the revenue columns that had  90% of NaN values)
Basic cleaning of the data 

2. Clean and merges
movie_rating : creating our base final dataset by merging movie_metadata with a cleaned version of IMDB ratings
movie_ratings_budgets : also created a dataset that will be used to run the analysis on movies' budgets: merging movie_rating with a cleaned version of Kaggle movie_metadata.csv 


# Proposed timeline



# Organization within the team


