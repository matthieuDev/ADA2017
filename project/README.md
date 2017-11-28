# Data analysis of Swiss votations from 1981 to nowadays

# Abstract
We seek to use the data from the Federal Office of Statistics about votations to gain an insight of political trends in the country. The term _Röstigraben_ has been used in Switzerland to refer to cultural differences between the German-speaking and the French-speaking part of Switzerland. Similarly, the term _Polentagraben_ is used to refer about the Italian-speaking part of the country. However can we see such differences in the votations trends of these communities? If so, is it something that evolved since 1981? Is there specific topics of votation which show no cultural splits or on the contrary any topics which show a clear breaking?

Several articles have been written on the subject and the _Röstigraben_ have been reported to exist. However, recently it has been said that these differences have been attenuated today to see another kind of split: a gap in voting pattern between cities and countryside. Can we verify this statement? Is there other demographic explanations?

Votation patterns in Switzerland are particularly interesting as it is one of the only developed countries to have such linguistic splitting (we may also cite Belgium and Canada). Still it does not prevent to have a strong national cohesion. However, each region is influenced by different news channels and ideologies in line with the language spoken (e.g. French-speaking citizens are more influenced by French authors and politics than the German-speaking citizens and vice versa with Germany). Note that this should be particularly true before the internet era and the sharing of news and opinions on a global scale. Do we observe the emergence of multiple identities among the same nation?


# Research questions


1. Röstigraben, Polentagraben, countryside-cities splît
Our main point of focus is to observe political division in Switzerland, and its correlation with different cultural aspects such as language, confession, urban status, etc. Is there a recurrence in the splits during votations? Do they differ depending on the topics?

2. Outliers
We are interested to find out about entities that we may call "chronical winners" and "chronical losers", in other words cantons/regions/towns that are often on parity with votation results and those that often vote the opposite. Is it a phenomenon limited to few entities or common?

3. Visualization
We plan to illustrate our results by showing the contonal/regional/communal map of Switzerland colored according to the results of the different questions. This will really help the cultural/linguistic/religious differences to stand out.

# Dataset

The main dataset we plan to use is the results of all the popular votations from 1981 to May 2017 in Switzerland published by Swiss Federal Statistical Office. The dataset is available [here](https://www.bfs.admin.ch/bfs/fr/home/statistiques/politique/votations.assetdetail.3362356.html) (in French, not available in English): []().

The data are available as HTML tables that can be parsed using the _requests_ library and the convenient pandas function _read\_html_. The only small issue here is that the entire table is not available at once, it is then necessary to scrap multiple small table and then merge them (which is feasible). Note that we will translate the dataset in English (mainly column names). In this dataset, results of each votation are available at a town level (which is the lowest available possible level in Switzerland). The two level index of the table (here we use index as it is used in pandas) is the town (group by canton and district) and the object of the votation with its voting date. Columns are _ registered electors (#)_, _received ballots (#)_, _participation (%)_, _valid ballots (#)_, _YES (#)_, _NO (#)_, _YES (%)_.

The Swiss Federal Statistical Office classify each votation among each topics: 
- Political regime
- Foreign politic
- Security policy
- Economy
- Public finances
- Infrastructure, development, environment
- Social policy
- Education, culture and media

Unfortunately, we did not find each votation object already labeled. However, we can find the aggregated sum by topic for each year [here](https://www.bfs.admin.ch/bfs/fr/home/statistiques/politique/votations.assetdetail.3362351.html). We will label each votation object with its topic manually (in total there were 312 objects since 1981) and cross-check the consistency of our labelling with the aggregated sums.

Note that votes are anonymized. Thus, it is not possible to get reliable data on an individual basis (fortunately for the voters). However, it is possible to enrich our dataset, as we need, with demographical data for each town also published by the Swiss Federal Statistical Office. These data are always available either as xls(x) spreadsheets or HTML tables. In both cases we may easily parse and/or use them.

# A list of internal milestones up until project milestone 2
 - **November 7th** : Datasets are imported and cleaned. We expect to have at least some basic results about our main question, namely political division.
 
 - **November 14th** : We have completed the finding of interesting singularities in our data. Work on illustrating the results is started, but it is hard to know in advance how well the result will turn out. We now have clear results, division for different criterias, etc.

- **November 21st** : By then we expect to be set on how good our visualization can get and have selected what are the best things to show. A draft of the report (or story) is done with the main structure set.

# A list of internal milestones up until final milestone
 - **December 5th** : The ML implementation is complete. Ideas for pertinent uses of this technique are listed with stub graphs implemented.
 - **December 12th** : Graphs are complete, data story structure set.
 - **December 19th** : Work is complete.

# Next objectives
We plan to implement machine learning techniques to analyse divides within the country. To do this, we will create vectors of n dimensions, n being the number of votations. Each dimension will represent the score of the associated votation. We will then be able to compute which communities/districts/cantons are closer to each other, which will allow us to extract clusters of regions which will hopefully allow us to group regions and see whether "röstigraben" is still or thing, or if other divides have taken over. This will also be feasible per-theme. Our reasoning between this idea is that we feel it is not appropriate to sort votation topics by how liberal or conservative they are, and thus we cannot just aggregate votation scores together to get "liberal scores" for each region. We think our approach will allow us to understand the complexity of opinions in our country.

# Pending miscellaneous improvements
- The json map data represents certain lakes as communities. These will have to be ignored in the future to have clean maps.
- As many communities have merged over the years, our data needs some adjustments to take these changes in consideration correctly.
- We plan to give the maps a more elegant feel by not having the underlying topographic map, which is useless, underneath the data.

# Questions for TAa
 
 Not yet, but some will come during our work :)
