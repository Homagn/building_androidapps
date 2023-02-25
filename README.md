Enabling developer model for your android phone and enable usb debugging
=========================================================================
(https://developer.android.com/studio/debug/dev-options)

1. Find the build number on your device 

	Google Pixel | Settings > About phone > Build number

	Samsung Galaxy S8 and later | Settings > About phone > Software information > Build number

	LG G6 and later | Settings > About phone > Software info > Build number

	HTC U11 and later | Settings > About > Software information > More > Build number or Settings > System > About phone > Software information > More > Build number

	OnePlus 5T and later | Settings > About phone > Build number



2. Tap the Build Number option seven times until you see the message You are now a developer! This enables developer options on your device.

3. Return to the previous screen to find Developer options at the bottom.

4. Enable usb debugging

Android 9 (API level 28) and higher: Settings > System > Advanced > Developer Options > USB debugging

Android 8.0.0 (API level 26) and Android 8.1.0 (API level 27): Settings > System > Developer Options > USB debugging

Android 7.1 (API level 25 (also worked for 21)) and lower: Settings > Developer Options > USB debugging





Now install android studio on windows by googling
=================================================



Instructions for creating first android studio web app project
==============================================================


(if you download github project then all the contents go inside (project_name)/app/src/main/ folder)
(example - simple_web_app/assets/, simple_web_app/java/, simple_web_app/res/, simple_web_app/AndroidManifest.xml all these folders should be in MyApplication/app/src/main/)




https://www.geeksforgeeks.org/build-an-android-app-with-html-css-and-javascript-in-android-studio/

Step by Step Implementation
===========================

Step 1: Create a New Project
============================

Open a new project.

We will be working on Empty Activity with language as Java. Leave all other options unchanged.

Name the application at your convenience.

There will be two default files named activity_main.xml and MainActivity.java.

If you don’t know how to create a new project in Android Studio then you can refer to How to Create/Start a New Project in Android Studio?  

Step 2. Working on the XML file
===============================

Navigate to the app > res > layout > activity_main.xml and add the below code to that file. Below is the code for the activity_main.xml file.

(xml file copy this)
```bash

<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity">

    <TextView
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Hello World!"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent" />
    <WebView
        android:layout_width="match_parent"
        android:layout_height="match_parent"
        android:id="@+id/webView"/>

</androidx.constraintlayout.widget.ConstraintLayout>
```


Step 3. Working on HTML file
============================

Navigate to app > new > file and name it as index.html. Use the following code in the index.html file

```bash
<html>
<head>
    <link rel="stylesheet" href="style.css">
</head>
<body>
<h1>
    This Text is shown with help of HTML.
</h1>
<script src="index.js"></script>
</body>
</html>
```

Step 4. Working on CSS file
===========================

Navigate to app > new > file and name it as style.css. Use the following code in the style.css file

```bash

body
{
    background-color: pink;
}
h1
{
    color:white
}

```

Step 5. Working on Javascript file
==================================

Navigate to app > new > file and name it as index.js. Use the following code in the index.js file

```bash
document.write("This text is shown from Javascript");
```


Step 6. Working on Java file
============================

Navigate to the MainActivity.java file and use the following code in it.

replace .androidwebapp; in the first line with the relevant name of your project

if the project folder is MyApplication it will be .myapplication;

```bash
package com.example.androidwebapp;
  
import androidx.appcompat.app.AppCompatActivity;
  
import android.os.Bundle;
import android.webkit.WebView;
  
public class MainActivity extends AppCompatActivity {
  
    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
  
        WebView webView=findViewById(R.id.webView);
        webView.getSettings().setJavaScriptEnabled(true);
        webView.loadUrl("file:///android_asset/index.html");
    }
}
```

Step 7. Changing asset location for apk
=======================================

Suppose for the main project folder thats storing everything, its in desktop/MyApplication

copy paste the following files from MyApplication/app/  to inside MyApplication/app/src/main/assets/ folder (create the assets folder if you have to)

index.html

index.js

style.css



Step 8 Connecting and verifying that the app runs on samsung galaxy s6
======================================================================

Connect the cellphone after enabling developer model to the computer via usb

In the top right corner of the android studio youll see a hammer symbol

near the hammer symbol, you can select option for the physical device which will be discovered after connecting usb as SM-S906L

click the play button just beside the recognized device tab and then gradle build will start and the application will show on the cellphone after sometime
