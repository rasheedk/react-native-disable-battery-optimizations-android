# react-native-disable-battery-optimizations-android

## Getting started

`$ npm install react-native-disable-battery-optimizations-android --save`

### Mostly automatic installation for react native >= v 0.60
Manual linking not required for above versions

For manual linking :
`$ react-native link react-native-disable-battery-optimizations-android`

### Manual installation



#### Android

1. Open up `android/app/src/main/java/[...]/MainActivity.java`
  - Add `import com.reactlibrary.RNDisableBatteryOptimizationsandroidPackage;` to the imports at the top of the file
  - Add `new RNDisableBatteryOptimizationsPackage()` to the list returned by the `getPackages()` method
2. Append the following lines to `android/settings.gradle`:
  	```
  	include ':react-native-disable-battery-optimizations-android'
  	project(':react-native-disable-battery-optimizations-android').projectDir = new File(rootProject.projectDir, 	'../node_modules/react-native-disable-battery-optimizations-android/android')
  	```
3. Insert the following lines inside the dependencies block in `android/app/build.gradle`:
  	```
      compile project(':react-native-disable-battery-optimizations-android')
  	```

## Usage
```javascript
import RNDisableBatteryOptimizationsAndroid from 'react-native-disable-battery-optimizations-android';

RNDisableBatteryOptimizationsAndroid.isBatteryOptimizationEnabled().then((isEnabled)=>{
	if(isEnabled){
		RNDisableBatteryOptimizationsAndroid.openBatteryModal();
	}
});

// for direct whitelisting app with Instant Dialogue 
//The user will be taken to a screen where they can indicate that they are willing to suspend portions of Doze mode effects on your app.
Note: Play store will not allow using this method, and will allow only as an exception


RNDisableBatteryOptimizationsAndroid.enableBackgroundServicesDialogue();

Also 
Add  this permission in your AndroidManifest.xml

<uses-permission android:name="android.permission.REQUEST_IGNORE_BATTERY_OPTIMIZATIONS"/>


```
  
