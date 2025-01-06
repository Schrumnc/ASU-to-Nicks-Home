# Route Map Project

## Overview

This project visualizes a route on a map using Leaflet.js. The route includes various stops and is displayed with custom styles and tooltips.

## Files

- `index.html`: The main HTML file that sets up and displays the map.
- `data/route.js`: Contains the GeoJSON data for the route and stops.

## Dependencies

- [Normalize.css](https://cdnjs.cloudflare.com/ajax/libs/normalize/5.0.0/normalize.css): A CSS reset library.
- [Leaflet.js](https://unpkg.com/leaflet@1.0.1/dist/leaflet.js): A JavaScript library for interactive maps.
- [jQuery](http://code.jquery.com/jquery-3.1.1.min.js): A fast, small, and feature-rich JavaScript library.

## Usage

1. Open `index.html` in a web browser.
2. The map will be centered at the specified coordinates with a zoom level of 16.
3. The base map tiles are loaded from CartoDB.
4. The route and stops are loaded from `data/route.js` and displayed on the map.
5. The route is styled with a purple line, and stops are marked with tooltips displaying their names.

## Code Explanation

### HTML Structure

- The `<head>` section includes meta tags, external CSS, and internal styles.
- The `<body>` section contains a title, a map container (`#map`), and a section with information about the map.

### JavaScript

- The map is created using Leaflet.js with specified options (center and zoom level).
- Base map tiles are loaded from CartoDB.
- GeoJSON data from `data/route.js` is used to create the route and stops on the map.
- The route is styled with a custom color, weight, opacity, and dash pattern.
- Stops are marked with tooltips displaying their names.
- The map view is adjusted to fit the bounds of the route.

## License

This project is licensed under the MIT License.
