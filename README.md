# WikiCorpus 

[Project Description] ()
[How to Install and Run the Project] ()
[How to Use the Project] ()

## Project Description
Our code makes a wikipedia corpus based on an existing article and a keywword of interest. 

1/ It first selects all the wikipedia articles that respects the defined criteria
2/ It scraps information for all these articles

The output is dataframe containing all the selected wikipedia articles and basics information for these articles.

### How is an article selected ?

Let's imagine you are interested in the article "Wikipedia culture". The code will go through all the articles of the wikipedia "free search" making a first selection.
To specify this corpus, a word of interest should be added, for example "Wikipedia".  Within the free search articles, this will only select the articles containing the keyword in their title or one of their subtitles.
The final list is making the corpus.

### Which information are scraped ?

For each article, some informations from the "page information" are scrapped. We also scrap informations from the main page and from the "page statistics" (Xtools).
Using these scraped data, we also apply some bascis functions for instance to calculate the Sci-score (cf Sci-score paragraph).
Finally we get :
The name of the article, its url , a count a for the references from XTools, a count of the articles with our code, the number of scientific journal citations, a Sci-count, the page protection, the page lenght (in Bytes), the date of birth, the creator, the total number of edits, the recent edits and some formated dates.

#### Sci-score ?
Describe the calculation of the sci-score

## How to Install and Run the Project

## How to Use the Project
