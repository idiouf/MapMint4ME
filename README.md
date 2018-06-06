# MapMint4ME
MapMint4ME is an Android applicaiton to record your data on the field.
diff --git a/.idea/misc.xml b/.idea/misc.xml
index 5d19981..b0dc372 100644
--- a/.idea/misc.xml
+++ b/.idea/misc.xml
@@ -1,8 +1,5 @@
 <?xml version="1.0" encoding="UTF-8"?>
 <project version="4">
-  <component name="EntryPointsManager">
-    <entry_points version="2.0" />
-  </component>
   <component name="NullableNotNullManager">
     <option name="myDefaultNullable" value="android.support.annotation.Nullable" />
     <option name="myDefaultNotNull" value="android.support.annotation.NonNull" />
@@ -27,20 +24,13 @@
       </value>
     </option>
   </component>
-  <component name="ProjectLevelVcsManager" settingsEditedManually="false">
-    <OptionsSetting value="true" id="Add" />
-    <OptionsSetting value="true" id="Remove" />
-    <OptionsSetting value="true" id="Checkout" />
-    <OptionsSetting value="true" id="Update" />
-    <OptionsSetting value="true" id="Status" />
-    <OptionsSetting value="true" id="Edit" />
-    <ConfirmationsSetting value="0" id="Add" />
-    <ConfirmationsSetting value="0" id="Remove" />
-  </component>
-  <component name="ProjectRootManager" version="2" languageLevel="JDK_1_7" default="true" assert-keyword="true" jdk-15="true" project-jdk-name="1.8" project-jdk-type="JavaSDK">
+  <component name="ProjectRootManager" version="2" languageLevel="JDK_1_7" default="true" project-jdk-name="1.8" project-jdk-type="JavaSDK">
     <output url="file://$PROJECT_DIR$/build/classes" />
   </component>
   <component name="ProjectType">
     <option name="id" value="Android" />
   </component>
+  <component name="SvnBranchConfigurationManager">
+    <option name="mySupportsUserInfoFilter" value="true" />
+  </component>
 </project>
