<!--
date: '2008-10-24'
published: true
slug: 2008-10-source-code-for-masaajid-map
time_to_read: 5
title: Source Code for masaajid map...
-->

Though I'd share the code for those interested in how I did the masaajid maps:  
> <gm:page title="Masaajid in South Africa" authenticate="false" onload="kmlPE()" gadget="true">  
> <!--  
> The mashup application demonstrates taking a Google Earth KML file and mapping it on a Google Map.  
> @author: GME Team & Valery Hronusov  
> -->  
> <h2>Masaajid in South Africa</h2>  
> <!-- Map definition -->  
> <gm:map id="map" height="600px" width="800px"  
> lat="-28.7500" lng="24.7700" zoom="5" maptypes="true"/>  
> <script>  
> function kmlPE()  
> {  
> var myMap = google.mashups.getObjectById('map').getMap();  
> var geoXml = new GGeoXml("http://yusufk.googlepages.com/masjids.kml");  
> myMap.setMapType(myMap.getMapTypes()[0]);  
> myMap.addOverlay(geoXml);  
> myMap.enableDoubleClickZoom();  
> }  
> </script>  
> </gm:page>

  
The above code can be easily pasted/ test using the [Google mashup editor](http://code.google.com/support/mashupeditorsignup).

[Original post](https://ysfk.blogspot.com/2008/10/source-code-for-masaajid-map.html)

#programming #howto #legacy-blogger 