---
layout: post
title: "Theme Cluster"
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
<select onchange="theThingToDoIfItChange()" id="selection_theme">
      <option value="Economy">Economy</option>
      <option value="Education,culture,media">Education,culture,media</option>
      <option value="Foreign policy">Foreign policy</option>
      <option value="Infrastructure, planning, environment">Infrastructure, planning, environment</option>
      <option value="Political regime">Political regime</option>
      <option value="public finances">public finances</option>
      <option value="security policy">security policy</option>
      <option value="social policies">social policies</option>
      <option value="Economy">Economy</option>
      <option value="Education,culture,media">Education,culture,media</option>
      <option value="Foreign policy">Foreign policy</option>
      <option value="Infrastructure, planning, environment">Infrastructure, planning, environment</option>
      <option value="Political regime">Political regime</option>
      <option value="public finances">public finances</option>
      <option value="security policy">security policy</option>
      <option value="social policies">social policies</option>
</select>

<select onchange="theThingToDoIfItChange()" id="selection_cluster">
	  <option value="kmeans">kmeans</option>
	  <option value="DBSCAN">DBSCAN</option>
</select>

</figure>








<div style="display: none;" id="comp_div">
<img src="{{ site.github.url }}/assets/data/map_theme/map_AdI.png" id="image">
<a href="{{ site.github.url }}/assets/data/map_theme/map_AdI.html" id="map"> see the full html here</a>
</div>

<img src="{{ site.github.url }}/assets/data/maps_theme_ml/kmeans_Economy.png" id="image_cluster">
<a href="{{ site.github.url }}/assets/data/maps_theme_ml/kmeans_Economy.html" id="map_cluster"> see the full html here</a>

<div style="display: none;" id="pca_div">
<img src="{{ site.github.url }}/assets/data/maps_theme_ml/EconomyPCAA_kmeans2.png" id="pca_image">
</div>


<p id="text">Hello World!</p>

	
<figure>
	<script type="text/javascript">
		function theThingToDoIfItChange(){
			
			let image = document.getElementById("image");
			let map = document.getElementById("map")
			
			let selected_theme = document.getElementById("selection_theme").value;
			let selected_cluster = document.getElementById("selection_cluster").value;
			
			image.setAttribute("src","{{ site.github.url }}/assets/data/map_theme/map_"+selected_theme+".png");
			map.setAttribute("href","{{ site.github.url }}/assets/data/map_theme/map_"+selected_theme+".html");
			
			
			let image_cluster = document.getElementById("image_cluster");
			let map_cluster = document.getElementById("map_cluster");
			
			
			
			image_cluster.setAttribute("src", "{{ site.github.url }}/assets/data/maps_theme_ml/"+selected_cluster+"_"+selected_theme+".png");
			map_cluster.setAttribute("href","{{ site.github.url }}/assets/data/maps_theme_ml/"+selected_cluster+"_"+selected_theme+".html");
			
			let image_pca = document.getElementById("pca_image");
			if (selected_cluster == "kmeans"){
				image_pca.setAttribute("src", "{{ site.github.url }}/assets/data/maps_theme_ml/"+selected_theme+"PCAA_kmeans2.png");
			}else {
				image_pca.setAttribute("src", "{{ site.github.url }}/assets/data/maps_theme_ml/"+selected_theme+"PCAA_"+selected_cluster+".png");
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
      "Economy": "describe Economy",
      "Education,culture,media": "describe Education,culture,media",
      "Foreign policy": "describe Foreign policy",
      "Infrastructure, planning, environment": "describe Infrastructure, planning, environment",
      "Political regime": "describe Political regime",
      "public finances": "describe public finances",
      "security policy": "describe security policy",
      "social policies": "describe social policies",
      "Economy": "describe Economy",
      "Education,culture,media": "describe Education,culture,media",
      "Foreign policy": "describe Foreign policy",
      "Infrastructure, planning, environment": "describe Infrastructure, planning, environment",
      "Political regime": "describe Political regime",
      "public finances": "describe public finances",
      "security policy": "describe security policy",
      "social policies": "describe social policies",
      };


		document.getElementById("text").innerHTML = dict ["map_AdI"];
		
	</script>
</figure>
analyse results

discuss results

## Conclusion 

