For this project I wanted to find out what possibilities there are for seeing how quick I can reach something from a certain location. 
## Path between points
First step was to write something to see if I could visualize a simple route between some points, based on the order given and the coordinates of the points. I wanted to use OSM as a map provider and as a router Graphhopper, since OSM is open source and Graphhopper since it provides enough free requests for my needs. To keep the routing simple for now, I will only consider cars in this phase, and no traffic. 
```python
client = Graphhopper(api_key=api_key)
route = client.directions(locations=coords, profile='car')
```
To generate the map I will use folium, since it provides a nice format and plenty of render possibilities like a zoomable html. A challenge I encountered in this phase is that the coordinates as I put them into the Graphhopper API and the plot in folium are reversed. That means that in one of them the coordinates of Berlin are `[13.413706, 52.490202]` and in the other are `[52.490202, 13.413706]`. To accommodate this difference I made a simple function to reverse them. 

<html>
<head>
    
    <meta http-equiv="content-type" content="text/html; charset=UTF-8" />
    
        <script>
            L_NO_TOUCH = false;
            L_DISABLE_3D = false;
        </script>
    
    <style>html, body {width: 100%;height: 100%;margin: 0;padding: 0;}</style>
    <style>#map {position:absolute;top:0;bottom:0;right:0;left:0;}</style>
    <script src="https://cdn.jsdelivr.net/npm/leaflet@1.9.3/dist/leaflet.js"></script>
    <script src="https://code.jquery.com/jquery-3.7.1.min.js"></script>
    <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.2.2/dist/js/bootstrap.bundle.min.js"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/Leaflet.awesome-markers/2.0.2/leaflet.awesome-markers.js"></script>
    <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/leaflet@1.9.3/dist/leaflet.css"/>
    <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/bootstrap@5.2.2/dist/css/bootstrap.min.css"/>
    <link rel="stylesheet" href="https://netdna.bootstrapcdn.com/bootstrap/3.0.0/css/bootstrap.min.css"/>
    <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/@fortawesome/fontawesome-free@6.2.0/css/all.min.css"/>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/Leaflet.awesome-markers/2.0.2/leaflet.awesome-markers.css"/>
    <link rel="stylesheet" href="https://cdn.jsdelivr.net/gh/python-visualization/folium/folium/templates/leaflet.awesome.rotate.min.css"/>
    
            <meta name="viewport" content="width=device-width,
                initial-scale=1.0, maximum-scale=1.0, user-scalable=no" />
            <style>
                #map_b5e7c083ba36358cf126303ebf087bc8 {
                    position: relative;
                    width: 100.0%;
                    height: 100.0%;
                    left: 0.0%;
                    top: 0.0%;
                }
                .leaflet-container { font-size: 1rem; }
            </style>
        
</head>
<body>
    
    
            <div class="folium-map" id="map_b5e7c083ba36358cf126303ebf087bc8" ></div>
        
