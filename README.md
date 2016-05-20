# Ractive Mapbox GL popup
A [Mapbox GL](https://www.mapbox.com/mapbox-gl-js/api/) popup component for [Ractive](https://github.com/ractivejs/ractive)

[Demo on GitHub pages](http://aesqe.github.io/ractive-mapboxgl-popup/) (uses [Ractive.load](https://github.com/ractivejs/ractive-load) to fetch component data).

--

**Example use in your template:**

```html
<mapboxglPopup marker="{{marker}}" map="{{map}}" popupContent="{{marker.properties.description}}" partialName="popupTemplate" />
```

where `marker` is a Mapbox GL marker, `map` is the Mapbox GL map (object) containing the marker, and `popupContent` is the object referenced in the partial named (`partialName`) "popupTemplate".

Here's an example of a marker:

```javascript
{
	"type": "Feature",
	"properties": {
		"marker-symbol": "theatre",
		"description": "I'm a theatre"
	},
	"geometry": {
		"type": "Point",
		"coordinates": [-77.003168, 38.894651]
	}
}
```

and here of a partial:

```html
{{#partial popupTemplate}}
	<div class="marker-description">
		{{popupContent}}
	</div>
{{/partial}}
```

Just look at the [demo source code](https://github.com/aesqe/ractive-mapboxgl-popup/blob/master/index.html) and it'll all make sense.
