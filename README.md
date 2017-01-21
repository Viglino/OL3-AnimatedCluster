# OL3-AnimatedCluster
A cluster layer for OpenLayers 3 (OL3)  that animates clusters on zoom change and a select interaction that spread out cluster to allow feature selection  in it.

Inspired by [acanimal/AnimatedCluster](https://github.com/acanimal/AnimatedCluster).

[View the live  example...](http://viglino.github.io/OL3-AnimatedCluster)

[<img src="https://github.com/Viglino/OL3-AnimatedCluster/raw/gh-pages/cluster_ani.gif" width="600px" />](http://viglino.github.io/OL3-AnimatedCluster)

If you like this, you may like [ol3-ext](http://viglino.github.io/ol3-ext/).

## How it runs?

`ol.layer.AnimatedCluster` is a layer that animates clusters on zoom change. The layer is created with an `ol.source.Cluster` as standard cluster vector layers.

`ol.interaction.SelectCluster` is a select interaction that handles clusters. On select cluster springs apart to reveal the features. The revealed features are themselves selectable. Revealed features are a cluster with an attribute `features` that contain the original feature so they can be use as a cluster. 

##Usage

Include the following files in your page:
```html
<script type="text/javascript" src="https://cdn.rawgit.com/Viglino/OL3-AnimatedCluster/gh-pages/interaction/selectclusterinteraction.js"></script>
<script type="text/javascript" src="https://cdn.rawgit.com/Viglino/OL3-AnimatedCluster/gh-pages/layer/animatedclusterlayer.js"></script>
```
Create a cluster layer to add to the map object:
```javascript
// Cluster Source
var clusterSource = new ol.source.Cluster({
     distance: 40,
     source: new ol.source.Vector()
	});
// Animated cluster layer
var clusterLayer = new ol.layer.AnimatedCluster(
	{	name: 'Cluster',
		source: clusterSource,
		// Use a style function for cluster symbolisation
		style: getStyle
	});
// Add the layer to the map
map.addLayer(clusterLayer);
```
The getStye function will customize the clusters symbolisation.

Look at the [standard OL3 cluster example](http://openlayers.org/en/master/examples/cluster.html) or [the repo example](http://viglino.github.io/OL3-AnimatedCluster) to know how to define such a function.


## Licence

OL3-ext is licenced under the **French Opensource BSD** compatible CeCILL-B FREE SOFTWARE LICENSE.  
 (c) 2016 - Jean-Marc Viglino

> Full text license in English: (http://www.cecill.info/licences/Licence_CeCILL-B_V1-en.txt)  
> Full text license in French: (http://www.cecill.info/licences/Licence_CeCILL-B_V1-fr.txt)
