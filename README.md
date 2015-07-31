# July-30-Scribe-Notes


Module 1: Exploratory Analysis
====================

Required Files: 
  - gdprowth.R
  - gdprowth.csv
  - titanic.R
  - TitanicSurvival.csv

Recommended Readings:
  - [a few introductory slides](notes/STA380intro.pdf)
  - [Jeff Leek's guide to sharing data](https://github.com/jtleek/datasharing)  
  - [Introduction to RMarkdown](http://rmarkdown.rstudio.com)  
  - [Introduction to GitHub](https://help.github.com/articles/set-up-git/) 

Recommended Learning Tasks:
  - Sign up for a github account
  - Clone the class repository

Data Visualization: Plotting Do's and Dont's
---------------------

Additional Readings:
  - [NYT 2014 Year in Interactive Storytelling](http://www.nytimes.com/interactive/2014/12/29/us/year-in-interactive-storytelling.html)
  - [An Interview with Edward Tufte](http://www.washingtonmonthly.com/magazine/mayjune_2011/features/the_information_sage029137.php?page=all)

  
Plots, graphs and other forms of data visualization can be utilized to make convoluted or confusing data quick and easy to understand. Plots of data should be used to make comparisons between related entities with *sufficient*, *truthful*, and *multivariate* relationships. Good statistical graphics are vehicles for promoting accurate comparison, especially for large datasets that are not easy to understand intuitively. (This means no pie charts!)

The following is a series of plots with commentary on their execution (for better or worse).

Misleading axes violate the *truthfulness* of the data you are representing:

![](https://cloud.githubusercontent.com/assets/13579628/8998562/c9150c30-36f4-11e5-8d5c-228726d24181.png)

As do percentages that don't add up:

![](https://cloud.githubusercontent.com/assets/13579628/8998597/43e95a42-36f5-11e5-894f-63a69c669d91.png)

Distorting relative sizes can be a real hazard in 3D respresentations:

![](https://cloud.githubusercontent.com/assets/13579628/8998562/c9150c30-36f4-11e5-8d5c-228726d24181.png)

Plots should leverage human pattern recognition to simplify dense information, not make trivial comparisons:

![](https://cloud.githubusercontent.com/assets/13579628/8998562/c9150c30-36f4-11e5-8d5c-228726d24181.png)

Compare what we've seen so far to one of the most famous information graphics in history. French civil engineering Charles Joseph Minard's *Carte figurative des pertes successives en hommes de l'Armée Française dans la campagne de Russie 1812-1813*. This combination of map and Sankey Diagram contains information on the path of Napoleon's Grande Armée, major battlefields, the strength of his forces, and the air temperature. One can easily understand the terrible nature of events leading to the loss of over 95% of Napoleon's forces.

![](https://upload.wikimedia.org/wikipedia/commons/thumb/2/29/Minard.png/1920px-Minard.png)
