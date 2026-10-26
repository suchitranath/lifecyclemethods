# Ex.No:1 To create a HelloWorld Activity using all lifecycles methods to display messages.


## AIM:

To create a HelloWorld Activity using all lifecycles methods to display messages using Android Studio.

## EQUIPMENTS REQUIRED:

Latest Version Android Studio

## ALGORITHM:

Step 1: Open Android Stdio and then click on File -> New -> New project.

Step 2: Then type the Application name as HelloWorld and click Next. 

Step 3: Then select the Minimum SDK as shown below and click Next.

Step 4: Then select the Empty Activity and click Next. Finally click Finish.

Step 5: Design layout in activity_main.xml.

Step 6: Display message give in MainActivity file.

Step 7: Save and run the application.

## PROGRAM:
```
/*
Program to print the text “Hello World”.
Developed by: Suchitra Nath
Registeration Number : 212223220112
*/
```
# activity_main.xml
```

<LinearLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical"
    android:padding="20dp">

    <TextView
        android:id="@+id/messageText"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:text="Hello World!"
        android:textSize="24sp"
        android:textStyle="bold" />

</LinearLayout>

```
# MainActivity.java
```

package com.example.helloworld_mui1;

import android.os.Bundle;
import android.util.Log;
import android.widget.TextView;
import android.widget.Toast;

import androidx.appcompat.app.AppCompatActivity;

public class MainActivity extends AppCompatActivity {

    TextView messageText;
    String messages = "";

    void displayMessage(String message) {
        Log.d("ActivityLifecycle", message);

        if (messageText != null) {
            messages += message + "\n";
            messageText.setText(messages);
        }

        Toast.makeText(this, message,
                Toast.LENGTH_SHORT).show();
    }

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        messageText = findViewById(R.id.messageText);
        messages = "Hello World!\n";

        displayMessage("onCreate called");
    }

    @Override
    protected void onStart() {
        super.onStart();
        displayMessage("onStart called");
    }

    @Override
    protected void onResume() {
        super.onResume();
        displayMessage("onResume called");
    }

    @Override
    protected void onPause() {
        displayMessage("onPause called");
        super.onPause();
    }

    @Override
    protected void onStop() {
        displayMessage("onStop called");
        super.onStop();
    }

    @Override
    protected void onRestart() {
        super.onRestart();
        displayMessage("onRestart called");
    }

    @Override
    protected void onDestroy() {
        Log.d("ActivityLifecycle", "onDestroy called");
        super.onDestroy();
    }
}

```
# AndroidManifest.xml
```
<?xml version="1.0" encoding="utf-8"?>
<manifest xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools">

    <application
        android:allowBackup="true"
        android:dataExtractionRules="@xml/data_extraction_rules"
        android:fullBackupContent="@xml/backup_rules"
        android:icon="@mipmap/ic_launcher"
        android:label="@string/app_name"
        android:roundIcon="@mipmap/ic_launcher_round"
        android:supportsRtl="true"
        android:theme="@style/Theme.HelloWorld_mui1">
        <activity
            android:name=".MainActivity"
            android:exported="true"
            android:windowSoftInputMode="adjustResize">
            <intent-filter>
                <action android:name="android.intent.action.MAIN" />

                <category android:name="android.intent.category.LAUNCHER" />
            </intent-filter>
        </activity>
    </application>

</manifest>

```
## OUTPUT

<img width="1920" height="1200" alt="image" src="https://github.com/user-attachments/assets/350c80d1-076f-42f1-8aa8-2780a3e53d23" />




## RESULT
Thus a Simple Android Application create a HelloWorld Activity using all lifecycles methods to display messages using Android Studio is developed and executed successfully.
