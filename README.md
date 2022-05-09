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
To run our project, make sure you have installed the following : [setuptools](https://pypi.org/project/setuptools/), [pywikibot](https://github.com/wikimedia/pywikibot#readme), [mwparserfromhell](https://mwparserfromhell.readthedocs.io/en/latest/), [pandas](https://pandas.pydata.org/), [numpy](https://numpy.org/install/), [scipy](https://scipy.org/install/), [nltk](https://www.nltk.org/install.html), [tqdm](https://tqdm.github.io/), [wikipedia](https://pypi.org/project/wikipedia/), [pyqt5](https://pypi.org/project/PyQt5/), [pyqtwebengine](https://pypi.org/project/PyQtWebEngine/), [pathlib](https://docs.python.org/3/library/pathlib.html), [ruamel-yaml](https://pypi.org/project/ruamel.yaml/), [lxml](https://lxml.de/installation.html) and [seaborn](https://seaborn.pydata.org/)

All can be installed using pip : 

```
!pip install wikipedia setuptools pywikibot mwparserfromhell pandas numpy scipy nltk tqdm seaborn pyqt5 pyqtwebengine ruamel-yaml lxml
```

## How to Use the Project
Our method for delimiting our corpus is to do a wikipedia search of the principal article in our case "Effects of climate change" we want to scrap then to find the other articles we defined a keyword  in our example "Climate change" and if the keyword is in the title or the section, subsection or subsubsection. In our program the first arguments of our function correspond to the name of the main article, the second argument is the number of article of the wiki search that are going to be analyzed (5000 is the maximum), the third argument is the keyword if the keyword is either in the title, section, subsection or subsubsection then the article will be selected by our function.
To launch the corpus selection for your article you just need to replace "Effects of climate change"  by your main article and "Climate change" with the keywords for your corpus.
![image](https://user-images.githubusercontent.com/60670025/167416548-4a2ee4f1-d15b-4ed6-b877-708876ffaa77.png)
This function usually last 1h to 2h it's normal.

To launch the function creation of the dataframe you need in argument a list of the title of the article of the corpus, in second argument you need the keyword explained before that selects the  sections. If you want to scrap the wikicode of only the section containing the keyword if the keyword is not in the title then remove the ''' ''' shown in the picture: 
![image](https://user-images.githubusercontent.com/60670025/167449184-7e5fcb83-3ba2-4abd-89cb-37e8101f1e49.png)
Remove also the ''' ''' and comment the line page_text=page.text if you want the more precise wikicode.
![image](https://user-images.githubusercontent.com/60670025/167449226-4967675f-fa0f-42dd-b3cd-967846f0e017.png)

