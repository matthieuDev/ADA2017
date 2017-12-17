---
layout: post
title: "Parti recommendation Cluster"
---



<head>
<style>
li {
    display: inline;
}
</style>
</head>

### Introduction

Introduction 


### Presentation map theme

Intro


<figure>
<div>
<input type="button" onclick="display_pca()" id="pca_button" value="Display PCA">
   <input type="button" onclick="display_comp()" id="comp_button" value="Display non cluster">

  </div>
  

</figure>

<figure>
<select onchange="theThingToDoIfItChange()" id="selection_party">
      <option value="AdI">AdI</option>
      <option value="DS">DS</option>
      <option value="Lega">Lega</option>
      <option value="MCR">MCR</option>
      <option value="PBD">PBD</option>
      <option value="PCS">PCS</option>
      <option value="PDC">PDC</option>
      <option value="PES">PES</option>
      <option value="PEV">PEV</option>
      <option value="PLR">PLR</option>
      <option value="PLS">PLS</option>
      <option value="POCH">POCH</option>
      <option value="PRD">PRD</option>
      <option value="PS">PS</option>
      <option value="PSL">PSL</option>
      <option value="PST">PST</option>
      <option value="PVL">PVL</option>
      <option value="Rep.">Rep.</option>
      <option value="UDC">UDC</option>
      <option value="UDF">UDF</option>
</select>

<select onchange="theThingToDoIfItChange()" id="selection_cluster">
	  <option value="kmeans">kmeans</option>
	  <option value="DBSCAN">DBSCAN</option>
</select>

</figure>








<div style="display: none;" id="comp_div">
<img src="{{ site.github.url }}/assets/data/maps_partis/map_AdI.png" id="image">
<a href="{{ site.github.url }}/assets/data/maps_partis/map_AdI.html" id="map"> see the full html here</a>
</div>

<img src="{{ site.github.url }}/assets/data/map_recommendation_cluster/kmeans_AdI.png" id="image_cluster">
<a href="{{ site.github.url }}/assets/data/map_recommendation_cluster/kmeans_AdI.html" id="map_cluster"> see the full html here

<div style="display: none;" id="pca_div">
<img src="{{ site.github.url }}/assets/data/map_recommendation_cluster/AdIPCAA_kmeans2.png" id="pca_image">
</div>


<p id="text">Hello World!</p>

	
<figure>
	<script type="text/javascript">
		function theThingToDoIfItChange(){
			
			let image = document.getElementById("image");
			let map = document.getElementById("map")
			
			let selected_party = document.getElementById("selection_party").value;
			let selected_cluster = document.getElementById("selection_cluster").value;
			
			image.setAttribute("src","{{ site.github.url }}/assets/data/maps_partis/map_"+selected_party+".png");
			map.setAttribute("href","{{ site.github.url }}/assets/data/maps_partis/map_"+selected_party+".html");
			
			
			let image_cluster = document.getElementById("image_cluster");
			let map_cluster = document.getElementById("map_cluster");
			
			
			
			image_cluster.setAttribute("src", "{{ site.github.url }}/assets/data/map_recommendation_cluster/"+selected_cluster+"_"+selected_party+".png");
			map_cluster.setAttribute("href","{{ site.github.url }}/assets/data/map_recommendation_cluster/"+selected_cluster+"_"+selected_party+".html");
			
			let image_pca = document.getElementById("pca_image");
			if (selected_cluster == "kmeans"){
				image_pca.setAttribute("src", "{{ site.github.url }}/assets/data/map_recommendation_cluster/"+selected_party+"PCAA_kmeans2.png");
			}else {
				image_pca.setAttribute("src", "{{ site.github.url }}/assets/data/map_recommendation_cluster/"+selected_party+"PCAA_"+selected_cluster+".png");
			};
			
			document.getElementById("text").innerHTML = dict[selected];
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
		
		
		function display_comp() {
		let button = document.getElementById("comp_button");
		let div = document.getElementById("comp_div");
		
		if(button.value == "Display non cluster") {
			button.setAttribute("value","Hide non cluster");
			div.setAttribute("style","");
			
		}else {
			button.setAttribute("value","Display non cluster");
			div.setAttribute("style","display: none;");
		};
		
		};
		
		
		var dict = {
      "AdI": "describe AdI",
      "DS": "describe DS",
      "Lega": "describe Lega",
      "MCR": "describe MCR",
      "PBD": "describe PBD",
      "PCS": "describe PCS",
      "PDC": "describe PDC",
      "PES": "describe PES",
      "PEV": "describe PEV",
      "PLR": "describe PLR",
      "PLS": "describe PLS",
      "POCH": "describe POCH",
      "PRD": "describe PRD",
      "PS": "describe PS",
      "PSL": "describe PSL",
      "PST": "describe PST",
      "PVL": "describe PVL",
      "Rep.": "describe Rep.",
      "UDC": "describe UDC",
      "UDF": "describe UDF",
      };


		document.getElementById("text").innerHTML = dict ["map_AdI"];
		
	</script>
</figure>
analyse results

discuss results

## Conclusion 

