# [GPS Meterology](https://hodatahami.github.io/stormstorymap/)


**Story map**| **May 22, 2018** | **GPS Meterology** | **Contributors:** 
[Hoda Tahami](https://github.com/HodaTahami/)

![](img/1.PNG)




The accurate prediction of the path and intensity of a hurricane is crucial for planning the evacuation of the
                    populated areas and for assessing its impact. Since the evolution of severe weather phenomena is associated
                    with notable transient changes in water contents in the low atmosphere, the accurate monitoring of atmosphere
                    water vapor or <i>perceptible water vapor (PWV) </i>spatial-temporal variations is critical to forecast and localize
                    severe storms. On the other hand, the dynamic perturbations in the atmosphere water content can be measured
                    from the tropospheric delay of GNSS signal propagated from a satellite to a receiver on the ground. By observing
                    PWV spatial-temporal variations during a hurricane event, the nature of PWV of this type of event can be
                    characterized.

  

 ### Set up the workspace
 The basic folder structure to generate a story map should be as follows:
   ```powershell
   lab5
       │index.html
       │readme.md
       ├─css
       ├─js
       ├─img       
       ├─assets
      
            
          
   ```

### Required Libraries
In header we add the required css and javascript libraries

```powershell
        <title>GPS Meterology storymap</title>
        <meta charset="utf-8">
        <meta name="viewport" content="width=device-width, initial-scale=1">
    
        <!--meta data for sharing links on Facebook-->
        <meta property="og:title" content="GPS METEROLOGICAL MAP"/>
        <meta property="og:description" content="This is an example of a storymap."/>
        <meta property="og:image" content="assets/hurricane2.jpg"/>
    
        <!--add required stylesheets-->
        <link rel="stylesheet" href="https://unpkg.com/leaflet@1.2.0/dist/leaflet.css" />
        <link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.7/css/bootstrap.min.css">
        <link rel="stylesheet" href="https://unpkg.com/leaflet@1.2.0/dist/leaflet.css">
        <link rel="stylesheet" href="https://cesiumjs.org/releases/1.31/Build/Cesium/Widgets/widgets.css">
        <link href="https://fonts.googleapis.com/css?family=Lobster|Open+Sans" rel="stylesheet">
        <link rel="stylesheet" href="css/style.css">
    
        <!--add favicon for the web page-->
        <link rel="shortcut icon" href="img/GNSS.ico" type="image/x-icon">
    
        <!--facebook and info icons-->
        <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/4.7.0/css/font-awesome.min.css">
    
        <!--animation-->
        <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/animate.css/3.5.2/animate.min.css">
    
        <!--Font-->
        <link href="https://fonts.googleapis.com/css?family=Cairo" rel="stylesheet">
    
        <link rel="stylesheet" type="text/css" href="css/storymap.2.3.css">
        <!--add required libraries-->
        <script src="https://unpkg.com/leaflet@1.2.0/dist/leaflet.js"></script>
        <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.1.1/jquery.min.js"></script>
        <script src="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.7/js/bootstrap.min.js"></script>
        <script src="https://cdnjs.cloudflare.com/ajax/libs/leaflet-ajax/2.1.0/leaflet.ajax.min.js"></script>
        <script src="https://cesiumjs.org/releases/1.31/Build/Cesium/Cesium.js"></script>
    
        <!--mini globle map-->
        <script src="https://cdnjs.cloudflare.com/ajax/libs/d3/3.5.5/d3.min.js"></script>
        <script src="https://cdnjs.cloudflare.com/ajax/libs/topojson/1.6.19/topojson.min.js"></script>
        <script src="js/globeminimap.js"></script>
    
        <!--story map plugin-->
        <script src="js/storymap.2.3.js"></script>
   ```

###  The storyline
We use 5 different sections

##### section 1: overview

In this section we use a video (09sept_Irma_g16geocolor)
 ``` html
  <section data-scene="overview" data-background="assets/09sept_Irma_g16geocolor.mp4">
                  <div class="fullscreen text-center">
                      <h1 style="color: rgb(254,196,79)"> <b>GPS Meteorology</b></h1>
                      <h1>
                          <small style="color: rgb(255,247,188)"> This story map illustrates the GPS meteorology for
                              monitoring of Hurricane Matthew 2016.
                          </small>
                      </h1>
                      <br/><br/><br/><br/><br/><br/><br/><br/><br/><br/><br/><br/><br/>
                      <div class="credit">
                          <p><img style="width:140px;" align="right" src="img/osu.png"></p> <br/><br/><br/>
                          <p style="color: rgb(255,247,188)" align="right"> Created by Hoda Tahami From Oregon State University,2018 </p>
                      </div>
                 </div>
                  <br/><br/><br/>
  
              </section>
  ```
 
 
##### section 2: GPSMap

In this section we talk about problem 
 ![](img/2.PNG)
 

 
 ```
<section data-scene="GPSMap">
                <h2 style="color: #045a8d" align="left" ><b>GPS meteorology </b></h2>
                <p align="justify">
                    The accurate prediction of the path and intensity of a hurricane is crucial for planning the evacuation of the
                    populated areas and for assessing its impact. Since the evolution of severe weather phenomena is associated
                    with notable transient changes in water contents in the low atmosphere, the accurate monitoring of atmosphere
                    water vapor or <i>perceptible water vapor (PWV) </i>spatial-temporal variations is critical to forecast and localize
                    severe storms. On the other hand, the dynamic perturbations in the atmosphere water content can be measured
                    from the tropospheric delay of GNSS signal propagated from a satellite to a receiver on the ground. By observing
                    PWV spatial-temporal variations during a hurricane event, the nature of PWV of this type of event can be
                    characterized.</p>
                <p align="justify">
                    This project will use data to produce a geovisualization, predicting hurricane path in US east coast states
                    (Florida, Georgia, North and South Carolina). The path forecasting is based on the 24 hour GNSS observations
                    of stations located at east coast area. As a case study, we adopted one of the most recent destructive and
                    long-lived hurricane along the Florida, Georgia, and South-Carolina coast, namely, <i><b>Hurricane Matthew</b></i>, occurred
                    in October 2016.
                    To investigate the potential of GNSS data for retrieving the perturbation of GNSS derived PWV,
                    seven days (5 October-11 October) observations of <a href="https://www.ngs.noaa.gov/CORS_Map/"><b>Continuously Operating Reference Stations (CORS) </b></a> were used to
                    track the hurricane trace .</p>
                <p align="justify">
                    The geovisualization will incorporate interactive elements, allowing the user to observe the fluctuation
                    of atmospheric parameters over time (seven days) and the predicted path of maximum rainfall in every one
                    hour prediction period. With forecasting the precipitation in each station, the path of maximum rainfall
                    movement can be displayed over the time. This geovisualization seeks to use certain indicators to show where
                    we can expect the maximum GNSS-derived precipitation as the atmospheric parameters (pressure, temperature,
                    relative humidity) fluctuate.  </p>
            </section>
 ```

##### section 3: Path
talk about the Hurricane Path Prediction
 ![](img/3.PNG)
 
 
```html
<section data-scene="Path">

                <h2 style="color: #045a8d" align="left" ><b>Hurricane Path Prediction</b></h2>
                <p align="justify">
                    The accurate prediction of the path and intensity of a hurricane is crucial for planning the evacuation of the
                    populated areas and for assessing its impact. Since the evolution of severe weather phenomena is associated
                    with notable transient changes in water contents in the low atmosphere, the accurate monitoring of atmosphere
                    water vapor or <i>perceptible water vapor (PWV) </i>spatial-temporal variations is critical to forecast and localize
                    severe storms. On the other hand, the dynamic perturbations in the atmosphere water content can be measured
                    from the tropospheric delay of GNSS signal propagated from a satellite to a receiver on the ground. By observing
                    PWV spatial-temporal variations during a hurricane event, the nature of PWV of this type of event can be
                    characterized.</p>
                    <br/>
                    <img src="img/Path.jpg" class="img-responsive" alt="responsive image" alt-text="Hurricane 2016" >
                    <br/><br/>


            </section>

```



##### section 4: end
in final section we add another background picture
 ![](img/4.PNG)
```html
 <section data-scene="end" data-background="assets/hurricane.jpg">
                <div class="fullscreen text-center">
                    <br/>
                    <h1 class="">Watching for the next hrricane!!!</h1>
                    <h1>
                        <small style="color: rgba(255,255,255,0.95)">Download Storymap.js from
                            <a href="https://github.com/HodaTahami/GPS_Meterology_Storymap"> <i><b> https://github.com/HodaTahami/GPS_Meterology_Storymap </b></i> </a>
                        </small>
                    </h1>

                </div>
                <div class="credit">
                    <p><img style="width:180px;" align="right" src="img/osu.png"></p> <br/><br/><br/>
                    <p>Created by Hoda Tahami From Oregon State University</p>
                </div>
            </section>
           
```

###### defining some button
A social media button to share the storymap to Facebook 

A github button linking to your github repository

An identify Icon to introduce the story map and auther and etc.

```
   <!--map div-->
        <div class="col-sm-6 col-md-8 storymap-map"></div>
    </div>


    <dl>
        <dt>
            <!--facebook icon-->
            <a class="fa fa-facebook-square btn" style="top:40px;color: #d0d1e6"
               href="https://facebook.com/sharer.php?u=https://github.com/HodaTahami/GPS_Meterology_Storymap"
               target="_blank"></a>
        </dt>
        <dt>
            <!--github icon-->
            <a class="fa fa-git-square btn" href="https://github.com/HodaTahami/GPS_Meterology_Storymap" style="top:60px;color:#d0d1e6"
               target="_blank"></a>
        </dt>
        <dt>
            <!--info icon-->
            <i class="fa fa-info-circle btn" style="top:80px;color:#d0d1e6" data-toggle="modal" data-target="#info-modal"></i>
        </dt>
    </dl>

    <!--the info page-->
    <div class="modal fade" id="info-modal" role="dialog">
        <div class="modal-dialog modal-md">
            <div class="modal-content">
                <div class="modal-header">
                    <button type="button" class="close" data-dismiss="modal">&times;</button>
                    <h4 class="modal-title">About</h4>
                </div>
                <div class="modal-body">
                    <p>This is a web map of hurricane monitoring using Global Positining system (GPS).
                        The story map library is derived from the storymap plugin for leaflet at <a href="https://github.com/HodaTahami/GPS_Meterology_Storymap"> <i><b> https://github.com/HodaTahami/GPS_Meterology_Storymap </b></i> </a>, and its functionality
                        relies on leaflet, Mapbox and Boostrap.</p>
                    <p><b>Author: Hoda Tahami</b> | College of Engineering, Department of Civil Engineeing | Oregon State University
                    </p>
                    <p>The <a href="https://www.nesdis.noaa.gov/sites/default/files/09sept_Irma_g16geocolor.mp4">background video</a> on the front page
                        was clipped from NOAA website. </p>
                    <p>The favicon image was acquired from <a href="http://en.proft.me/media/android/android_location_api.png"> GNSS </a></p>
                    <p>This story map uses geospatial data from mapbox and GPS data from NGS</p>
                </div>
            </div>
        </div>
    </div>
</div>

```

##### Defining layers

we introduce 3 different base map layers and also add data

```html

   var layers = {
          Stations: {
              layer: L.geoJson.ajax('assets/TestBuffer.geojson', {
                  color: 'orange',
                  weight: 20,
                  opacity: 0.3
              })
          },
          HurricanePath: {
              layer: L.geoJson.ajax('assets/HurricanePath.geojson', {
                  color: 'red',
                  weight: 20,
                  opacity: 0.3
              })
          },
          satellite: {
              layer: L.tileLayer('https://api.tiles.mapbox.com/v4/{id}/{z}/{x}/{y}.png?access_token=pk.eyJ1IjoiamFrb2J6aGFvIiwiYSI6ImNpcms2YWsyMzAwMmtmbG5icTFxZ3ZkdncifQ.P9MBej1xacybKcDN_jehvw', {
                  id: 'mapbox.satellite'
              })
          },
  
  
  
          cartodb_dark: {layer:L.tileLayer('https://api.mapbox.com/styles/v1/hoda-tahami/cj9j2lkb52uwl2spkgiqcuck8/tiles/256/{z}/{x}/{y}?access_token=pk.eyJ1IjoiaG9kYS10YWhhbWkiLCJhIjoiY2o4eHk3cDE2MDBzOTMzcXJ5dHJuY3h2NSJ9.qeQeUCbBvD3zRKcwb3TIlw#13.2/40.721642/-73.990029/0', {
              detectRetina: true,
              attribution: 'Created By <a href="http://github.com/HodaTahami/">Hoda Tahami</a> based on the <a href="assets/license.txt">Mapbox Odyssey style</a>'
          })}
      };

 
```
##### Scenes
In next step we define scenes
```
  var scenes = {
        overview: {lat: 44.0000000, lng: -123.5000000, zoom: 7, name: 'Cover Page'},
        GPSMap: {lat: 32.104717, lng:  -90.335284 , zoom: 6, name: 'GPSMap',layers: ['Stations']},
        Path: {lat: 31.648100, lng:  -83.445390 , zoom: 7, name: 'Path',layers: ['HurricanePath', 'satellite'] },
        end: {lat: 44.0000000, lng: -123.5000000, zoom: 7, name: 'The End'}
    };
 ```
 
 ##### Story map elements
 Finally define the story map elements
  ```
      $('#storymap').storymap({
          scenes: scenes,
          layers: layers,
          baselayer: layers.cartodb_dark,
          legend: true, // if you do not want a legend feature, you can simply not define the createLegend function.
          credits:  "Created by Hoda Tahami, 2018",
          loader: true,
          scalebar: false,
          navwidget: true,
  
          createMap: function () {
              // create a map in the "map" div, set the view to a given place and zoom
              var map = L.map($(".storymap-map")[0], {zoomControl: false, scrollWheelZoom: false}).setView([28.536343, -81.382425], 15);
  
              //add an miniglobe
              new L.Control.GlobeMiniMap({
                  marker: 'red',
                  position: 'bottomright'
              }).addTo(map);
  
  
              return map;
          }
      });
       ```