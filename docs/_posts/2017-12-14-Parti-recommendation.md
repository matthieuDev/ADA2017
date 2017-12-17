---
layout: post
title: "Parti recommendation"
---





### Introduction

Introduction 


### Presentation map theme

Intro
<figure>
<select onchange="theThingToDoIfItChange()" id="selection">
      <option value="map_AdI">map_AdI</option>
      <option value="map_DS">map_DS</option>
      <option value="map_Lega">map_Lega</option>
      <option value="map_MCR">map_MCR</option>
      <option value="map_PBD">map_PBD</option>
      <option value="map_PCS">map_PCS</option>
      <option value="map_PDC">map_PDC</option>
      <option value="map_PES">map_PES</option>
      <option value="map_PEV">map_PEV</option>
      <option value="map_PLR">map_PLR</option>
      <option value="map_PLS">map_PLS</option>
      <option value="map_POCH">map_POCH</option>
      <option value="map_PRD">map_PRD</option>
      <option value="map_PS">map_PS</option>
      <option value="map_PSL">map_PSL</option>
      <option value="map_PST">map_PST</option>
      <option value="map_PVL">map_PVL</option>
      <option value="map_Rep.">map_Rep.</option>
      <option value="map_UDC">map_UDC</option>
      <option value="map_UDF">map_UDF</option>
</select>
</figure>

<img src="{{ site.github.url }}/assets/data/maps_partis/map_AdI.png" id="image">
<a href="{{ site.github.url }}/assets/data/maps_partis/map_AdI.html" id="map"> see the full html here
<p id="text">Hello World!</p>

	
<figure>
	<script type="text/javascript">
		function theThingToDoIfItChange(){
			
			let image = document.getElementById("image");
			let map = document.getElementById("map");
			
			let selected = document.getElementById("selection").value;
			
			image.setAttribute("src","{{ site.github.url }}/assets/data/maps_partis/"+selected+".png");
			map.setAttribute("href","{{ site.github.url }}/assets/data/maps_partis/"+selected+".html");
			document.getElementById("text").innerHTML = dict[selected];
		};
		var dict = {
      "map_AdI": "describe map_AdI",
      "map_DS": "describe map_DS",
      "map_Lega": "describe map_Lega",
      "map_MCR": "describe map_MCR",
      "map_PBD": "describe map_PBD",
      "map_PCS": "describe map_PCS",
      "map_PDC": "describe map_PDC",
      "map_PES": "describe map_PES",
      "map_PEV": "describe map_PEV",
      "map_PLR": "describe map_PLR",
      "map_PLS": "describe map_PLS",
      "map_POCH": "describe map_POCH",
      "map_PRD": "describe map_PRD",
      "map_PS": "describe map_PS",
      "map_PSL": "describe map_PSL",
      "map_PST": "describe map_PST",
      "map_PVL": "describe map_PVL",
      "map_Rep.": "describe map_Rep.",
      "map_UDC": "describe map_UDC",
      "map_UDF": "describe map_UDF",
      };

		document.getElementById("text").innerHTML = dict ["map_AdI"];
		
	</script>
</figure>
analyse results

discuss results

## Conclusion 

