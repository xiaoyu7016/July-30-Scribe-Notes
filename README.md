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

####Supplemental Materials:
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

####A Brief List of Chart Types
- *Tables* are used to organize exact amounts of data and to display numerical information. Tables do not show visual comparisons. As a result, tables take longer to read and understand. It is more difficult to examine overall trends and make comparisons with tables, than it is with graphs.
- *Line graphs* are used to display data or information that changes continuously over time. Line graphs allow us to see overall trends such as an increase or decrease in data over time.
- *Bar graphs* are used to compare facts. The bars provide a visual display for comparing quantities in different categories or groups. Bar graphs help us to see relationships quickly. However, bar graphs can be difficult to read accurately. A change in the scale in a bar graph may alter one's visual perception of the data.
- *Circle graphs* are used to compare the parts of a whole. Circle graphs represent data visually in the same proportion as the numerical data in a table: The area of each sector in a circle graph is in the same proportion to the whole circle as each item is to the total value in the table. Constructing an accurate circle graph is difficult to do without a computer. This is because you must first find each part of the whole through several elaborate calculations and then use a protractor to draw each angle. This leaves a lot of room for human error. Circle graphs are best used for displaying data when there are no more than five or six sectors, and when the values of each sector are different. Otherwise they can be difficult to read and understand.

Exercises in R - Basic Plotting and Measures of Association
---------------------
####Supplemental Materials:
  - [Statistical Robustness](https://en.wikipedia.org/wiki/Robust_statistics)
  - [Statistical Association](https://en.wikipedia.org/wiki/Association_(statistics))
  - [Pearson Correlation](https://en.wikipedia.org/wiki/Pearson_product-moment_correlation_coefficient)
  - [Spearman Correlation](https://en.wikipedia.org/wiki/Spearman%27s_rank_correlation_coefficient)
  - [Examples of simple plotting in R](http://www.harding.edu/fmccown/r/)
  - [Contingency Tables](http://onlinestatbook.com/2/chi_square/contingency.html)
  - [Relative Risk](https://en.wikipedia.org/wiki/Relative_risk)

#####Robustness
A robust statistic is resistant to errors in the results, produced by deviations from assumptions[1] (e.g., of normality). This means that if the assumptions are only approximately met, the robust estimator will still have a reasonable efficiency, and reasonably small bias, as well as being asymptotically unbiased, meaning having a bias tending towards 0 as the sample size tends towards infinity.
  - The median is a robust measure of central tendency, while the mean is not. The median has a breakdown point of 50%, while the mean has a breakdown point of 0% (a single large observation can throw it off).
  - The median absolute deviation and interquartile range are robust measures of statistical dispersion, while the standard deviation is not.

#####Getting into the R scripts (gdprowth.R and titanic.R)

Let's start by looking at gdpgrowth. First we'll load some useful libraries for plotting:
> library(mosaic)
> library(foreach)

Now we'll read in the gpdgrowth.csv and print out the first 6 rows to get a sense of what we are working with.
> gdpgrowth = read.csv('./data/gdpgrowth.csv', header=TRUE)
> head(gdpgrowth)

Suppose we want to plot the relationship between GDP growth rate and defense spending. Note the attributes for labeling axes.

> plot(gdpgrowth$DEF60, gdpgrowth$GR6096,
>	pch=19, col='grey',
>	xlab='Fraction GDP spent on national defense (1960)',
>	ylab='GDP growth rate, 1960-1996')


We could also use a boxplot to examine GDP growth in East Asian countries and other countries.
> boxplot(GR6096 ~ EAST, data=gdpgrowth,
> xlab='East Asian?',
> ylab='GDP growth rate, 1960-1996')

It's also possible to stratify by categorical variables using a lattice (or trellis) plot
> xyplot(GR6096 ~ DEF60 | EAST, data=gdpgrowth)


Go back to the scatterplot... Whoa! Who's the outlier? 
> plot(gdpgrowth$DEF60, gdpgrowth$GR6096,
> pch=19, col='grey',
> xlab='Fraction GDP spent on national defense (1960)',
> ylab='GDP growth rate, 1960-1996')

We can select points in R plots and allow R to return information using identify(). Make sure to click on the point of interest.
> outlier = identify(gdpgrowth$DEF60, gdpgrowth$GR6096, n=1)
> gdpgrowth[outlier,]

Jordan is probably having a large impact on the correlation of out chosen data. We can calculate the correlation using:
> cor(gdpgrowth$DEF60, gdpgrowth$GR6096)

Similiarly, we calculate the correlation without Jordan by calling our data set with [-outlier] applied.
> cor(gdpgrowth$DEF60[-outlier], gdpgrowth$GR6096[-outlier])

So, we can see that the Pearson Correlation is not robust; a single outlier value can dramatically impact the correlation that we calculate. What about a more robust measure of correlation - Spearman's rank correlation? We can apply the argument "method ='spearman'" to our cor() function to compute correlation by rank.

> cor(gdpgrowth$DEF60, gdpgrowth$GR6096, method='spearman')
> cor(gdpgrowth$DEF60[-outlier], gdpgrowth$GR6096[-outlier], method='spearman')

Let's switch to the titanic survivor's dataset to get an understanding of contingency tables and relative risk.

We have data on all passengers from the titanic, their age, gender, and status after the sinking accident.
> library(mosaic)
> TitanicSurvival = read.csv('./data/TitanicSurvival.csv')

Of interest to us is the relationship between male and female survivor rates. We can use xtabs() to compute a contingency table, a type of table displaying the frequency distribution of variables.
> t1 = xtabs(~sex + survived, data=TitanicSurvival)
> t1
> p1 = prop.table(t1, margin=1)
> p1

We can calculate the relative risk of dying for both men and women using the contingency table!
> risk_female = p1[1,1]
> risk_male = p1[2,1]
> relative_risk = risk_male/risk_female
> relative_risk

Mathematically, this can be expressed as RR = P(Y=1 | X=1) / P(Y=1 | X=0). So the relative risk of perishing as a male onboard the Titanic is: RR = [(Men Perished)/(All Males)] / [(Females Perished)/(All Females)]

As a side note, the odds ratio could also be computed as the ratio of the odds, rather than the risks. This would be calculated as OR = [(Men Perished)/(Surviving Males)] / [(Females Perished)/(Surviving Females)]

Both of these measures are common in epidemeology, along with the absolute risk ratio.
