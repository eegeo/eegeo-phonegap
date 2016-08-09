<a href="https://www.eegeo.com/">
    <img src="https://cdn2.eegeo.com/wp-content/uploads/2016/03/eegeo_logo_quite_big.png" alt="eeGeo Logo" title="eegeo" align="right" height="80px" />
</a>

# eeGeo Phonegap 

![eeGeo](https://cdn2.eegeo.com/wp-content/uploads/2016/03/readme-banner.jpg)

The eeGeo Phonegap project allows you to easily create eeGeo [beautiful 3D maps](https://www.eegeo.com/) phonegap multi-platform projects.

## Examples

You can find [feature-by-feature examples](https://www.eegeo.com/eegeo.js/examples/) on our website.

## API

A [full API reference](https://www.eegeo.com/eegeo.js/docs/) is also available on our website.

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

	c. Add: export ANDROID_HOME="[ROOT_TO_ANDROID_SDK]"

	d. Save, close and restart terminal

5. Android Studio: 
*https://developer.android.com/studio*

6. Xcode: 
*https://developer.apple.com/xcode*

### eegeo.js and leaflet.css:

1. Download eegeo.js from *https://cdn-webgl.eegeo.com/eegeojs/early_access/latest/eegeo.js* and replace eegeo.js with the downloaded one in <PROJECT>/www/js/ directory.

2. Download leaflet.css from *https://cdnjs.cloudflare.com/ajax/libs/leaflet/0.7.7/leaflet.css* replace leaflet.css3 with the downloaded one in <PROJECT>/www/css/ directory

### API Key 

In order to use the eeGeo 3D Maps API, you must sign up for a free developer account at https://www.eegeo.com/developers. After signing up, you'll be able to create an [API key](https://www.eegeo.com/developers/apikeys) for your apps. 

After signing up for a developer account and creating an API key, add it to the phonegap app [index.html file](https://github.com/eegeo/eegeo-phonegap/blob/master/www/index.html) replace <EEGEO_APP_KEY_HERE> with your your key

###Building PhoneGap on various platforms:

#####Android Build

1. Open terminal and add navigate to <PROJECT> directory

2.  **$ phonegap build android**

3. Import <PROJECT>/platforms/android in Android Studio and run

4. Additional step for Android to fix screen density issues - change the main Activity class in the project to include the following code snippet:

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
1. Open terminal and add navigate to <PROJECT> directory

2. **$ phonegap build ios**

3. Open <PROJECT>/platforms/ios/eegeo-phonegap.xcodeproj in Xcode and run 




> *Extracted from: http://docs.phonegap.com/getting-started*
