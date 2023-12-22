# ✨*Cheat sheet for a perfect movie*✨


# Data Story 

Explore the narrative behind the development of our cheat sheet by following this link to access our [data story](https://camillevalat.github.io/Abcd5-website/).

# Abstract

Since the year 2000, the number of movies released in the UK as well as the US more than doubled. While the industry is rapidly growing, a significant proportion of movies continue to fall short of achieving significant recognition or commercial success. This proves that making a successful movie is a far more intricate process than it appears. While this seems to be a daunting task, separating it into smaller and simpler parts will put things into perspective. The CMU dataset contains data on more than 80’000 movies and with that, we will try to depict a cheat sheet for a perfect movie.

# Research Questions

In this project, we are trying to find what features affect a movie's rating, and to do so we have decided to focus on the following questions:

•	How the language of a movie impact its success? What about the use of English compared to other languages?

•	Does the apparition of a character name more than once affect how much a viewer will get attached to a movie and thus rate it higher?

•	Does release date have an influence? If yes, when is it best to release a movie? Does it have a link with the genre ?

•	What makes a good movie plot?

•	Can we make a successful movie with a low budget? Or is budget a relevant factor of success?

•	Do viewers enjoy seeing character stereotypes in a movie? Does their presence have an influence on a movie’s success?


# Additional Datasets

In addition to our main CMU movies dataset, we decided to use others in order to be able to properly answer our questions:

•	[**Freebase ID to IMDB ID**](https://query.wikidata.org/#PREFIX%20wd%3A%20%3Chttp%3A%2F%2Fwww.wikidata.org%2Fentity%2F%3E%0APREFIX%20wdt%3A%20%3Chttp%3A%2F%2Fwww.wikidata.org%2Fprop%2Fdirect%2F%3E%0APREFIX%20wikibase%3A%20%3Chttp%3A%2F%2Fwikiba.se%2Fontology%23%3E%0A%0ASELECT%20%3Fitem%20%3FfreebaseID%20%3FimdbID%0AWHERE%20%7B%0A%20%20%3Fitem%20wdt%3AP31%2Fwdt%3AP279%2a%20wd%3AQ11424.%0A%20%20%3Fitem%20wdt%3AP646%20%3FfreebaseID.%0A%20%20%3Fitem%20wdt%3AP345%20%3FimdbID.%0A%20%20%7D) : a dataset of a mapping from Freebase ID to IMDb ID. We merge the query.tsv dataset with the movie_metadata one on Freebase ID. We need this dataset to be able to  to merge the IMDb ratings dataset and the budget dataset (both identified by IMDb ID) with our Freebase ID identified movies from the CMU dataset.

•	[**IMDb Ratings**](https://developer.imdb.com/non-commercial-datasets/) : a dataset from IMDb for the movies’ ratings . We merge the ratings.tsv dataset with our dataset from CMU on IMDb ID.

•	[**Budgets**](https://www.kaggle.com/datasets/rounakbanik/the-movies-dataset?resource=download&select=movies_metadata.csv) : a dataset from Kaggle for the budgets . We merge the dataset from Kaggle (only keeping budget and IMDb ID columns) with our dataset from CMU on IMDb ID.

# Methods

### Step 1. Preprocessing and dataset construction

**Preprocessing**: We load and clean the CMU datasets, checking for NaN values and removing or cleaning columns (For example, we removed the ‘revenue’ column of movie_metadata as 87% of it was NaN values)

**Datasets construction**: We create our dataset for our future analysis by combining thr CMU ones with the additional ones:
-	movie_rating : creating our base final dataset by merging movie_metadata with a cleaned version of IMDB ratings
-	movie_ratings_budgets : the dataset to be used to run the analysis on budgets, created by merging movie_rating with a cleaned version of Kaggle movie_metadata.csv
-	name_cluster_analysis : the dataset to be used to run analysis on character names, created by merging movie_rating, character_metadata and name_clusters.
-	Tropes: the dataset to be used to run analysis on character tropes, created by merging a cleaned version of tropes.csv with name_cluster_analysis.

### Step 2. Language 

To assess the influence of English on movies, we split films into two categories: those not in English language and those in English along with at least one other language. We made initial visualizations to examine these categories. To determine if there was a statistically significant difference in scores between the two groups, we used the Mann-Whitney U test. For a deeper analysis, we also performed subgroup analyses within different movie genres.
	
### Step 3. Character name

Initially, we analysed the effect of the presence of a character across multiple films by computing the average weighted score for each character name based on their presence in multiple movies. We then used linear regression to fit the data to see the trend our data produced.

Next,  our focus shifted to investigating the influence of movie sequels on ratings. Assuming that movies featuring the same character name played by the same actor constituted sequels, we charted the mean weighted scores against the quantity of sequels.  We once again used linear regression to analyse the trend.

### Step 4. Genre and release date

First, we initiated our process by filtering out the data lacking information on the release month. Subsequently, we focused our analysis on the top 20 most popular genres, a strategy aimed at reducing the impact of anomalous scores associated with less common genres.

Once the data was meticulously cleaned, we embarked on our analysis utilizing line graphs and heatmaps to uncover insights and patterns.

### Step 5. Movie plots

We use natural language processing to analyse the movie plots. We start by loading and preparing the movie plot data by performing preproccessing steps like: converting text to lowercase, removing punctuation, removing numbers, removing stopwords and lemmatizing. Then we postprocess the text by tokenizing and creating a term frequency matrix. For the analysis we perform latent dirichlet analysis, and inspect the generated topics.

### Step 6. Budgets

Initially, we began with basic data visualizations (printing statistics, plotting disitrbutions). Next, we examined the correlation between a film's budget and its release year, as well as the relationship between a film's budget and its rating. Those analysis are conducted using both visualization tools and linear regression methods. Finally, we investigated how movie budgets vary across different genres. For that, we applied linear regression to analyze the connection between budget and score within each of the top 20 movie genres.

### Step 7. Character type

We began by examining how different character types influence movie ratings. Initially, we grouped the data by character type, computing the average weighted scores for each category. To further this analysis, we separated the character types by gender and analysed this impact through visual plots.
We also explored which character type associates best with which genre. Finally, we used the OLS method in linear regression,we employed the OLS method in linear regression, to  help us determine whether character names or character types have a stronger influence on a movie's rating.


# Proposed timeline

*   05.11.23 : Data preprocessing and dataset creation
*   15.11.23 : First analysis
*   17.11.23 : Milestone 2 deadline
*   01.12.23 : Pause to work on Homework 2
*   05.12.23 : Further analysis on each research questions
*   10.12.23 : Draft for the data story
*   12.12.23 : Final analysis and conclusions on each research questions
*   13.12.23 : Clean the notebook (code and comments)
*   18.12.23 : Finalize data story
*   20.12.23 : Update the readme
*   22.12.23 : Milestone 3 deadline



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
    <td class="tg-0lax">Language and Country Analysis<br><br>Write Datastory<br><br>Develop Website</td>
  </tr>
  <tr>
    <td class="tg-0lax">Victoria Arduini</td>
    <td class="tg-0lax">Budget Analysis<br><br>Write Datastory<br><br>Develop Website</td>
  </tr>
  <tr>
    <td class="tg-0lax">Ilyaas Shousha</td>
    <td class="tg-0lax">Release Date Analysis<br><br>Write Datastory</td>
  </tr>
  <tr>
    <td class="tg-0lax">Asama Hayder</td>
    <td class="tg-0lax">Plot Summary Analysis<br><br>Write Datastory</td>
  </tr>
  <tr>
    <td class="tg-0lax">Anna Yildiran</td>
    <td class="tg-0lax">Character Name Analysis<br><br>Character Types Analysis<br><br>Write Datastory<br><br>Develop Website</td>
  </tr>
</tbody>
</table>


