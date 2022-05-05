# WikiCorpus 

## Project Description
Our code makes a wikipedia corpus based on a specific term.

1. It first selects all the wikipedia articles that respects the defined criteria
2. It scraps information for all these articles

The output is dataframe containing all the selected wikipedia articles and basics information for these articles.

### How is an article selected ?

Let's imagine you are interested in "Wikipedia culture". The code will go through all the articles of the wikipedia "free search" making a first selection.
To specify this corpus, a word of interest should be added, for example "Wikipedia".  Within the free search articles, this will only select the articles containing the keyword in their title or one of their subtitles.
The final list is making the corpus.

### Which information are scraped ?

For each article, some informations from the "page information" are scrapped. We also scrap informations from the main page and from the "page statistics" (Xtools).
Using these scraped data, we also apply some bascis functions for instance to calculate the Sci-score (cf Sci-score paragraph).
Finally we get :
The name of the article, its url , a count a for the references from XTools, a count of the articles with our code, the number of scientific journal citations, a Sci-count, the page protection, the page lenght (in Bytes), the date of birth, the creator, the total number of edits, the recent edits and some formated dates.

#### Sci-score ?
One of the basic information of our dataframe is a sciscore. This score between 0 and 1 is the ratio of scientific papers other the total number of references. To do so, we count the total number of doi, pmid and pmc. If all the papers collected by this method are peer-reviewed scientific papers, not all scientific references have a doi, a pmid or a pmc, mostly due to bad citation formatting. As such, the this score is only an estimate. 
A score close to 1 means a higly scientific based article.
A score close to 0 means a low scientific based article.

## How to Install and Run the Project

### Installation
To run our project, make sure you have installed the following : [setuptools](https://pypi.org/project/setuptools/), [pywikibot](https://github.com/wikimedia/pywikibot#readme), [mwparserfromhell](https://mwparserfromhell.readthedocs.io/en/latest/), [pandas](https://pandas.pydata.org/), [numpy](https://numpy.org/install/), [scipy](https://scipy.org/install/), [nltk](https://www.nltk.org/install.html), [tqdm](https://tqdm.github.io/), [wikipedia](https://pypi.org/project/wikipedia/), [pyqt5](https://pypi.org/project/PyQt5/), [pyqtwebengine](https://pypi.org/project/PyQtWebEngine/), [pathlib](https://docs.python.org/3/library/pathlib.html), [ruamel-yaml](https://pypi.org/project/ruamel.yaml/), [lxml](https://lxml.de/installation.html), [seaborn](https://seaborn.pydata.org/)

All can be installed using pip : 

```
!pip install wikipedia setuptools pywikibot mwparserfromhell pandas numpy scipy nltk tqdm seaborn pyqt5 pyqtwebengine ruamel-yaml lxml
```

## How to Use the Project
