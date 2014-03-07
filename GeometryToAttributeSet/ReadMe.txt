Deployment Configuration:

To configure this application, change the value of the four variables in the configuration section (lines 49-52)
Variables:
mapServiceURL - change this to the URL of the map service that you want to display in the map. The sample uses http://roadsandhighwayssample.esri.com/arcgis/rest/services/RoadsHighways/NewYorkRoads/MapServer.
visibleLayers - This is an array of layers in the map service to make visible. In the sample, only layer with id 3 is visible.
networkLayerURL - This is the url of your LRS network. Make sure your URL does not end with a slash. The sample uses http://roadsandhighwayssample.esri.com/arcgis/rest/services/RoadsHighways/NewYorkRoads/MapServer/exts/LRSServer/networkLayers/16
attributeSet - These are the attributes that you are going to query from the event layers. It is an array of objects with the properties layerId and fields. For complete documentation on this argument see the REST documentation for Query Attribute set here: http://roadsandhighwayssample.esri.com/roads/api/index.html. 
The sample uses [{ "layerId": 3, "fields": ["functional_class"] }, { "layerId": 5, "fields": ["median_type"] }, { "layerId": 6, "fields": ["median_width"] }, { "layerId": 12, "fields": ["through_lane"] }, { "layerId": 11, "fields": ["terrain_type"] }, { "layerId": 10, "fields": ["speed_limit"] }, { "layerId": 7, "fields": ["pvt_type", "pvt_width", "total_lane", "iri"] }];

Ensure the web server is CORS-enabled. [http://enable-cors.org/]
Change the corsEnabledServers property to the web server hostname. It is now pointing to http://roadsandhighwayssample.esri.com

Setup a proxy script on the web server. [https://developers.arcgis.com/javascript/jshelp/ags_proxy.html]
Change the proxy URL to point to the web server's proxy script. It is currently pointing to "/proxy/proxy.ashx"
