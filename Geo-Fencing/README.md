
## GeoFencing


### Tutorial 

Hello and Welcome to this tutorial, 


Below are the instructions on how to use ESRI’s AppStudio to create a simple geofencing app for mobile device use. 


This could be modified to use any REST service or custom hosted feature service layer! However for this example we will be creating an alert for Austin, Texas Pollinator’s Habitat & National Parks. 


Specifics: 
* User’s device internal GPS sensor is used for current of device
* Gyroscope internal to the device is used for motion & direction 
* Vibration is used to alert the user that they have passed a set geofence
* Multiple service layers can be displayed for alert


Directions:
Changing the mapped areas:
1. Download .zip from GitHub for ESRI-AppStudio-Samples (https://github.com/Esri/arcgis-appstudio-samples/tree/v2.1/Find%20Address)
2. Extract files to (Windows:) C:\Users\<username>\ArcGIS\AppStudio\Apps (Mac or linux:) Home\ArcGIS\AppStudio\Apps
3. Open ESRI AppStudio 
4. Search your home page for “Geo-Fencing”
5. Right Click on the Sample App tile 
6. Select ‘Duplicate’
7. In the resulting window rename the duplicate app accordingly and ‘Create’
8. The new app will appear on the home screen (easily searchable)
9. Double click on the tile 
   1. This will open the resulting sample app QML
   2. Examine the elements for things you may want to edit or remove
   3. Close the example 
1. Select the App tile; in the resulting right hand rail select ‘Edit’
   1. This will open ESRI QT Creator 
   2. The app that opens will be displaying the QML text for the sample app (despite being named ‘MyApp’)
   3. Take the time to browse the QML; a simple text, similar to java
      1. Objects are specified followed by their properties
1. Find the section ‘Map’ and delete the following sections: 
   1. FeatureLayer for ‘featureLayer_starbucks’ (lines 181-219)
1. File>Save All 
2. Now to add the new REST service: Austin, TX Pollinator Habitat REST FeatureServer
   1. Under the header ‘FeatureLayer’ for the esir building layer
      1. Replace ‘id’ with: featureLayer_pollinatorhabitat 
   2. Under the header ‘ServiceFeatureTable’
      1. Replace the ‘id’ with: pollinator_habitat
      2. Replace the ‘URL’ with: http://services.arcgis.com/0L95CJ0VTaxqcmED/ArcGIS/rest/services/pollinator_habitat/FeatureServer/0
      3. Ensure ‘visible’ is: ‘True’
1.  On lines 125 & 129 replace the arriving messages with your own text!
2.  File>Save All 
3.  Under the function ‘updateStatus’ remove the if statements that are specific to Starbuck (cmd+f>'starbucks'). Then replace the esribuildings with “pollinator_habitat” (this occurs twice).
4. Then in the resulting currentQueryTakeId = change this to  ‘servicefeaturetable_pollinatorhabitat’
5. Ensure that the projeciton refrence is being pulled from the REST Service you have added
Removing the layer options: 
1. Remove the roundbutton section for layers (unless you’re going to add multiple then ensure there is a button for all layers to be toggled on or off) 
#Removing Developer Watermark: 
1. Delete the green commented out text at the beginning of the code down to the import statements
Save ALL

You've now got a REST service geofence app to alert when entering an area or leaving by vibration, audio, and text notifiction!!

______________________________________________________________________________________________________________________________


## Issues

You must have more than one layer with the way this code is written. Any less will cause Contorl call errors. 

## Contributing

This began as a ESRI sample script prior to being ameneded for the tutorial. The final Script is avaible here to begin the tutorial please naviage to the ESRI Git Repository for App Studio.  
