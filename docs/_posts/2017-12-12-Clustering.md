---
layout: post
title: "Clustering"
---




### Introduction

Introduction 


### Kmeans map

Intro
<figure>
<select onchange="theThingToDoIfItChange()" id="selection">
	  <option value="kmeans2">kmeans2</option>
      <option value="kmeans3">kmeans3</option>
      <option value="kmeans4">kmeans4</option>
      <option value="kmeans5">kmeans5</option>
</select>
</figure>

<img src="{{ site.github.url }}/assets/data/map_ml/kmeans2.png" id="image">
<a href="{{ site.github.url }}/assets/data/map_ml/kmeans2.html" id="map"> see the full html here
<p id="text">Hello World!</p>

	
<figure>
	<script type="text/javascript">
		function theThingToDoIfItChange(){
			
			let image = document.getElementById("image");
			let map = document.getElementById("map");
			
			let selected = document.getElementById("selection").value;
			
			image.setAttribute("src","{{ site.github.url }}/assets/data/map_ml/"+selected+".png");
			map.setAttribute("href","{{ site.github.url }}/assets/data/map_ml/"+selected+".html");
			document.getElementById("text").innerHTML = dict [selected];
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
analyse results

discuss results


## DBSCAN
Presentation

<img src="{{ site.github.url }}/assets/data/map_ml/DBSCAN.png" id="image">
<a href="{{ site.github.url }}/assets/data/map_ml/DBSCAN.html" id="map"> see the full html here
<p id="text">Describe DBSCAN</p>

analyse results

discuss results



## Conclusion 

