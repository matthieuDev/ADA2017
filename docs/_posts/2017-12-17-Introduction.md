---
layout: post
title: "Introduction"
---

This project consists of a data analysis of Swiss votations results from 1981 to nowadays. Switzerland is a unique case study in the world in the sense that it is the only country that implements direct democracy, as opposed to most countries' representative democracies where people delegate their voting power to the decision-makers they elect, which means that only 0.1% of the world's population gets the opportunity to make direct decisions over changes to their national constitution. Language divides, as we will see it just below, will make that work even more interesting.

We seek to use the data from the Federal Office of Statistics about votations to gain an insight of political trends in the country. Switzerland being at the crossroads of three of the major Western European languages, it is understandable that cultural differences will unavoidably emerge. It must be noted that this country is one of the only developed countries to have such a linguistic variety (we may also cite Belgium and Canada). Still, it does not prevent a strong national cohesion. However, each region is influenced by different news channels and ideologies in line with the language spoken (e.g. French-speaking citizens are more influenced by French authors and politics than the German-speaking citizens and same goes the other way with Germany). Note that this should be particularly true before the internet era and the sharing of news and opinions on a global scale that we witness today.

The term _Röstigraben_ (_Rösti_ is a typical Swiss-German dish, _Graben_ is Swiss-German for "ditch") has long been used in Switzerland to describe to cultural differences between the German-speaking and the French-speaking part of Switzerland. Similarly, the term _Polentagraben_ (_Polenta_ is a typical Swiss-Italian dish) is used to refer about the cultural diffences between the Italian-speaking part of the country and the rest. However can we see such differences in the votating trends of these communities? If so, is it something that evolved since 1981? Is there specific topics of votation which show no cultural splits or on the contrary any topics which show a clear divide? Do we observe the emergence of multiple identities among the same nation?

Several articles have been written on the subject and the _Röstigraben_ phenomenon is part of common political talk in Switzerland. However, evidence has emerged that these differences have been attenuated today to leave another kind of split: a gap in voting patterns between urban areas and the countryside. Can we verify this statement? Are there other demographic explanations?

These are questions we will try to answer using our data.

# Research questions

Here are the main questions we asked ourselves when we started working on this project:

1. **Röstigraben, Polentagraben, countryside-cities split:**
Our main point of focus is to observe political division in Switzerland, and its correlation with different cultural aspects such as language and urban status. Is there a recurrence in the splits during votations? Do they differ depending on the topics?

2. **Outliers:**
We are interested to find out about entities that we may call "chronical winners" and "chronical losers", in other words cantons/regions/towns that are often on parity with votation results and those that often vote the opposite. Is it a phenomenon limited to few entities or a common one?

# Dataset

The main dataset being used is the results of all the popular votations from 1981 to May 2017 in Switzerland published by Swiss Federal Statistical Office. The dataset is available [here](https://www.bfs.admin.ch/bfs/fr/home/statistiques/politique/votations.assetdetail.3362356.html).

The data are available as HTML tables that can be parsed using the _requests_ library and the convenient pandas function _read\_html_. The only small issue here is that the entire table is not available at once, it is then necessary to scrap multiple small table and then merge them, which is what we do in the notebook named `bfs_scrap.ipynb`.

Note that votes are anonymized. Thus, it is not possible to get reliable data on an individual basis (fortunately for the voters). However, it is possible to enrich our dataset, as we need, with demographical data for each town also published by the Swiss Federal Statistical Office. These data are always available either as Excel spreadsheets or HTML tables. In both cases we managed to easily parse them and integrate them.

# Objectives
Our main objective in this project is to implement machine learning techniques, namely K-Means and DBSCAN to generate clusters of similarly voting communities using the votation data in order to determine the existence of political divides in Switzerland. With the data we have, it is thus possible to observe not only the divides, but their evolution over time or their status depending on the theme of the vote. Our reasoning behind this idea is that we feel it is extremely arbitrary to sort votation topics by how liberal or conservative they are, and thus we cannot just aggregate votation scores together to get "liberal scores" for each region.

To visualize our data, we use the `Folium` plugin for Python to generate maps using our results and geographical data taken from [OpenStreetMap.org](www.openstreetmap.org) that we have slightly modified for various reasons, including community mergers, wrong orthograph in names of locations and various inconsistencies with the boundaries of certain communities.


# Introduction structure of the story
sommaire
pk les donnees sont presentes comme ca
A FAIRE QUAND LE RESTE EST FAIT