\ No newline at end of file
diff --git a/app/build.gradle b/app/build.gradle
index 84c6bad..9a035fc 100644
--- a/app/build.gradle
+++ b/app/build.gradle
@@ -1,12 +1,12 @@
 apply plugin: 'com.android.application'
 
 android {
-    compileSdkVersion 23
-    buildToolsVersion "23.0.2"
+    compileSdkVersion 27
+    buildToolsVersion '27.0.3'
     defaultConfig {
         applicationId "fr.geolabs.dev.mapmint4me"
         minSdkVersion 16
-        targetSdkVersion 23
+        targetSdkVersion 27
         versionCode 9
         versionName "1.0"
         multiDexEnabled true
@@ -23,9 +23,8 @@ android {
 
 dependencies {
     compile fileTree(include: ['*.jar'], dir: 'libs')
-    compile 'com.android.support:support-v4:23.4.0'
-    compile 'com.google.android.gms:play-services:9.0.2'
+    compile 'com.google.android.gms:play-services:12.0.1'
     compile 'com.google.android.gms:play-services-gcm:9.0.2'
-    compile 'com.google.android.gms:play-services-location:9.0.2'
+    compile 'com.google.android.gms:play-services-location:12.0.1'
     compile 'com.readystatesoftware.sqliteasset:sqliteassethelper:+'
 }
diff --git a/app/src/main/AndroidManifest.xml b/app/src/main/AndroidManifest.xml
index 8948b4b..1d36633 100644
--- a/app/src/main/AndroidManifest.xml
+++ b/app/src/main/AndroidManifest.xml
@@ -20,7 +20,7 @@
 
     <uses-feature android:name="android.hardware.camera" android:required="false" />
 
-    <supports-screens android:anyDensity="false"/>
+    <supports-screens android:anyDensity="true"/>
     <permission android:name="fr.meteolib.android.permission.C2D_MESSAGE"
         android:protectionLevel="signature" />
     <uses-permission android:name="fr.meteolib.android.permission.C2D_MESSAGE" />
diff --git a/app/src/main/assets/index.html b/app/src/main/assets/index.html
index ec53199..205c3b6 100644
--- a/app/src/main/assets/index.html
+++ b/app/src/main/assets/index.html
@@ -1,4 +1,5 @@
-<!DOCTYPE html>
+<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML Basic 1.1//EN"
+        "http://www.w3.org/TR/xhtml-basic/xhtml-basic11.dtd">
 <html lang="en">
 <head>
     <meta charset="utf-8">
@@ -107,13 +108,13 @@ body { padding-top: 70px; }
             <div id="navbar" class="navbar-collapse collapse">
                 <ul class="nav navbar-nav">
                     <li >
-                        <a href="index.html" aria-haspopup="true" aria-expanded="true"><span class="glyphicon glyphicon-home" aria-hidden="true"></span> Home <span class="caret"></span></a>
+                        <a href="./index.html" aria-haspopup="true" aria-expanded="true"><span class="glyphicon glyphicon-home" aria-hidden="true"></span> Home <span class="caret"></span></a>
                         <ul class="dropdown-menu">
-                            <li><a href="edit.html"><span class="glyphicon glyphicon-edit" aria-hidden="true"></span> Edit</a></li>
-                            <li><a href="import.html"><span class="glyphicon glyphicon-cloud-download" aria-hidden="true"></span> Import</a></li>
-                            <li><a href="view.html"><span class="glyphicon glyphicon-eye-open" aria-hidden="true"></span> View</a></li>
-                            <li><a href="export.html"><span class="glyphicon glyphicon-cloud-upload" aria-hidden="true"></span> Export</a></li>
-                            <li><a href="map.html"><span class="glyphicon glyphicon-globe" aria-hidden="true"></span> Map</a></li>
+                            <li><a href="./edit.html"><span class="glyphicon glyphicon-edit" aria-hidden="true"></span> Edit</a></li>
+                            <li><a href="./import.html"><span class="glyphicon glyphicon-cloud-download" aria-hidden="true"></span> Import</a></li>
+                            <li><a href="./view.html"><span class="glyphicon glyphicon-eye-open" aria-hidden="true"></span> View</a></li>
+                            <li><a href="./export.html"><span class="glyphicon glyphicon-cloud-upload" aria-hidden="true"></span> Export</a></li>
+                            <li><a href="./map.html"><span class="glyphicon glyphicon-globe" aria-hidden="true"></span> Map</a></li>
 
                         </ul>
                     </li>
@@ -185,6 +186,7 @@ body { padding-top: 70px; }
             if($(this).attr("href")==tmp[tmp.length-1]){
                 $(this).parent().addClass("active");
                 var closure=$(this);
+                try{
                 $.ajax({
                     method: "GET",
                     url: './menus/'+closure.attr('href'),
@@ -194,6 +196,8 @@ body { padding-top: 70px; }
                         closure.parent().remove();
                     }
                 });
+                }catch(e){
+                }
             }
         });
     });
diff --git a/app/src/main/assets/scripts/generic.js b/app/src/main/assets/scripts/generic.js
index 7eb9f2f..b2d315a 100644
--- a/app/src/main/assets/scripts/generic.js
+++ b/app/src/main/assets/scripts/generic.js
@@ -1,4 +1,4 @@
-var MM4ME_DEBUG=false;
+var MM4ME_DEBUG=true;
 var EDITION_TYPE_FILE=5;
 var mainTable={};
 var mtable=null;
