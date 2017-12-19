---
layout: post
title: "Clustering"
---


### Introduction

In this part, we are going to take a closer look at our votations data and try to identify distinct communities with different votation patterns in Switzerland. In order to do so, we will use only the votation dataset and more specifically the results (in % Yes) of all the the municipalities for all the votations since 1981 to nowadays as one single period of time (we are going to make the same exercise in a later post but analysing the data per decades). The clustering methods used here are K-means and DBSCAN introduced earlier. Please note that the clustering is performed without dimension reduction as it is possible to run the algorithms in reasonable time. The PCA drown are here to verify if the clustering happened correctly, but the dimension reduction is performed _**after**_ the clustering.


### Kmeans maps

<input type="button" onclick="display_pca()" id="pca_button" value="Display PCA">

<figure>
<select onchange="theThingToDoIfItChange()" id="selection">
	  <option value="kmeans2">K-means, k=2</option>
      <option value="kmeans3">k-means, k=3</option>
      <option value="kmeans4">k-means, k=4</option>
      <option value="kmeans5">k-means, k=5</option>
</select>
</figure>

<img src="{{ site.github.url }}/assets/data/map_ml/kmeans2.png" id="image">
<a href="{{ site.github.url }}/assets/data/map_ml/kmeans2.html" id="map"> See the full map here</a>
<p id="text">Hello World!</p>

<div style="display: none;" id="pca_div">
<img src="{{ site.github.url }}/assets/data/map_ml/PCAA_kmeans2.png" id="pca_image">
</div>

### Analysis and discussion
#### K-means, k=2
When we try to classify our votation data into two categories, it is clear that two distinct communities appear. On one side the Romandy (French community) and on the other side the rest of Switzerland (German, Italian and Romansh communities). A reader may quickly take a look at our map of the languages spoken in Switzerland drawn in previous post.  Looking at the visualisation of the two first principal components of the PCA, we can see that the two categories are distinguishable by human eyes and the algorithm correctly classified them. Thus, we succesfully identify a _röschtigraben_ pattern in our data.

This result is very _**strong**_ and lets quickly explain _why_. The K-mean algorithm here is does not use any _geographical_ or _linguistic_ features, i.e., the algorithm is unaware of the geographical position of a municipality or the language spoken there. Yet, _except_ few municipalities in Ticino classified with Romandy and few municipalities in _Berner Jura_ (which are attached to the canton of Bern mainly German speaking), the algorithm classified the municipalities into two geographical/linguistical categories corresponding to the _exact_ linguistic frontier between the French and the German communities in Switzerland. The existence of differences in votations patterns between French speaking and German speaking citizens in _**undeniable**_.

It is also very important to note that K-means has essentially only one parameter which is the number of clusters. Thus, it is nearly impossible to influence it in order to _show a specific a result_. What may influence the final clusters in the iterative process of K-mean is the initial centers of the clusters and the number of iterations. In our case, we let _sklearn_ deals with its default values. Thus, the algorithm is run 10 times with different initial clusters centers chosen randomly with a maximum of 300 iterations if the convergence is not reached with fewer. The final result is the best classification of the 10 consecutive runs in terms of inertia, i.e., minimizing the within-cluster sum of squared.

#### K-means, k=3

	
analyse results

discuss results


## DBSCAN
Presentation

<input type="button" onclick="display_pca_DBSCAN()" id="pca_button_DBSCAN" value="Display PCA">

<img src="{{ site.github.url }}/assets/data/map_ml/DBSCAN.png" id="image">
<a href="{{ site.github.url }}/assets/data/map_ml/DBSCAN.html" id="map"> see the full html here

<div style="display: none;" id="pca_div_DBSCAN">
<img src="{{ site.github.url }}/assets/data/map_ml/PCAA_DBSCAN.png">
</div>

<p id="text">Describe DBSCAN</p>



analyse results

discuss results



## Conclusion 






<figure>
	<script type="text/javascript">
		function theThingToDoIfItChange() {
			
			let image = document.getElementById("image");
			let map = document.getElementById("map");
			
			let selected = document.getElementById("selection").value;
			
			image.setAttribute("src","{{ site.github.url }}/assets/data/map_ml/"+selected+".png");
			map.setAttribute("href","{{ site.github.url }}/assets/data/map_ml/"+selected+".html");
			document.getElementById("text").innerHTML = dict [selected];
			
			
			let image_pca = document.getElementById("pca_image");
			image_pca.setAttribute("src", "{{ site.github.url }}/assets/data/map_ml/PCAA_"+selected+".png");
			
		};
		
		
		function display_pca() {
		let button = document.getElementById("pca_button");
		let div = document.getElementById("pca_div");
		
		if(button.value == "Display PCA") {
			button.setAttribute("value","Hide PCA");
			div.setAttribute("style","");
			
		}else {
			button.setAttribute("value","Display PCA");
			div.setAttribute("style","display: none;");
		};
		};
		
		function display_pca_DBSCAN() {
		let button = document.getElementById("pca_button_DBSCAN");
		let div = document.getElementById("pca_div_DBSCAN");
		
		if(button.value == "Display PCA") {
			button.setAttribute("value","Hide PCA");
			div.setAttribute("style","");
			
		}else {
			button.setAttribute("value","Display PCA");
			div.setAttribute("style","display: none;");
		};
		};
		
		
		var dict = {
      "kmeans2": "describe kmeans2",
      "kmeans3": "describe kmeans3",
      "kmeans4": "describe kmeans4",
      "kmeans5": "describe kmeans5",
      };
		document.getElementById("text").innerHTML = dict ["map_Economy"];
		
	</script>
</figure>
