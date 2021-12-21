# danwbeeston.github.io

My site is designed to be used a marking starting point. 
There are links to relevant documents for each graph on there.

This document is just a copy of the project 'write up'. 




Project Aim: 

It was once a truism in the West that economic advancement naturally led to social liberalization. 
Poorer nations, once they had amassed wealth, would adopt a style of governance similar to that of western democracy. 

However, recent statements from the Chinese and Russian authorities claim this truism is false.
They believe growth and freedom are not fundamentally linked and that it is possible to have flourishing autocracies. 
This project aims to test this and answer:

1.	What is the relationship between Growth and Freedom?

2.	If growth and freedom are not synonymous, which is more important for the happiness of a nation’s citizens?




The data you used, how you accessed it, including notes on automation/replication; 

For gaining data on GDP per Capita, Populations and GDP Growth, I used the trusted FRED and World Bank databases and accessed their json and csv files.
A data join was used to compile some of these. 
The FRED downloads were originally intended to be APIs but worked more reliable when automatically downloaded periodically using python code (Project Chart 6).

For access to the Human Freedom Index, I downloaded csv’s directly from the Cato Institute. 
The Democracy Index was scraped from Wikipedia using Colab/Python. 
Happiness Data was accessed through an API created by Norman Lo that sources data from the World Happiness Project. 
Lo’s project is a frequently updated open-source project which combines happiness, population size, GDP per capita and Gini co-efficients.


Challenges in data cleaning and/or analysis, and the tools you used to overcome them;

The greatest challenge in data cleaning was compiling the various csv files into the document ‘Project Megasheet Data’. 
This was because many databases use different lists of countries (some including data for sub-regions such as “OECD” “EU”) 
and countries have different names (e.g. Eswatini vs Swaziland). Time was spent manually aligning country columns before a data join was performed. 
Between some sets, data joins were beyond my skill due to datasets being in long-form / wide-form in a way that couldn’t be easily converted. 
These had to be cleaned in Excel. 
There were fewer problems in analysis beyond coming to terms with using Vega-lite and nesting layers correctly. 
These were largely resolved using online tutorials and reading the Vega documentation carefully. 
However, many initial graphs of this project did not show correlations. These were abandoned or refined as the project when along. 
Also, there were issues using non-linear regressions on my interactive charts, I instead opted to use a loess regression which better captures the curve of my LoBF. 




Conclusions:


We can see that there is generally a positive correlation between freedom and GDP per capita up until GDP per capita exceeds $50k, 
at which point increases in wealth do not seem to impact freedom. 
The outliers are typically relatively small oil-exporting nations such as the UAE and Qatar. 
We also see that freedom has a slight negative correlation with GDP growth in 2008 but this trend weakens in 2018. 

Combining these diagrams, we see that as nations increase their GDP per capita, their freedoms typically increase and their growth rates 
diminishes until they join the western democracy cluster. China, whilst slightly richer per capita than the trend would predict, is not 
significantly enough away to suggest the trend has been broken. Whilst Russia is moderately richer than the trend would predict, it is 
joined by other oil exporters. This evidence supports the original truism that wealth equals freedom, with the caveat ‘unless you have oil’.



An increase in GDP per Capita does lead to an increase in happiness, dramatically at first, however after $50k the trend once again disappears.
However, there are many nations with very similar wealth levels but with drastically different happiness levels, what causes this? It doesn’t 
seem to be distribution of wealth (as signified by the Gini-Co-efficient). But by taking three above-trend, ‘over-happy’ nations and three 
below-trend, ‘under-happy’ nations we can see how growth and freedom affect happiness. 

The ‘Over-Happy’ nations have typically seen an increase in their freedom over the last decade whilst ‘Under-Happy’ nations have seen a decrease
in freedom. Freedom strongly positively correlates with happiness.
Indexed growth since 2000 doesn’t seem to have a correlation.

We can therefore conclude that GDP per Capita and Freedom are both important to happiness, independently of one another. 


