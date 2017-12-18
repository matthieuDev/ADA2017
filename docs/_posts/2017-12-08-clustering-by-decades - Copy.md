---
layout: post
title: "Clustering by Decades"
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
   <input type="button" onclick="display_mult()" id="mult_button" value="Display all years">

</div>
</figure>

<figure>
<select onchange="theThingToDoIfItChange()" id="selection_cluster">
      <option value="kmeans2">kmeans2</option>
      <option value="kmeans3">kmeans3</option>
      <option value="kmeans4">kmeans4</option>
      <option value="kmeans5">kmeans5</option>
	  <option value="DBSCAN">DBSCAN</option>
</select>
</figure>





<div style="" id="one_year">
<figure>
<select onchange="theThingToDoIfItChange()" id="selection_year">
      <option value="1980">1981to1989</option>
      <option value="1990">1990to1999</option>
      <option value="2000">2000to2009</option>
      <option value="2010">2010to2017</option>
</select>
</figure>



<img src="{{ site.github.url }}/assets/data/decade/1980/kmeans2.png" id="image_cluster">
<a href="{{ site.github.url }}/assets/data/decade/1980/kmeans2.html" id="map_cluster"> see the full html here</a>

<div style="display: none;" id="pca_div">
<img src="{{ site.github.url }}/assets/data/maps_theme_ml/EconomyPCAA_kmeans2.png" id="pca_image">
</div>
<p id="text">Hello World!</p>
</div>

<div style="display: none;" id="all_year">
  <img src="{{ site.github.url }}/assets/data/decade/1980/kmeans2.png" id="image_cluster_1980">
<a href="{{ site.github.url }}/assets/data/decade/1980/kmeans2.html" id="map_cluster_1980"> see the full html here 
<div style="display: none;" id="pca_div_1980">
<img src="{{ site.github.url }}/assets/data/decade/1980/PCAA_kmeans2.png" id="pca_image_1980">
</div>

  <img src="{{ site.github.url }}/assets/data/decade/1990/kmeans2.png" id="image_cluster_1990">
<a href="{{ site.github.url }}/assets/data/decade/1990/kmeans2.html" id="map_cluster_1990"> see the full html here 
<div style="display: none;" id="pca_div_1990">
<img src="{{ site.github.url }}/assets/data/decade/1990/PCAA_kmeans2.png" id="pca_image_1990">
</div>

  <img src="{{ site.github.url }}/assets/data/decade/2000/kmeans2.png" id="image_cluster_2000">
<a href="{{ site.github.url }}/assets/data/decade/2000/kmeans2.html" id="map_cluster_2000"> see the full html here 
<div style="display: none;" id="pca_div_2000">
<img src="{{ site.github.url }}/assets/data/decade/2000/PCAA_kmeans2.png" id="pca_image_2000">
</div>

  <img src="{{ site.github.url }}/assets/data/decade/2010/kmeans2.png" id="image_cluster_2010">
