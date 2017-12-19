---
layout: post
title: "Data clustering by theme"
---



<head>
<style>
li {
    display: inline;
}
</style>
</head>

Now that we have implemented clustering, we can restrict the data by specific theme, and thus possibly observe division among themes. We will do this with both Kmeans and DBSCAN (which had a hard time giving us pertinent results here). Here we can compare the non-clustering solution with the clustering, and additionally we can look at the Principal Component Analysis (PCA) which gives valuable information as to why clusters look the way they do.

<figure>
<div>
<input type="button" onclick="display_pca()" id="pca_button" value="Display PCA">
   <input type="button" onclick="display_comp()" id="comp_button" value="Display non cluster">

  </div>
  

</figure>

<figure>
<select onchange="theThingToDoIfItChange()" id="selection_theme">
      <option value="Economy">Economy</option>
      <option value="Education,culture,media">Education, culture, media</option>
      <option value="Foreign policy">Foreign policy</option>
      <option value="Infrastructure, planning, environment">Infrastructure, planning, environment</option>
      <option value="Political regime">Political regime</option>
      <option value="public finances">Public finances</option>
      <option value="security policy">Security policy</option>
      <option value="social policies">Social policies</option>
</select>

<select onchange="theThingToDoIfItChange()" id="selection_cluster">
	  <option value="kmeans">kmeans</option>
	  <option value="DBSCAN">DBSCAN</option>
</select>

</figure>








<div style="display: none;" id="comp_div">
<img src="{{ site.github.url }}/assets/data/map_theme/Economy.png" id="image">
<a href="{{ site.github.url }}/assets/data/map_theme/Economy.html" id="map"> see the full html here</a>
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
			
			document.getElementById("text").innerHTML = dict[selected_theme];
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
      "Economy": "While DBSCAN fails to extract valuable info, we observe with Kmeans that there is a clear _Röstigraben_ when it comes to economical policies, although some regions like Central Switzerland are also part of the French-speaking cluster. The PCA here shows an interesting distribution that Kmeans didn't manage to split horizontally.",
      "Education,culture,media": "We observe a much clearer divide here, with Western and Southern Switzerland quite in accordance on the subject. The PCA shows us however that the two groups are still clogged together.",
      "Foreign policy": "One long cluster here split by the middle, we notice that _Röstigraben_ again here for foreign policy.",
      "Infrastructure, planning, environment": "We see two clean clusters here that Kmeans successfully detected. We think this clear divide on infrastructure votations has to do with environmental issues.",
      "Political regime": "A less clear _Röstigraben_ here on political regime. Our PCA shows that the divide is less evident. This is indeed not the most divisive issue in Switzerland.",
      "public finances": "Again, quite a consensus on the subject of finances.",
      "security policy": "The cluster is a bit wider this time, with Western Switzerland and Ticino are a bit more divided from the rest than for other issues.",
      "social policies": "As we would expect, social policies are a more debatable subject, with two quite distinct clusters in the PCA, and very clean _Röstigraben_ and _Polentagraben_.",
      };


		document.getElementById("text").innerHTML = dict ["Economy"];
		
	</script>
</figure>

### Analysis & Discussion

The first thing we can notice is that some issues are more subjects of debate than others. The main suspects here are social policies, foreign policies and infrastucture/planning/environment, which us Swiss people can certify as being questions that divide people in our country. French-speaking Switzerland is known for being more open to questions like social assistance, the European Union and the environment. These clear cuts were expected and they reinforce the idea of a _Röstigraben_ in this country in the last decades. We can however get a glimpse of a city/countryside divide, although it is quite overshadowed by the language divide when looking at older data.