@@ -1159,8 +1159,10 @@ function authenticate(url,login,passwd,func,func1){
         success: function(data){
             if(MM4ME_DEBUG)
                 console.log(data);
-            if(func)
+            if(func){
+                console.log("Call func!")
                 func();
+            }
         },
         error: function(){
             if(func1){
@@ -1187,7 +1189,8 @@ function authenticate(url,login,passwd,func,func1){
 
 function disconnect(url){
     var curl=url+"?service=WPS&request=Execute&version=1.0.0&Identifier=authenticate.clogOut&DataInputs=&RawDataOutput=Result";
-    console.log(curl);
+    if(MM4ME_DEBUG)
+        console.log(curl);
     $.ajax({
         method: "GET",
         url: curl,
diff --git a/app/src/main/assets/scripts/import.js b/app/src/main/assets/scripts/import.js
index 78ebbec..6e3869b 100644
--- a/app/src/main/assets/scripts/import.js
+++ b/app/src/main/assets/scripts/import.js
@@ -45,7 +45,7 @@
                     var closure=a;
                     return function(){
                         closure1=$(this);
-                        authenticate(closure["url"],closure["login"],closure["password"],function(){createSqliteDB4ME(closure1,closure["url"]);});
+                        authenticate(closure["url"],closure["login"],closure["password"],function(){console.log(closure['url']);console.log(closure1);createSqliteDB4ME(closure1,closure["url"]);});
                     }
                 };
                 $(".media-list").find("button").last().click(cmd(list[i]));
@@ -121,6 +121,7 @@
 
         function createSqliteDB4ME(elem,url){
             var curl=url+"?service=WPS&version=1.0.0&request=Execute&Identifier=mm4me.createSqliteDB4ME&DataInputs=&ResponseDocument=Result@asReference=true;Result1@asReference=true;Result2@asReference=true&storeExecuteResponse=true&status=true";
+            console.log(curl);
             $.ajax({
                 method: "GET",
                 url: curl,
@@ -131,10 +132,12 @@
                     var statusLocation=$(data).find("ExecuteResponse").attr("statusLocation");
                     if(MM4ME_DEBUG)
                         console.log(statusLocation);
-                    ping(elem.parent().parent(),statusLocation,url);
+                    if(statusLocation)
+                        ping(elem.parent().parent(),statusLocation,url);
                     disconnect(url);
                 },
-                error: function(){
+                error: function(data){
+                    console.log(data);
                     alert("error !");
                 }
             });
diff --git a/app/src/main/java/fr/geolabs/dev/mapmint4me/MapMint4ME.java b/app/src/main/java/fr/geolabs/dev/mapmint4me/MapMint4ME.java
index c5b698c..be6347d 100644
--- a/app/src/main/java/fr/geolabs/dev/mapmint4me/MapMint4ME.java
+++ b/app/src/main/java/fr/geolabs/dev/mapmint4me/MapMint4ME.java
@@ -177,6 +177,18 @@ public class MapMint4ME extends Activity implements
             setContentView(R.layout.activity_map_mint4_me);
             myLocationManager = (LocationManager) getSystemService(Context.LOCATION_SERVICE);
             myWebView = (WebView) findViewById(R.id.webView);
+            myWebView.setWebViewClient(new WebViewClient() {
+                @Override
+                public boolean shouldOverrideUrlLoading(WebView webView, String webResourceRequest) {
+                    if (Uri.parse(webResourceRequest).getScheme().equals("file")) {
+                        webView.loadUrl(webResourceRequest);
+                    } else {
+                        // If the URI is not pointing to a local file, open with an ACTION_VIEW Intent
+                        webView.getContext().startActivity(new Intent(Intent.ACTION_VIEW, Uri.parse(webResourceRequest)));
+                    }
+                    return true; // in both cases we handle the link manually
+                }
+            });
             //myWebView.setWebViewClient(new WebViewClient() { @Override public void onReceivedSslError(WebView view, SslErrorHandler handler, SslError error){ handler.proceed(); } });
             WebSettings webSettings = myWebView.getSettings();
             /*myWebView.setScrollBarStyle(WebView.SCROLLBARS_INSIDE_OVERLAY);
@@ -214,32 +226,6 @@ public class MapMint4ME extends Activity implements
                 mDialogDaemon.shutdown();
                 mDialogDaemon = null;
             }
-            /*mDialogDaemon = new ScheduledThreadPoolExecutor(1);
-            // This process will execute immediately, then execute every 3 seconds.
-            mDialogDaemon.scheduleAtFixedRate(new Runnable() {
-                @Override
-                public void run() {
-                    runOnUiThread(new Runnable() {
-                        @Override
-                        public void run() {
-                            // Check Internet access
-                            Log.d(TAG, "******** CALL THREAD TO CHECK WIFI / GPS ********");
-                            ConnectivityManager connectivityManager
-                                    = (ConnectivityManager) getSystemService(Context.CONNECTIVITY_SERVICE);
-                            NetworkInfo activeNetworkInfo = connectivityManager.getActiveNetworkInfo();
-                            mInternetActivated=activeNetworkInfo != null && activeNetworkInfo.isConnected();
-                            String res = null;
-                            try {
-                                res = mWebAppInterface.getFullGPS();
-                            }catch(Exception e) {
-                                Log.d(TAG, "javascript:updateStatus("+res+","+mInternetActivated+");");
-                            }
-                            myWebView.loadUrl("javascript:updateStatus("+res+","+mInternetActivated+");");
-                            Log.d(TAG, "javascript:updateStatus("+res+","+mInternetActivated+");");
-                        }
-                    });
-                }
-            }, 0L, 10000L, TimeUnit.MILLISECONDS);*/
 
         }
 
diff --git a/app/src/main/res/xml/file_paths.xml b/app/src/main/res/xml/file_paths.xml
index f5d1c88..ead582f 100644
--- a/app/src/main/res/xml/file_paths.xml
+++ b/app/src/main/res/xml/file_paths.xml
@@ -1,4 +1,5 @@
 <?xml version="1.0" encoding="utf-8"?>
 <paths xmlns:android="http://schemas.android.com/apk/res/android">
     <files-path name="my_images" path="Android/data/fr.geolabs.dev.mapmint4me/files/Pictures" />
+    <files-path name="android_assets" path="Android/data/fr.geolabs.dev.mapmint4me/assets" />
 </paths>
diff --git a/build.gradle b/build.gradle
index c20bca1..65997f8 100644
--- a/build.gradle
+++ b/build.gradle
@@ -3,9 +3,14 @@
 buildscript {
     repositories {
         jcenter()
+        maven {
+            url 'https://maven.google.com/'
+            name 'Google'
+        }
+        google()
     }
     dependencies {
-        classpath 'com.android.tools.build:gradle:2.2.2'
+        classpath 'com.android.tools.build:gradle:3.1.2'
 
         // NOTE: Do not place your application dependencies here; they belong
         // in the individual module build.gradle files
@@ -15,6 +20,7 @@ buildscript {
 allprojects {
     repositories {
         jcenter()
+        google()
     }
 }
 
diff --git a/gradle/wrapper/gradle-wrapper.properties b/gradle/wrapper/gradle-wrapper.properties
index 5ca183d..3e5f28c 100644
--- a/gradle/wrapper/gradle-wrapper.properties
+++ b/gradle/wrapper/gradle-wrapper.properties
@@ -1,6 +1,6 @@
-#Tue Sep 27 16:09:35 CEST 2016
+#Tue Jun 05 16:00:54 CEST 2018
 distributionBase=GRADLE_USER_HOME
 distributionPath=wrapper/dists
 zipStoreBase=GRADLE_USER_HOME
 zipStorePath=wrapper/dists
-distributionUrl=https\://services.gradle.org/distributions/gradle-2.14.1-all.zip
+distributionUrl=https\://services.gradle.org/distributions/gradle-4.4-all.zip
