#Getting eeGeo.js on PhoneGap


### Pre-installations required:

1. Homebrew:
**$ ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)**
 
2. NPM: 
**$ brew install node**

3. PhoneGap:
**$ npm install phone gap**

	Alternatively, you can also use PhoneGap Desktop to create PhoneGap applications: 
*http://docs.phonegap.com/getting-started/1-install-phonegap/desktop/#mac*

4. Add an environment variable for Android SDK:   
a. **$ touch ~/.bash_profile**
b. **$ open ~/.bash_profile**
c. **Add: export ANDROID_HOME=<ROOT TO ANDROID SDK>**
d. **Save, close and restart terminal**

5. Android Studio: 
*https://developer.android.com/studio*

6. Xcode: 
*https://developer.apple.com/xcode*

### Creating a new PhoneGap project and linking it with eeGeo.js:

1. **$ phonegap create eegeo-phonegap --id "com.eegeo.phonegap" --name "eegeo-phonegap"**


2. Download eeGeo.js from *https://cdn-webgl.eegeo.com/eegeojs/early_access/latest/eegeo.js* and place it in <PROJECT>/www/js/ directory.

3. Download leaflet.css from *https://cdnjs.cloudflare.com/ajax/libs/leaflet/0.7.7/leaflet.css* and place it in <PROJECT>/www/css/ directory

4. Open index.html in www directory and replace all code with the following:



```<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Transitional//EN" "http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd"> 
<html xmlns="http://www.w3.org/1999/xhtml" ng-app="myApp">
   
  <head>
         
    <meta http-equiv="Content-Type" content="text/html; charset=utf-8" />
         
    <link rel="stylesheet" type="text/css" href="css/leaflet.css">
         <script type="text/javascript" src="js/eegeo.js"></script>     <script type="text/javascript" charset="utf-8" src="js/cordova.js"></script>      
    <meta name="format-detection" content="telephone=no" />
         
    <meta name="msapplication-tap-highlight" content="no" />
         
    <meta name="viewport" content="user-scalable=no, initial-scale=1, maximum-scale=1, minimum-scale=1, width=device-width" />
       
  </head>
    
  <body >
      
    <div id="map" style="width: 100vw; height: 100vh; padding:0; margin-left: -8px; margin-top: -8px;"></div>
     <script type="text/javascript">      var map = L.eeGeo.map("map", "239805706db267b03e086cc2c0c739d6");    </script>  
  </body>
   
</html>```



###Building PhoneGap on various platforms:

#####Android
1. Open terminal and add navigate to <PROJECT> directory

2.  **$ phonegap build android**

3. Import <PROJECT>/platforms/android in Android Studio and run

Note: Chrome 38 WebGL support required is present only in Android 5.0+.
	
#####iOS
1. Open terminal and add navigate to <PROJECT> directory

2. **$ phonegap build iOS**

3. Open <PROJECT>/platforms/ios/eegeo-phonegap.xcodeproj in Xcode and run 




> *Extracted from: http://docs.phonegap.com/getting-started*
