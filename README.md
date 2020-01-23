#### First android app

According to [tutorial](https://www.tutorialspoint.com/android/android_hello_world_example.html)
[I'm an inline-style link](https://www.google.com)

#### Components
#### Компоненты


class MainActivity : Activity {
}

what you see on screen
что видим на экране

class MyService : Service {
}

in background
на заднем плане


class MyReceiver : BroadcastReceiver {
   public void onReceive(context,intent){}
}

messaging between apps via **intents**
обмен сообщениями через **intent**


class MyContentProvider : ContentProvider {
   public void onCreate(){}
}

data exchange
обмен данными

``` kotlin
package com.example.first_app

import androidx.appcompat.app.AppCompatActivity
import android.os.Bundle

class MainActivity : AppCompatActivity() {

    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        setContentView(R.layout.activity_main)
    }
}
```



#### manifest.xml
``` xml
<?xml version="1.0" encoding="utf-8"?>
<manifest xmlns:android="http://schemas.android.com/apk/res/android"
    package="com.example.first_app" >

    <application
        android:allowBackup="true"
        android:icon="@mipmap/ic_launcher"
        android:label="@string/app_name"   
                   <!--@string refers to string.xml-->
        android:roundIcon="@mipmap/ic_launcher_round"
        android:supportsRtl="true"
        android:theme="@style/AppTheme" >
                    <!--@style refers to style.xml-->
                    <!--@style ссылается на style.xml-->
        <activity android:name=".MainActivity" >
                    <!--what you see on phone screen - mainActivity-->
                    <!--что видим на экране телефона - mainActivity-->
            <intent-filter>
                <action android:name="android.intent.action.MAIN" />
                    <!--entry point of the app-->
                    <!--вход в приложение-->
                <category android:name="android.intent.category.LAUNCHER" />
            </intent-filter>
        </activity>
    </application>

</manifest>
```

<activity>elements for activities
<service> elements for services
<receiver> elements for broadcast receivers
<provider> elements for content providers


#### strings.xml
res/values/strings.xml
``` xml
<resources>
   <string name="app_name">HelloWorld</string>
   <string name="hello_world">Hello world!</string>
   <string name="menu_settings">Settings</string>
   <string name="title_activity_main">MainActivity</string>
</resources>
```

####  activity_main.xml
шаблон для activity
res/layout/activity_main.xml
``` xml
<RelativeLayout xmlns:android="http://schemas.android.com/apk/res/android"
   xmlns:tools="http://schemas.android.com/tools"
   android:layout_width="match_parent"
   android:layout_height="match_parent" >

   <TextView
      android:layout_width="wrap_content"
      android:layout_height="wrap_content"
      android:layout_centerHorizontal="true"
      android:layout_centerVertical="true"
      android:padding="@dimen/padding_medium"
      android:text="@string/hello_world"
      tools:context=".MainActivity" /> # view in MainActivity
      tools:context=".MainActivity" /> #  отобразим в MainActivity

</RelativeLayout>
```

#### Launching
Connect Android phone via USB, enable remote debugging in developer options of Android phone, 
run app in Android Studio,    
give permissions to launch current app on device screen.

#### Запуск
Подключить телефон через USB, включить удалённую отладку в режиме разработчика на Android телефоне,
выбрать приложение и телефон в Инструментах,
разразрешить запуск приложений на самом телефоне.
