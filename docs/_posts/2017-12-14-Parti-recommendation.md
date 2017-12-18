---
layout: post
title: "Party Recommendations"
---

Another meaningful information we have is the recommendations of parties for each votation. An interesting thing we can extract from that is popular agreement with party policies. For that we generate one map for each party, showing the percentage of votations where each community voted along with a given party's recommendation.

<figure>
<select onchange="theThingToDoIfItChange()" id="selection">
      <option value="map_AdI">Alliance des Indépendants (Left, Liberal)</option>
      <option value="map_DS">Démocrates Suisses (Conservative)</option>
      <option value="map_Lega">Lega dei Ticinesi (Conservative)</option>
      <option value="map_MCR">Mouvement Citoyens Romand (Right, Conservative)</option>
      <option value="map_Rep.">Mouvement Républicain (Right, Conservative) [DEFUNCT]</option>
      <option value="map_POCH">Organisations Progressistes de Suisse (Left, Liberal) [DEFUNCT]</option>
      <option value="map_PSL">Parti des Automobilistes (Right, Conservative)</option>
      <option value="map_PBD">Parti Bourgeois Démocratique (Center-Right, Liberal)</option>
      <option value="map_PCS">Parti Chrétien Social (Center-Left)</option>
      <option value="map_PDC">Parti Démocrate Chrétien (Center, Liberal)</option>
      <option value="map_PES">Parti Ecologiste (Left, Liberal)</option>
      <option value="map_PEV">Parti Evangélique (Center)</option>
      <option value="map_PLR">Parti Libéral-Radical (Center-Right, Liberal)</option>
      <option value="map_PLS">Parti Libéral (Center-Right, Liberal) [DEFUNCT]</option>
      <option value="map_PRD">Parti Radical-Démocratique (Center-Right, Liberal) [DEFUNCT]</option>
      <option value="map_PS">Parti Socialiste (Left, Liberal)</option>
      <option value="map_PST">Parti Suisse du Travail (Far Left)</option>
      <option value="map_UDC">Union Démocratique du Centre (Right, Conservative)</option>
      <option value="map_UDF">Union Démocratique Fédérale (Right, Conservative)</option>
      <option value="map_PVL">Verts Libéraux (Center, Liberal)</option>
</select>
</figure>

<img src="{{ site.github.url }}/assets/data/maps_partis/map_AdI.png" id="image">
<a href="{{ site.github.url }}/assets/data/maps_partis/map_AdI.html" id="map"> See the full html here
<h3>What this map tells us</h3>
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
      "map_AdI": "This party is relatively on par with urban voters (Geneva, Bern, Zürich, Basel).",
      "map_DS": "This party is clearly unpopular among French speakers. We notice a clear divide at the language border. It seems to have its roots in traditional rural areas.",
      "map_Lega": "This party is solely based in Ticino, and even there it is not the law of the land. It is not very popular in the country and most communities that agree with it are in rural areas.",
      "map_MCR": "While not the most popular, it has a rather homogeneous correlation with voting results on the whole country. There are no real hubs of support though.",
      "map_PBD": "This party enjoys minor peaks of support in urban regions, especially around Lake Geneva, with clear lack of support in traditional rural areas.",
      "map_PCS": "This party is much more popular in French speaking Switzerland, with a clear divide on the language boundary. Its popularity is quite homogeneous there, while in the rest of the country the re are no big hibs of support.",
      "map_PDC": "We notice clear peaks of support in urban regions and more generally in the Swiss Plateau, along with some in low populated regions of the Alps.",
      "map_PES": "Very popular in the French and Italian parts, with a clear peak in Zürich. Low support in the rest of Switzerland.",
      "map_PEV": "Although there are no big zones of low correlation with voting results, this party clearly draws more support in urban regions.",
      "map_PLR": "This party's popularity is higher in the French part, especially around lake Geneva. Otherwise most of the rest of the country has about 50% voting agreement.",
      "map_PLS": "Similar to the PLR, its successor, shit party is more popular in urban regions, although more homogeneously with the German part.",
      "map_POCH": "Quite low support except for the cantons of Ticino and Jura and a bit of Zürich, where it lies around 60% of agreement while the rest is at 40% and lower.",
      "map_PRD": "This party enjoys strong support in urban regions of the Plateau, with support dropping to 50% in the Alps and Jura mountains.",
      "map_PS": "For this party we see a clear disagreement between the German speaking regions, where support is low, and the others.",
      "map_PSL": "This party enjoys support mainly from German speaking regions, with high peaks in traditional Switzerland. Support in the other regions is about 50%.",
      "map_PST": "Very low support everywhere except French and Italian regions, where it is above 60% in a few areas.",
      "map_PVL": "Surprising case here, where support is around 55% all over the country, except for one community where agreement tops above 80%.",
      "map_Rep.": "Agreement with thie party is widely distributed, with peaks below 40% in Ticino and Jura and peaks above 70% in rural areas.",
      "map_UDC": "Support of this party is especially strong in the whole German speaking part of the country, with a clear difference in French speaking regions. Support is especially high in central Switzerland.",
      "map_UDF": "We see the same peaks in central Switzerland as UDC, but with most other regions relatively lower that with said party.",
      };

		document.getElementById("text").innerHTML = dict ["map_AdI"];
		
	</script>
</figure>

## Analysis

From these results we can notice tendancies that can be confirmed by many of us: parties with more liberal and progressive policies tend to be more supported in urban regions and in the French and Italian speaking regions, while the opposite is true for more conservative parties.

It has to be noticed that there are no "super-winners" or "super-losers" among parties, by that we mean that no party's policies are almost 100% correlated with votation outcomes, regardless of the party or the region. We do notice clear peaks of various shapes for some, but overall this shows that Switzerland's political landscape is wide and diverse. The most flagrant division is along the so-called "Röstigraben" and "Polentagraben" for some smaller parties, but bigger parties like UDC, PS, PLR or PDC, although we do see a divide, are not really the subjects of biggest divisions we noticed here.

## Conclusion 

