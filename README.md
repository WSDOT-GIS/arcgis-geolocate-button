Geolocate Button for ArcGIS JavaScript API
==========================================

Creates a Geolocate Button. When the user clicks the button, a popup will appear in the user's current location.

## Features ##

* Displays accuracy in meters or km.

## Instructions ##

Follow the instructions below to use the Geolocate Button in your projects

1. Add [Bower] module to your project by running the following command from the commandline while the current directory is the directory containing your project.

        $ bower install arcgis-geolocate-button
    This will install the necessary components into the `bower_components` folder of your project.

2. Add CSS to HTML head.

    ```html
    <head>
        <link href="//js.arcgis.com/3.14/esri/css/esri.css" rel="stylesheet" />
        <link href="bower_components/arcgis-geolocate-button/GeolocateButton.css" rel="stylesheet" />
    </head>
    ```

3. Add package to dojoConfig.

    ```html
    <body>
    <!-- ... -->
        <script>
           (function () {
                var root = location.pathname.replace(/\/[^\/]*$/, "");
                var dojoConfig = {
                    async: true,
                    packages: [{
                        name: "GeolocateButton",
                        location: root + "/bower_components/arcgis-geolocate-button",
                        main: "GeolocateButton"
                    }]
                };
                window.dojoConfig = dojoConfig;
            }());
        </script>
        <script src="//js.arcgis.com/3.14/"></script>
    </body>
    ```

4. Add button element inside of map DOM node.

    ```html
    <body>
        <div id="map">
            <div id="locationButtons">
                <button type="button" title="Geolocate" class="geolocate" id="geolocateButton"></button>
            </div>
        </div>
    <!-- ... -->
    </body>
    ```

2. Call function to convert DOM node into Geolocate Button.

    ```javascript
    require(["esri/map", "GeolocateButton"], function(Map, createGeolocateButton) {
      var map;

      map = new Map("map", {
        basemap: "hybrid",
        center: [-120.80566406246835, 47.41322033015946],
        zoom: 7,
        showAttribution: true
      });
  
      createGeolocateButton(document.getElementById("geolocateButton"), map);
    });
    ```

[Bower]:http://bower.io