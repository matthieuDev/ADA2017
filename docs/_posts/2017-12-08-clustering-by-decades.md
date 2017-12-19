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
	<input type="button" onclick="display_pca_clustbydec()" id="pca_button_clustbydec" value="Display PCA">
   <input type="button" onclick="display_mult_clustbydec()" id="mult_button_clustbydec" value="Display all years">

</div>
</figure>

<figure>
<select onchange="theThingToDoIfItChange_clustbydec()" id="selection_cluster_clustbydec">
      <option value="kmeans2">kmeans2</option>
      <option value="kmeans3">kmeans3</option>
      <option value="kmeans4">kmeans4</option>
      <option value="kmeans5">kmeans5</option>
	  <option value="DBSCAN">DBSCAN</option>
</select>
</figure>





<div style="" id="one_year">
<figure>
<select onchange="theThingToDoIfItChange_clustbydec()" id="selection_year_clustbydec">
      <option value="1980">1981to1989</option>
      <option value="1990">1990to1999</option>
      <option value="2000">2000to2009</option>
      <option value="2010">2010to2017</option>
</select>
</figure>



<img src="{{ site.github.url }}/assets/data/decade/1980/kmeans2.png" id="image_cluster_clustbydec">
<a href="{{ site.github.url }}/assets/data/decade/1980/kmeans2.html" id="map_cluster_clustbydec"> see the full html here</a>

<div style="display: none;" id="pca_div_clustbydec">
<img src="{{ site.github.url }}/assets/data/maps_theme_ml/EconomyPCAA_kmeans2.png" id="pca_image_clustbydec">
</div>
</div>

<div style="display: none;" id="all_year_clustbydec">
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

</div>




	
<figure>
	<script type="text/javascript">
		function theThingToDoIfItChange_clustbydec(){
			
			
			let selected_decade = document.getElementById("selection_year_clustbydec").value;
			let selected_cluster = document.getElementById("selection_cluster_clustbydec").value;
			
		
			let image_cluster = document.getElementById("image_cluster_clustbydec");
			let map_cluster = document.getElementById("map_cluster_clustbydec");
			
			
			
			image_cluster.setAttribute("src", "{{ site.github.url }}/assets/data/decade/"+selected_decade+"/"+selected_cluster+".png");
			map_cluster.setAttribute("href","{{ site.github.url }}/assets/data/decade/"+selected_decade+"/"+selected_cluster+".html");
			
			let image_pca = document.getElementById("pca_image_clustbydec");
			
				image_pca.setAttribute("src", "{{ site.github.url }}/assets/data/decade/"+selected_decade+"/PCAA_"+selected_cluster+".png");
			
			
			var i = 1980;
			while (i<2020){
				document.getElementById("image_cluster_"+i).setAttribute("src", "{{ site.github.url }}/assets/data/decade/"+i+"/"+selected_cluster+".png");
				document.getElementById("map_cluster_"+i).setAttribute("href", "{{ site.github.url }}/assets/data/decade/"+i+"/"+selected_cluster+".html");;
				document.getElementById("pca_image_"+i).setAttribute("src", "{{ site.github.url }}/assets/data/decade/"+i+"/PCAA_"+selected_cluster+".png");;
				i = i + 10 ;
			}
			
		};
		
		
		
		function display_pca_clustbydec() {
		let button = document.getElementById("pca_button_clustbydec");
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
		
		
		function display_mult_clustbydec() {
		let button = document.getElementById("mult_button_clustbydec");
		let all_year = document.getElementById("all_year_clustbydec");
		let one_year = document.getElementById("one_year_clustbydec");
		
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
		
		
	


	</script>
</figure>
analyse results

discuss results

## Conclusion 

