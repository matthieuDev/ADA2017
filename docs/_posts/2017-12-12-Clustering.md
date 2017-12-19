---
layout: post
title: "Clustering"
---




### Introduction

In this part, we are going to take a closer look at our votations data and try to identify distinct communities with different votation pattern in Switzerland. In order to do so, we will use only the votation dataset and more specifically the results (in % Yes) of all the the municipalities for all the votations since 1981 to nowadays as one single period of time (we are going to make the same exercise in a later post but analysing the data per decades). The clustering methods used here are Kmeans and DBSCAN introduced earlier. 


### Kmeans map



<input type="button" onclick="display_pca()" id="pca_button" value="Display PCA">

<figure>
<select onchange="theThingToDoIfItChange()" id="selection">
	  <option value="kmeans2">Kmeans, k=2</option>
      <option value="kmeans3">kmeans, k=3</option>
      <option value="kmeans4">kmeans, k=3</option>
      <option value="kmeans5">kmeans, k=4</option>
</select>
</figure>

<img src="{{ site.github.url }}/assets/data/map_ml/kmeans2.png" id="image">
<a href="{{ site.github.url }}/assets/data/map_ml/kmeans2.html" id="map"> see the full html here
<p id="text">Hello World!</p>

<div style="display: none;" id="pca_div">
<img src="{{ site.github.url }}/assets/data/map_ml/PCAA_kmeans2.png" id="pca_image">
</div>

###Analysis


	
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
