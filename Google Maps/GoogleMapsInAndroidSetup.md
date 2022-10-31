### setup firebae in android

#### 1. amend android/build.gradle
###### 1.1 inset
````
dependencies {
classpath 'com.android.tools.build:gradle:7.1.2'
classpath "org.jetbrains.kotlin:kotlin-gradle-plugin:$kotlin_version"

// add this
classpath 'com.google.gms:google-services:4.3.13'
}
````

###### 1.2 Ensure these lines are present

    repositories {
        google()
    mavenCentral()
    }

and
 
    allprojects {
        repositories {
        google()
        mavenCentral()
    }
}

#### 2. amend android/app/build.gradle
###### 2.1 edit the default config
    defaultConfig {

    // Note the application id has to match appId in the Google platform console.

        applicationId "com.example.zz_google_maps1"
        minSdkVersion 21
        targetSdkVersion flutter.targetSdkVersion
        versionCode flutterVersionCode.toInteger()
        versionName flutterVersionName
        multiDexEnabled true
    }
and add in this plugin

    apply plugin: 'com.google.gms.google-services'

###### 2.2 edit the android section to set minSdkVersion
    android {
    compileSdkVersion 33


#### 3. amend android/app/maine/AndroidManifest.xml
     <meta-data android:name="com.google.android.geo.API_KEY"
           android:value="AIzaSyABjEoS3sOCrgtKIW94o9cxTfN_xvVtehQ"/>
    </application>

and at the tope of the manifest add the user permissions

    <manifest xmlns:android="http://schemas.android.com/apk/res/android"
        package="com.example.zz_gmap">
        <uses-permission android:name="android.permission.ACCESS_FINE_LOCATION" />
        <uses-permission android:name="android.permission.ACCESS_COARSE_LOCATION" />

#### 4. Copy google-services.json to android/app/main folder
Copy the google-services.json file created in the Firestore console to android/app/main folder
