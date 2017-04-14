<a href="https://www.eegeo.com/">
    <img src="https://cdn2.eegeo.com/wp-content/uploads/2017/04/WRLD_Blue.png" align="right" height="80px" />
</a>

# WRLD PhoneGap 

![WRLD](https://cdn2.eegeo.com/wp-content/uploads/2017/04/screenselection01.png)

The WRLD PhoneGap project allows you to easily create WRLD [beautiful 3D maps](https://www.wrld3d.com/) using PhoneGap on multiple platforms.

## Examples

You can find [feature-by-feature examples](https://docs.wrld3d.com/wrld.js/latest/docs/examples/) on our website.

## API

A [full API reference](https://docs.wrdl3d.com/wrld.js/latest/docs/api/) is also available on our website.

## Getting Started

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

	c. Add: **export ANDROID_HOME="[ROOT_TO_ANDROID_SDK]"**

	d. Save, close and restart terminal.

5. Android Studio: 
*https://developer.android.com/studio*

6. Xcode: 
*https://developer.apple.com/xcode*

### wrld.js and leaflet.css:

1. Download wrld.js from *https://cdn-webgl.wrld3d.com/wrldjs/early_access/latest/wrld.js* and replace wrld.js with the downloaded one in ````<PROJECT>/www/js/```` directory.

2. Download leaflet.css from *https://cdnjs.cloudflare.com/ajax/libs/leaflet/0.7.7/leaflet.css* replace leaflet.css3 with the downloaded one in ````<PROJECT>/www/css/```` directory.

### WRLD API Key:

In order to use the WRLD 3D Maps API, you must sign up for a free developer account at https://www.wrld3d.com/developers. After signing up, you'll be able to create an [API key](https://www.wrld3d.com/developers/apikeys) for your apps. 

After signing up for a developer account and creating an API key, add it to the PhoneGap app [index.html file](https://github.com/wrld3d/wrld-phonegap/blob/master/www/index.html) by replacing ````<EEGEO_APP_KEY_HERE>```` with your key.

###Building PhoneGap on various platforms:

#####Android Build

1. Open terminal and navigate to ````<PROJECT>```` directory.

2.  **$ phonegap build android**

3. Import ````<PROJECT>/platforms/android```` in Android Studio and run.

4. Additional step for Android to fix screen density issues - change the main Activity class in the Android project to include the following code snippet:

````@Override
   public void onCreate(Bundle savedInstanceState)
   {
       super.onCreate(savedInstanceState);
       loadUrl(launchUrl);
       CordovaWebViewEngine engine = appView.getEngine();
       SystemWebView webView = (SystemWebView)engine.getView();
       WebSettings settings = webView.getSettings();
       settings.setUseWideViewPort(true);
       settings.setLoadWithOverviewMode(true);
   }
   ````
Note: Requisite support for Chrome 38 WebGL is present only in Android 5.0+.

#####iOS
1. Open terminal and navigate to ````<PROJECT>```` directory

2. **$ phonegap build ios**

3. Open ````<PROJECT>/platforms/ios/eegeo-phonegap.xcodeproj```` in Xcode and run 




> *Extracted from: http://docs.phonegap.com/getting-started*
