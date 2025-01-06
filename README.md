Route Map Web Application
Overview
This project is a web-based route map application built using HTML, CSS, and the Leaflet.js library. It showcases a personal journey from Appalachian State University to various meaningful destinations, including Mama Nick's, Duck Donuts, and O'Malley's Pub.

The map highlights:

A custom route using GeoJSON data.
Stops with tooltips describing key points along the route.
Features
Interactive Map:

Powered by Leaflet.js with a CartoDB Voyager basemap.
GeoJSON data to plot a route and key points.
Custom Styling:

Custom styles for the map and UI, providing a clean and interactive user experience.
Unique route line styles (color, weight, and opacity) and tooltip popups.
Personal Narrative:

The project serves as a storytelling tool, with descriptions of the route and its significance.
How to Use
Prerequisites
A basic web server to serve static files (e.g., Live Server for Visual Studio Code).
Installation
Clone or download the repository to your local machine.
Ensure the following files are in the project directory:
index.html: The main HTML file.
data/route.js: A GeoJSON file containing route and point data.
Any required assets (e.g., CSS and JS libraries are loaded via CDNs).
Running the Project
Open index.html in your browser, or use a local web server to view the project.
Interact with the map:
View the plotted route and its stops.
Hover over points to see tooltips with more information.
File Structure
bash
Copy code
.
├── index.html             # Main HTML file for the application
├── data/
│   └── route.js           # GeoJSON data for the route and stops
├── README.md              # Documentation file (this file)
Technologies Used
HTML/CSS: For structure and styling.
Leaflet.js: Interactive map visualization.
CartoDB Basemaps: High-quality basemap tiles.
GeoJSON: Data format for representing the route and stops.
Customization
Map Initialization
To modify the initial view of the map, adjust the options object:

javascript
Copy code
var options = {
    center: [36.173849891280575, -80.05141310606683], // Latitude and Longitude
    zoom: 16 // Zoom level
};
Route and Stops
Update data/route.js to customize the GeoJSON data for new routes or stops.
Modify the style function in the JavaScript code to change the appearance of the route.
Tooltips
Customize the tooltip content by modifying the feature.properties['name'] field in the GeoJSON data.

License
This project is open-source and available under the MIT License.

