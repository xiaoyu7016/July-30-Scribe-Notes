# July-30-Scribe-Notes


Module 1: Exploratory Analysis
====================

####Required Files: 
  - gdprowth.R
  - gdprowth.csv
  - titanic.R
  - TitanicSurvival.csv

####Recommended Readings:
  - [a few introductory slides](notes/STA380intro.pdf)
  - [Jeff Leek's guide to sharing data](https://github.com/jtleek/datasharing)  
  - [Introduction to RMarkdown](http://rmarkdown.rstudio.com)  
  - [Introduction to GitHub](https://help.github.com/articles/set-up-git/) 

####Recommended Learning Tasks:
  - Sign up for a github account
  - Clone the class repository

Data Visualization: Plotting Do's and Dont's
---------------------

##Additional Readings:
  - [NYT 2014 Year in Interactive Storytelling](http://www.nytimes.com/interactive/2014/12/29/us/year-in-interactive-storytelling.html)
  - [An Interview with Edward Tufte](http://www.washingtonmonthly.com/magazine/mayjune_2011/features/the_information_sage029137.php?page=all)
  - [Typical projections in three dimensional space](https://en.wikipedia.org/wiki/Parallel_projection)

  
Plots, graphs and other forms of data visualization can be utilized to make convoluted or confusing data quick and easy to understand. Plots of data should be used to make comparisons between related entities with *sufficient*, *truthful*, and *multivariate* relationships. Good statistical graphics are vehicles for promoting accurate comparison, especially for large datasets that are not easy to understand intuitively. (This means no pie charts!)

There are elements common to all excellent statistical plots:
- Simple numbers for simple data
- Are labeled, scaled and easy to comprehend
- Truthful in magnitude
- Do not contain excessive 'chart junk'
- A meaningful, compelling display of multivariate data 
- They imbue the viewer with understanding of a complex topic

Most bad plots break the above rules and do the following:
- Lack a clear comparison between variable
- Use insufficient quantities or qualities of data; i.e. the representation of the data is derived from a biased sample, cannot be reproduced or is simply too small to make accurate predictions
- Misrepresent the truth; i.e. variations in values, omitted values, incorrect data, distortion of relative size, etc.
- Are not meaningful, or offer no valuable insight 
- Lack a key or labels altogether, or are labeled incorrectly 
- Are difficult to understand, or is easily misinterpreted: (note- the eye will pick up on size, color and other ques and make inaccurate assumptions, be mindful of this) 
- Encompass chart junk that detracts from , or misrepresents the data
- Are biased, and bend truths to back an argument 



The following is a series of plots with commentary on their execution (for better or worse).

Misleading axes violate the *truthfulness* of the data you are representing:

![](https://cloud.githubusercontent.com/assets/13579628/8998562/c9150c30-36f4-11e5-8d5c-228726d24181.png)

As do percentages that don't add up:

![](https://cloud.githubusercontent.com/assets/13579628/8998597/43e95a42-36f5-11e5-894f-63a69c669d91.png)

Distorting relative sizes can be a real hazard in 3D respresentations (see reading listed under section heading):

![](https://cloud.githubusercontent.com/assets/13579628/8999032/2b4ddc06-36fa-11e5-8f52-eaf6ded33fe3.png)

Plots should leverage human pattern recognition to simplify dense information, not make trivial comparisons. Low information density with a elaborate presentation is an example of chart junk:

![](https://cloud.githubusercontent.com/assets/13579628/8999034/3896d872-36fa-11e5-88c7-0386908542fa.png)

Compare what we've seen so far to one of the most famous information graphics in history, French civil engineer Joseph Minard's *Carte figurative des pertes successives en hommes de l'Armée Française dans la campagne de Russie 1812-1813*. This hand-drawn combination of map and Sankey Diagram contains information on the path of Napoleon's Grande Armée, major battle locations and dates, the strength of his forces, and the air temperature. One can easily understand the terrible nature of events leading to the loss of over 95% of Napoleon's forces.

![](https://upload.wikimedia.org/wikipedia/commons/thumb/2/29/Minard.png/1920px-Minard.png)

Another excellent example is Nicholas Felton's 'Annual Report' in which he documents each year of his life in infographic form. (http://feltron.com/)

![](http://feltron.com/images/FAR13_04.jpg)

####Chart Types