<a href="{{ site.github.url }}/assets/data/decade/2010/kmeans2.html" id="map_cluster_2010"> see the full html here 
<div style="display: none;" id="pca_div_2010">
<img src="{{ site.github.url }}/assets/data/decade/2010/PCAA_kmeans2.png" id="pca_image_2010">
</div>
<p id="text_all">Hello World!</p>
</div>




	
<figure>
	<script type="text/javascript">
		function theThingToDoIfItChange(){
			
			
			let selected_decade = document.getElementById("selection_year").value;
			let selected_cluster = document.getElementById("selection_cluster").value;
			
		
			let image_cluster = document.getElementById("image_cluster");
			let map_cluster = document.getElementById("map_cluster");
			
			
			
			image_cluster.setAttribute("src", "{{ site.github.url }}/assets/data/decade/"+selected_decade+"/"+selected_cluster+".png");
			map_cluster.setAttribute("href","{{ site.github.url }}/assets/data/decade/"+selected_decade+"/"+selected_cluster+".html");
			
			let image_pca = document.getElementById("pca_image");
			
				image_pca.setAttribute("src", "{{ site.github.url }}/assets/data/decade/"+selected_decade+"/PCAA_"+selected_cluster+".png");
			
			
			var i = 1980;
			while (i<2020){
				document.getElementById("image_cluster_"+i).setAttribute("src", "{{ site.github.url }}/assets/data/decade/"+i+"/"+selected_cluster+".png");
				document.getElementById("map_cluster_"+i).setAttribute("href", "{{ site.github.url }}/assets/data/decade/"+i+"/"+selected_cluster+".html");;
				document.getElementById("pca_image_"+i).setAttribute("src", "{{ site.github.url }}/assets/data/decade/"+i+"/PCAA_"+selected_cluster+".png");;
				i = i + 10 ;
			}
			
			document.getElementById("text").innerHTML = dict[selected_cluster+"/"+selected_decade];
			document.getElementById("text_all").innerHTML = dict[selected_cluster];
		};
		
		
		
		function display_pca() {
		let button = document.getElementById("pca_button");
		let div = document.getElementById("pca_div");
		
		if(button.value == "Display PCA") {
			button.setAttribute("value","Hide PCA");
			var i = 1980;
			while (i<2020){
				document.getElementById("pca_div_"+i).setAttribute("style","");
				i = i + 10 ;
			}
			
			
			div.setAttribute("style","");
			
		}else {
			button.setAttribute("value","Display PCA");
			div.setAttribute("style","display: none;");
			var i = 1980
			while (i<2020){
				document.getElementById("pca_div_"+i).setAttribute("style","display: none;");
				i = i + 10 ;
			}
		};
		};
		
		
		function display_mult() {
		let button = document.getElementById("mult_button");
		let all_year = document.getElementById("all_year");
		let one_year = document.getElementById("one_year");
		
		if(button.value == "Display all years") {
			button.setAttribute("value","Display one year");
			all_year.setAttribute("style","");
			one_year.setAttribute("style","display: none;");
		}else {
			button.setAttribute("value","Display all years");
			all_year.setAttribute("style","display: none;");
			one_year.setAttribute("style","");
			
		};
		
		};
		
		
		var dict = {
      "DBSCAN/1980": "describe DBSCAN for 1980",
      "DBSCAN/1990": "describe DBSCAN for 1990",
      "DBSCAN/2000": "describe DBSCAN for 2000",
      "DBSCAN/2010": "describe DBSCAN for 2010",
      "kmeans2/1980": "describe kmeans2 for 1980",
      "kmeans2/1990": "describe kmeans2 for 1990",
      "kmeans2/2000": "describe kmeans2 for 2000",
      "kmeans2/2010": "describe kmeans2 for 2010",
      "kmeans3/1980": "describe kmeans3 for 1980",
      "kmeans3/1990": "describe kmeans3 for 1990",
      "kmeans3/2000": "describe kmeans3 for 2000",
      "kmeans3/2010": "describe kmeans3 for 2010",
      "kmeans4/1980": "describe kmeans4 for 1980",
      "kmeans4/1990": "describe kmeans4 for 1990",
      "kmeans4/2000": "describe kmeans4 for 2000",
      "kmeans4/2010": "describe kmeans4 for 2010",
      "kmeans5/1980": "describe kmeans5 for 1980",
      "kmeans5/1990": "describe kmeans5 for 1990",
      "kmeans5/2000": "describe kmeans5 for 2000",
      "kmeans5/2010": "describe kmeans5 for 2010",
	  "DBSCAN": "describe DBSCAN",
      "kmeans2": "describe kmeans2",
      "kmeans3": "describe kmeans3",
      "kmeans4": "describe kmeans4",
      "kmeans5": "describe kmeans5"
      };


		document.getElementById("text").innerHTML = dict ["kmeans2/1980"];
		document.getElementById("text_all").innerHTML = dict ["1980"];
	</script>
</figure>
analyse results

discuss results

## Conclusion 

