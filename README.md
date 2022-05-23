# Project Description
This tool is a part of a [broader project](https://projects.learningplanetinstitute.org/projects/nnEVGw73/des) of using wikipedia to analize history of contemporary science.

Our code makes a wikipedia corpus based on a term of interest. 

1. It first selects all the wikipedia articles that respects the defined criteria
2. It scraps information for all these articles

The output is dataframe containing all the selected wikipedia articles and basics information for these articles.
The code also gives access to some plots on the corpus.

## How is an article selected ?

Let's imagine you are interested in "Wikipedia culture". The code will go through all the articles of the wikipedia "free search" making a first selection.
To specify this corpus, a word of interest should be added, for example "Wikipedia".  Within the free search articles, this will only select the articles containing the keyword in their title or the title of a section, subsection or subsubsection
The final list is making the corpus.

## Which information are scraped ?

For each article, some informations from the "page information" are scrapped. We also scrap informations from the main page and from the "page statistics" (Xtools).
Using these scraped data, we also apply some basics functions for instance to calculate the [Sci-score](https://github.com/Augustoni/wiki-score/edit/main/README.md#sci-score-).
Finally we get :
The name of the article, its url , a count of the article's references with our code, the number of scientific journal citations, a Sci-count, the page protection, the page length, the date of birth, the creator, the total number of edits, the recent edits and some formated dates.

### Sci-score 
One of the basic information of our dataframe is a sciscore. This score between 0 and 1 is the ratio of scientific papers other the total number of references. To do so, we count the total number of doi, pmid and pmc. If all the papers collected by this method are peer-reviewed scientific papers, not all scientific references have a doi, a pmid or a pmc, mostly due to bad citation formatting. As such, the this score is only an estimate. 
A score close to 1 means a higly scientific based article.
A score close to 0 means a low scientific based article.

# How to Install and Run the Project

## Installation
To run our project, make sure you have installed the following : [setuptools](https://pypi.org/project/setuptools/), [pywikibot](https://github.com/wikimedia/pywikibot#readme), [mwparserfromhell](https://mwparserfromhell.readthedocs.io/en/latest/), [pandas](https://pandas.pydata.org/), [numpy](https://numpy.org/install/), [scipy](https://scipy.org/install/), [nltk](https://www.nltk.org/install.html), [tqdm](https://tqdm.github.io/), [wikipedia](https://pypi.org/project/wikipedia/), [pyqt5](https://pypi.org/project/PyQt5/), [pyqtwebengine](https://pypi.org/project/PyQtWebEngine/), [pathlib](https://docs.python.org/3/library/pathlib.html), [ruamel-yaml](https://pypi.org/project/ruamel.yaml/), [lxml](https://lxml.de/installation.html) and [seaborn](https://seaborn.pydata.org/)

All can be installed using pip : 

```
!pip install wikipedia setuptools pywikibot mwparserfromhell pandas numpy scipy nltk tqdm seaborn pyqt5 pyqtwebengine ruamel-yaml lxml
```
## Run the Project
The project is contained in a .ipynb file which corresponds to a python notebook file. The code is designed to be run using the cells' logic of a notebook. [Jupyter](https://jupyter.org/) is an example of a free notebook you can use.
To create the corpus first launch *corpus creation and name of journal analysis* notebook. Then to compare corpora you can launch the *poster figures* notebook. 
If you want to have the history on one article using wikicode manually found you can look at the branch history.
The *wikipediaAnalysishistory* notebook is made based on Leo Blondel code that you can find in this gitlab: https://gitlab.com/xqua/wikipedia-data-collector/-/tree/main 
This notebook is a modification of the notebook *WikipediaAnalysisDemo* with the extraction of the name of the citation to make it work yu firstly need to run the code on Leo Blondel's Github.

# How to Use the Project

## Corpus Selection 
To launch the corpus selection for your article, you need to use your arguments for the function "corpus_selection".
In our function "corpus selection:
1. The first argument of our function correspond to the name of the main article.
2. The second argument is the number of article that the wiki search will analyze (5000 is the maximum).
3. The third argument is the keyword that will be searched in the main titles and the titles of sections, subsections or subsubsections.

In other words, you need to replace "Effects of climate change"  by your main article and "Climate change" with the keywords for your corpus.

![image](https://user-images.githubusercontent.com/60670025/167416548-4a2ee4f1-d15b-4ed6-b877-708876ffaa77.png)

This function usually lasts 1h-2h, so leave your computer on and grab a cup of coffee.

### Possibilities to fine-tune the corpus selection code
By default, our code is scrapping the whole text for each article. This means that the information on the references are concerning the whole article. However, for the article of the corpus that do not contain the keyword in their main title, the whole article may not be relevant of what you are studying. As so, if you only want to scrap the references of the section whose title contains your keyword, remove the ''' ''' shown in the picture: 

![image](https://user-images.githubusercontent.com/60670025/167449184-7e5fcb83-3ba2-4abd-89cb-37e8101f1e49.png)

You also need to remove the ''' ''' and the "line page_text=page‧text" if you want the more precise wikicode. Use "#" to comment the line, inactivating it without fully loosing it.

![image](https://user-images.githubusercontent.com/60670025/167449226-4967675f-fa0f-42dd-b3cd-967846f0e017.png)

## Get some basic plots on the corpus
The code also plots some figures that describe the corpus. The corresponding cells need to be played once the corpus has been charged. You get access to the following plots:
1. A pie chart of the creators
2. A yearly timeline of the artices date of birth
3. Barplots of the most cited references

# Acknowledgements

A huge thanks to Omer Benjakob, Rona Aviram which method we applied and who guided us throughout this project. For the code part a huge thanks to Leo Blondel and	Jean-Marc Sevin because without them we wouldn't be able to have done this.

# Contact 
If you are interested by the code and have struggle understanding something don't hesitate to contact us at the mail adress ariane.augustoni@cri-paris.org we will very pleased to answer you.
