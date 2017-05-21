# L.TileLayer.PixelFilter

A Leaflet TileLayer extension which will modify RGB codes in the tiles, based on a custom function.

Demos coming soon...

# Constructor and Options

Usage is almost exactly like a typical L.TileLayer, except for a few additional options.

    // after tiles load, any pure red (255,0,0) tiles will be replaced with black
    // any other colors will be filled with white at 1/4 opacity
    var colorizd = L.tileLayer.colorizr('https://osm-mapbox-or-something/tiles/{z}/{x}/{y}.png', {
        colorize: function(pixel) {
        	// pixel is an object with red, green, blue and alpha channel
        	// like this {r, g, b, a}
        	// swap red and green channel
        	return { r: pixel.g, g: pixel.r };
        }
    }).addTo(MAP);