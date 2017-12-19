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

Let us now look at our party data clusterized using K-means and DBSCAN. This time around, DBSCAN was able to give us more interesting results as the clusters are much more defined compared to the theme clustering. We are interested to see whether party allegiance is a defining factor of the _Röstigraben_ phenomenon.

<figure>
<div>
<input type="button" onclick="display_pca()" id="pca_button" value="Display PCA">
   <input type="button" onclick="display_comp()" id="comp_button" value="Display non cluster">

  </div>
  

</figure>

<figure>
<select onchange="theThingToDoIfItChange()" id="selection_party">
      <option value="AdI">Alliance des Indépendants (Left, Liberal)</option>
      <option value="DS">Démocrates Suisses (Conservative)</option>
      <option value="Lega">Lega dei Ticinesi (Conservative)</option>
      <option value="MCR">Mouvement Citoyens Romand (Right, Conservative)</option>
      <option value="Rep.">Mouvement Républicain (Right, Conservative) [DEFUNCT]</option>
      <option value="POCH">Organisations Progressistes de Suisse (Left, Liberal) [DEFUNCT]</option>
      <option value="PSL">Parti des Automobilistes (Right, Conservative)</option>
      <option value="PBD">Parti Bourgeois Démocratique (Center-Right, Liberal)</option>
      <option value="PCS">Parti Chrétien Social (Center-Left)</option>
      <option value="PDC">Parti Démocrate Chrétien (Center, Liberal)</option>
      <option value="PES">Parti Ecologiste (Left, Liberal)</option>
      <option value="PEV">Parti Evangélique (Center)</option>
      <option value="PLR">Parti Libéral-Radical (Center-Right, Liberal)</option>
      <option value="PLS">Parti Libéral (Center-Right, Liberal) [DEFUNCT]</option>
      <option value="PRD">Parti Radical-Démocratique (Center-Right, Liberal) [DEFUNCT]</option>
      <option value="PS">Parti Socialiste (Left, Liberal)</option>
      <option value="PST">Parti Suisse du Travail (Far Left)</option>
      <option value="UDC">Union Démocratique du Centre (Right, Conservative)</option>
      <option value="UDF">Union Démocratique Fédérale (Right, Conservative)</option>
      <option value="PVL">Verts Libéraux (Center, Liberal)</option>
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
<a href="{{ site.github.url }}/assets/data/map_recommendation_cluster/kmeans_AdI.html" id="map_cluster"> see the full html here</a>

<div style="display: none;" id="pca_div">
<img src="{{ site.github.url }}/assets/data/map_recommendation_cluster/AdIPCAA_kmeans2.png" id="pca_image">
</div>

	
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
			
			document.getElementById("text").innerHTML = dict[selected_party];
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
		
	</script>
</figure>

### Analysis & Discussion

An interesting feature in the PCAs is that almost all parties have two clear elongated clusters that display a very clear occurence of the _Röstigraben_. We were not expecting to see that clear of a cut. We can see that there seems to be a big relation between what parties recommend to vote and what different regions will vote. The parties that do not feature clear clusters are mostly either very small or very new, which leads us to think that these two big clusters would eventually appear for any party of a certain size and age. We can even see how closely related the PLS and PRD were before their fusion, as their clusters are almost identical.

