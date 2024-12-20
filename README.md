<!DOCTYPE html>
<html>

<head>
	<meta charset=utf-8 />
	<title>route map</title>
	<meta name='viewport' content='initial-scale=1,maximum-scale=1,user-scalable=no' />

	<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/normalize/5.0.0/normalize.css" />
	<link rel="stylesheet" href="https://unpkg.com/leaflet@1.0.1/dist/leaflet.css" />
	<link href="https://fonts.googleapis.com/css?family=Noto+Sans" rel="stylesheet">
	<link href="https://fonts.googleapis.com/css?family=Lora" rel="stylesheet">

	<style>
		body {
			margin: 0;
			padding: 0; 
			font-family: "Open Sans", sans-serif;
			color: #796f6f;
		}

		h1 {
			position: absolute;
			margin-top: 0;
			top: 10px;
			left: 45px;
			font-size: 2em;
			font-family: "Geneva", sans-serif;
			letter-spacing: .04em;
			padding: 10px 15px;
			background: rgba(256, 256, 256);
			border: 1px solid grey;
			border-radius: 3px;
			z-index: 800;
		}

		h2 {
			font-family: "American Typewriter", serif;
			letter-spacing: .04em;
		}

		#map {
			position: absolute;
			top: 0;
			bottom: 0;
			width: 100%;
		}

		section {
			position: absolute;
			bottom: 0;
			left: 10px;
			width: 280px;
			margin: 20px auto;
			padding: 0 15px;
			background: rgba(256, 256, 256);
			border: 1px solid grey;
			border-radius: 3px;
			z-index: 800;
		}

		p {
			font-size: .9em;
			line-height: 1.5em;
		}

		a {
			color: #669ac4;
			text-decoration: none;
		}

		a:hover {
			text-decoration: underline;
		}
	</style>
</head>

<body>

	<h1>APPALACHIAN STATE UNIVERSITY TO MAMA NICK'S </h1>

	<div id='map'></div>

	<section>
		<h2>ABOUT THIS MAP</h2>
            <p> This route depicts a critical pathway to home and solace that includes food, family, and friends. That being one of the best custom donut shops ever concieved; Duck Donuts. 
				It includes delicacies such as maple bacon, cookies and cream and any other flavor you can imagine that brings joy. After the obligarory donuts I visit my girlfriend and her family and welcome them with gifts. 
				After devouring some donuts and a coffee refill, my final destination is to go back home. Almost, because adjacent to my neighborhood is one of the oldest pubs in Raleigh where
				I had my first beer; O'Malley's Pub. I usually meet my mother there and we talk and catch up before we head back to the homestead for the day.  <menu></menu> </p>

    </section>  

    <script src="http://code.jquery.com/jquery-3.1.1.min.js"></script>
	<script src="https://unpkg.com/leaflet@1.0.1/dist/leaflet.js"></script>
    
    <script src="data/route.js"></script> 
   
   <script> 
   
//options to be used when creating the map
		var options = {
			center: [36.173849891280575, -80.05141310606683],
			zoom: 16
		}
        console.log(data);
//creation of the Leaflet map
		var map = L.map('map', options);

//request to load basemap
var CartoDB_VoyagerLabelsUnder = L.tileLayer('https://{s}.basemaps.cartocdn.com/rastertiles/voyager_labels_under/{z}/{x}/{y}{r}.png', {
	attribution: '&copy; <a href="https://www.openstreetmap.org/copyright">OpenStreetMap</a> contributors &copy; <a href="https://carto.com/attributions">CARTO</a>',
	subdomains: 'abcd',
	maxZoom: 20
}).addTo(map);

//string content to be inserted into a tooltip
		//var message = 'Beacon Heights!';

//create a Leaflet marker, centered on the map's center.
		//L.marker(map.getCenter())
		//	.bindTooltip(message) //bind the tooltip and message to the marker
		//	.addTo(map) // add the marker to the map`
		//	.openTooltip(); // open the tooltip

        var myRoute = L.geoJson(data, {
         filter : function(feature) {
            if(feature.geometry.type =="LineString") {
             return feature;
            }
        },
            style : function(feature) {
                return {
                    color: "#6a329f",
                    weight: 6,
                    opacity: 0.9,
                    dashArray: "1, 1"
                }
            }
            }).addTo(map);

            var myStops = L.geoJson(data, {
                filter : function(feature) {
                    if(feature.geometry.type == "Point") {
                        return feature;
                 }
                },
                onEachFeature : function(feature, layer) {
                    layer.bindTooltip(feature.properties['name']);
                }
                }).addTo(map);
        map.fitBounds(myRoute.getBounds());
	
    
    
        </script>


</body>




</html>  

		