</body>
<script>
    
    
            var map_b5e7c083ba36358cf126303ebf087bc8 = L.map(
                "map_b5e7c083ba36358cf126303ebf087bc8",
                {
                    center: [52.490202, 13.413706],
                    crs: L.CRS.EPSG3857,
                    zoom: 11,
                    zoomControl: true,
                    preferCanvas: false,
                }
            );

            

        
    
            var tile_layer_23bd6762a69ffeacba4beb882327cf60 = L.tileLayer(
                "https://tile.openstreetmap.org/{z}/{x}/{y}.png",
                {"attribution": "\u0026copy; \u003ca href=\"https://www.openstreetmap.org/copyright\"\u003eOpenStreetMap\u003c/a\u003e contributors", "detectRetina": false, "maxNativeZoom": 19, "maxZoom": 19, "minZoom": 0, "noWrap": false, "opacity": 1, "subdomains": "abc", "tms": false}
            );
        
    
            tile_layer_23bd6762a69ffeacba4beb882327cf60.addTo(map_b5e7c083ba36358cf126303ebf087bc8);
        
    
            var marker_bf697ce4d752fdd1b3132ccf84f9a9f4 = L.marker(
                [52.490202, 13.413706],
                {}
            ).addTo(map_b5e7c083ba36358cf126303ebf087bc8);
        
    
            var icon_230996869f1604f918ce8b029e49b0db = L.AwesomeMarkers.icon(
                {"extraClasses": "fa-rotate-0", "icon": "info-sign", "iconColor": "white", "markerColor": "green", "prefix": "glyphicon"}
            );
            marker_bf697ce4d752fdd1b3132ccf84f9a9f4.setIcon(icon_230996869f1604f918ce8b029e49b0db);
        
    
            marker_bf697ce4d752fdd1b3132ccf84f9a9f4.bindTooltip(
                `<div>
                     Click me!
                 </div>`,
                {"sticky": true}
            );
        
    
            var marker_c00454dd6661dc35f729645e0d6300b0 = L.marker(
                [52.514105, 13.421838],
                {}
            ).addTo(map_b5e7c083ba36358cf126303ebf087bc8);
        
    
            var icon_14828be3dfa8f2f1538f4fb997781325 = L.AwesomeMarkers.icon(
                {"extraClasses": "fa-rotate-0", "icon": "info-sign", "iconColor": "white", "markerColor": "green", "prefix": "glyphicon"}
            );
            marker_c00454dd6661dc35f729645e0d6300b0.setIcon(icon_14828be3dfa8f2f1538f4fb997781325);
        
    
            marker_c00454dd6661dc35f729645e0d6300b0.bindTooltip(
                `<div>
                     Click me!
                 </div>`,
                {"sticky": true}
            );
        
    
            var marker_cb952faae87eb04a82f02a664f64d5d6 = L.marker(
                [52.507987, 13.453649],
                {}
            ).addTo(map_b5e7c083ba36358cf126303ebf087bc8);
        
    
            var icon_4c247424b3c93f9f24130be0397ad42e = L.AwesomeMarkers.icon(
                {"extraClasses": "fa-rotate-0", "icon": "info-sign", "iconColor": "white", "markerColor": "green", "prefix": "glyphicon"}
            );
            marker_cb952faae87eb04a82f02a664f64d5d6.setIcon(icon_4c247424b3c93f9f24130be0397ad42e);
        
    
            marker_cb952faae87eb04a82f02a664f64d5d6.bindTooltip(
                `<div>
                     Click me!
                 </div>`,
                {"sticky": true}
            );
        
    
            var marker_4fe67cd955c359dba5e2e80b09f4d00a = L.marker(
                [52.543373, 13.401947],
                {}
            ).addTo(map_b5e7c083ba36358cf126303ebf087bc8);
        
    
            var icon_0ab77eff2e74e09163e11ef07739db9a = L.AwesomeMarkers.icon(
                {"extraClasses": "fa-rotate-0", "icon": "info-sign", "iconColor": "white", "markerColor": "green", "prefix": "glyphicon"}
            );
            marker_4fe67cd955c359dba5e2e80b09f4d00a.setIcon(icon_0ab77eff2e74e09163e11ef07739db9a);
        
    
            marker_4fe67cd955c359dba5e2e80b09f4d00a.bindTooltip(
                `<div>
                     Click me!
                 </div>`,
                {"sticky": true}
            );
        
    
            var poly_line_ebca777c937aa011f76d8e3ef0c1827c = L.polyline(
                [[52.49017, 13.41371], [52.49014, 13.41327], [52.49147, 13.41299], [52.49183, 13.41326], [52.49213, 13.41224], [52.49278, 13.40988], [52.49288, 13.40948], [52.49312, 13.40836], [52.49392, 13.40349], [52.49521, 13.40452], [52.49556, 13.40481], [52.496, 13.40516], [52.49606, 13.40519], [52.49613, 13.40521], [52.4962, 13.40519], [52.49634, 13.40512], [52.49637, 13.40506], [52.49644, 13.4051], [52.49681, 13.40538], [52.49694, 13.40551], [52.49791, 13.40627], [52.49894, 13.40702], [52.50052, 13.40824], [52.50175, 13.40922], [52.50272, 13.40996], [52.50343, 13.41055], [52.50341, 13.41067], [52.50341, 13.41083], [52.50344, 13.41097], [52.50349, 13.41105], [52.50353, 13.4111], [52.50359, 13.41112], [52.50365, 13.41112], [52.50372, 13.41109], [52.50379, 13.41102], [52.50405, 13.41104], [52.50728, 13.41358], [52.51072, 13.41625], [52.51101, 13.41645], [52.51299, 13.41747], [52.51342, 13.41765], [52.51368, 13.41774], [52.51452, 13.41793], [52.51531, 13.41813], [52.51543, 13.41817], [52.51538, 13.41837], [52.51523, 13.41886], [52.51421, 13.42185], [52.51412, 13.42178], [52.51401, 13.42167], [52.51384, 13.42217], [52.51403, 13.42235], [52.51369, 13.42334], [52.51351, 13.42386], [52.51343, 13.42403], [52.5131, 13.42463], [52.51226, 13.42584], [52.51218, 13.42597], [52.5117, 13.42688], [52.51116, 13.42792], [52.51081, 13.42866], [52.51047, 13.42944], [52.51019, 13.43011], [52.50878, 13.43391], [52.50846, 13.43463], [52.50826, 13.43501], [52.5081, 13.43526], [52.50801, 13.4354], [52.50748, 13.43608], [52.50701, 13.43666], [52.50673, 13.43705], [52.50607, 13.43793], [52.50592, 13.43815], [52.50548, 13.4389], [52.50532, 13.43926], [52.50469, 13.44082], [52.5043, 13.44184], [52.5036, 13.44388], [52.50346, 13.44422], [52.50335, 13.44452], [52.50297, 13.44567], [52.50269, 13.44659], [52.50264, 13.4468], [52.50284, 13.44705], [52.50294, 13.44714], [52.5051, 13.44882], [52.50519, 13.44886], [52.50534, 13.44887], [52.50543, 13.4489], [52.50729, 13.45005], [52.50739, 13.45014], [52.50758, 13.45037], [52.50774, 13.45052], [52.50809, 13.45075], [52.50856, 13.45102], [52.50808, 13.45369], [52.50799, 13.45364], [52.50808, 13.45369], [52.50856, 13.45102], [52.509, 13.45125], [52.50949, 13.45148], [52.50965, 13.45155], [52.50991, 13.45164], [52.51046, 13.45188], [52.51557, 13.45417], [52.51571, 13.4542], [52.51584, 13.4542], [52.51592, 13.45418], [52.5171, 13.45376], [52.51803, 13.45341], [52.51813, 13.45341], [52.51824, 13.45346], [52.51857, 13.4537], [52.51863, 13.45373], [52.51871, 13.45373], [52.51876, 13.45372], [52.5188, 13.45369], [52.51887, 13.45362], [52.51891, 13.45356], [52.51896, 13.45341], [52.51907, 13.45292], [52.51911, 13.45284], [52.51918, 13.45278], [52.52142, 13.45125], [52.52206, 13.45082], [52.52465, 13.44904], [52.52634, 13.44789], [52.52651, 13.44774], [52.52677, 13.44746], [52.53133, 13.44253], [52.53155, 13.4423], [52.53169, 13.44217], [52.53204, 13.44181], [52.53214, 13.44169], [52.53223, 13.44154], [52.53344, 13.43907], [52.53413, 13.43769], [52.53549, 13.43479], [52.53612, 13.4335], [52.53621, 13.4333], [52.53632, 13.433], [52.5369, 13.4313], [52.53853, 13.42655], [52.53923, 13.42447], [52.5393, 13.42414], [52.53955, 13.42252], [52.53964, 13.42196], [52.53971, 13.42145], [52.54051, 13.41641], [52.54077, 13.41467], [52.54078, 13.41453], [52.54079, 13.41438], [52.54079, 13.41394], [52.54098, 13.41271], [52.54102, 13.41232], [52.5411, 13.41197], [52.54117, 13.41114], [52.54114, 13.4109], [52.54134, 13.40853], [52.54134, 13.40832], [52.54133, 13.40822], [52.54195, 13.40791], [52.54222, 13.40785], [52.54238, 13.40778], [52.54253, 13.4077], [52.54264, 13.40756], [52.54283, 13.40736], [52.54306, 13.40723], [52.54384, 13.40683], [52.54413, 13.40675], [52.5441, 13.40655], [52.54415, 13.40626], [52.54424, 13.4057], [52.54425, 13.40538], [52.54424, 13.40519], [52.54423, 13.40501], [52.5442, 13.40483], [52.54416, 13.40465], [52.54407, 13.40445], [52.5439, 13.40419], [52.54359, 13.40381], [52.54352, 13.40376], [52.54348, 13.40375]],
                {"bubblingMouseEvents": true, "color": "#3388ff", "dashArray": null, "dashOffset": null, "fill": false, "fillColor": "#3388ff", "fillOpacity": 0.2, "fillRule": "evenodd", "lineCap": "round", "lineJoin": "round", "noClip": false, "opacity": 1.0, "smoothFactor": 1.0, "stroke": true, "weight": 3}
            ).addTo(map_b5e7c083ba36358cf126303ebf087bc8);
        
    
            poly_line_ebca777c937aa011f76d8e3ef0c1827c.bindTooltip(
                `<div>
                     Route
                 </div>`,
                {"sticky": true}
            );
        
</script>
</html>

Tree map of project this phase
``` 
├── README.md
├── apikey
├── index.html
├── requirements.txt
├── tests
│   ├── __init__.py
│   └── test_pathbetweenpoints.py
└── traveltimefromhome
    ├── __init__.py
    └── pathbetweenpoints.py
```

