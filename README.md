# L.TileLayer.Colorizr

A Leaflet TileLayer extension which will modify RGB codes in the tiles, based on a custom function.

Demos coming soon...

# Constructor and Options

Usage is almost exactly like a typical L.TileLayer, but you can pass a function (named colorize) to modify colors of each pixel individualy.

    var colorizd = L.tileLayer.colorizr('https://osm-mapbox-or-something/tiles/{z}/{x}/{y}.png', {
        colorize: function(pixel) {
        	// pixel is an object with red, green, blue and alpha channel like this {r, g, b, a}.
        	return { r: pixel.g, g: pixel.r };      // for example, to swap the red and green channel
        }
    })
