# MegaSorteSP
Projeto Atualizado APP-MegaSOrte 01.3

Projeto atualizado  - Projeto vencedor 
Por  - Douglas Baumhak Ribeiro
Mega SorteAPP


ACTIVITY_MAIN.XML
<?xml version="1.0" encoding="utf-8"?>
<ScrollView xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:id="@+id/ScrllFundo"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity">

    <androidx.constraintlayout.widget.ConstraintLayout
        android:id="@+id/fundoSCR"
        android:layout_width="match_parent"
        android:layout_height="match_parent"
        android:layout_gravity="center|center_horizontal"
        tools:context="com.android.application.MainActivity">


        <ImageView
            android:id="@+id/imageView"
            android:layout_width="0dp"
            android:layout_height="200dp"
            android:layout_marginStart="32dp"
            android:layout_marginLeft="32dp"
            android:layout_marginEnd="32dp"
            android:layout_marginRight="32dp"
            app:layout_constraintEnd_toEndOf="parent"
            app:layout_constraintStart_toStartOf="parent"
            app:layout_constraintTop_toTopOf="parent"
            app:srcCompat="@drawable/trevo5" />

        <Button
            android:id="@+id/b_generate"
            android:layout_width="150dp"
            android:layout_height="100dp"
            android:layout_marginStart="8dp"
            android:layout_marginLeft="8dp"
            android:layout_marginTop="8dp"
            android:layout_marginEnd="8dp"
            android:layout_marginRight="8dp"
            android:text="Jogar"
            android:textColor="#4CAF50"
            android:textColorHint="@color/cardview_light_background"
            android:textSize="35sp"
            android:textStyle="bold|italic"
            app:layout_constraintEnd_toEndOf="parent"
            app:layout_constraintStart_toStartOf="parent"
            app:layout_constraintTop_toBottomOf="@+id/et_max" />

        <EditText
            android:id="@+id/et_min"
            android:layout_width="272dp"
            android:layout_height="83dp"
            android:layout_marginStart="8dp"
            android:layout_marginLeft="8dp"
            android:layout_marginTop="32dp"
            android:layout_marginEnd="8dp"
            android:layout_marginRight="8dp"
            android:ems="10"
            android:hint="min"
            android:inputType="number"
            android:textColor="#1A9A0C"
            android:textSize="36sp"
            android:textStyle="bold"
            app:layout_constraintEnd_toEndOf="parent"
            app:layout_constraintStart_toStartOf="parent"
            app:layout_constraintTop_toBottomOf="@+id/txtJogar" />

        <EditText
            android:id="@+id/et_max"
            android:layout_width="268dp"
            android:layout_height="83dp"
            android:layout_below="@+id/et_min"
            android:layout_marginStart="8dp"
            android:layout_marginLeft="8dp"
            android:layout_marginTop="8dp"
            android:layout_marginEnd="8dp"
            android:layout_marginRight="8dp"
            android:ems="10"
            android:hint="max"
            android:inputType="number"
            android:textColor="#1A9A0C"
            android:textSize="36sp"
            android:textStyle="bold"
            app:layout_constraintEnd_toEndOf="parent"
            app:layout_constraintStart_toStartOf="parent"
            app:layout_constraintTop_toBottomOf="@+id/et_min" />

        <TextView
            android:id="@+id/tv_output"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:layout_marginStart="8dp"
            android:layout_marginLeft="8dp"
            android:layout_marginTop="24dp"
            android:layout_marginEnd="8dp"
            android:layout_marginRight="8dp"
            android:text="Clique para jogar"
            android:textColor="#1A9A0C"
            android:textSize="50sp"
            android:textStyle="bold|italic"
            app:layout_constraintEnd_toEndOf="parent"
            app:layout_constraintStart_toStartOf="parent"
            app:layout_constraintTop_toBottomOf="@+id/b_generate" />

        <TextView
            android:id="@+id/txtBemVindo"
            android:layout_width="0dp"
            android:layout_height="wrap_content"
            android:layout_marginStart="32dp"
            android:layout_marginLeft="32dp"
            android:layout_marginTop="24dp"
            android:layout_marginEnd="32dp"
            android:layout_marginRight="32dp"
            android:padding="@dimen/activity_horizontal_margin"
            android:text="Seja bem vindo ao MegaSorte"
            android:textColor="#1A9A0C"
            android:textSize="50sp"
            app:layout_constraintEnd_toEndOf="parent"
            app:layout_constraintStart_toStartOf="parent"
            app:layout_constraintTop_toBottomOf="@+id/imageView" />

        <TextView
            android:id="@+id/txtJogar"
            android:layout_width="0dp"
            android:layout_height="173dp"
            android:layout_marginStart="32dp"
            android:layout_marginLeft="32dp"
            android:layout_marginTop="8dp"
            android:layout_marginEnd="32dp"
            android:layout_marginRight="32dp"
            android:fontFamily="sans-serif-condensed-medium"
            android:padding="@dimen/activity_vertical_margin"
            android:text="Gere seus números e aposte na sua sorte.  Insira um número mínimo e um número máximo nos campos abaixo."
            android:textSize="40sp"
            android:textStyle="normal|italic"
            app:autoSizeTextType="none"
            app:layout_constraintEnd_toEndOf="parent"
            app:layout_constraintStart_toStartOf="parent"
            app:layout_constraintTop_toBottomOf="@+id/txtBemVindo"
            tools:ignore="UnknownId" />

    </androidx.constraintlayout.widget.ConstraintLayout>
</ScrollView>



PACKAGE COM.EXAMPLE.MEGASORTESP
package com.example.megasortesp;

import androidx.appcompat.app.AppCompatActivity;

import android.os.Bundle;
import android.view.View;
import android.widget.Button;
import android.widget.EditText;
import android.widget.TextView;
import java.util.Random;

public class MainActivity extends AppCompatActivity {

    EditText et_min, et_max;
    Button b_generate;
    TextView tv_output;

    Random r;
    int min, max, output;



    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate( savedInstanceState );
        setContentView( R.layout.activity_main );

        r = new Random(  );

        et_min = (EditText) findViewById( R.id.et_min );
        et_max = (EditText) findViewById( R.id.et_max );
        b_generate = (Button) findViewById( R.id.b_generate );
        tv_output = (TextView) findViewById( R.id.tv_output );

        b_generate.setOnClickListener( new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                String tempMin, tempMax;
                tempMin = et_min.getText().toString();
                tempMax = et_max.getText().toString();
                if(!tempMin.equals( "" ) && !tempMax.equals( "" )) {
                    min = Integer.parseInt( et_min.getText().toString() );
                    max = Integer.parseInt( et_max.getText().toString() );
                    if (max > min) {
                        output = r.nextInt((max - min) +1) + min;
                        tv_output.setText("Número sorteado foi: " + output);
                    }
                }


            }
        } );


    }
}


BuildConfig
package com.example.megasortesp;

public final class BuildConfig {
  public static final boolean DEBUG = Boolean.parseBoolean("true");
  public static final String APPLICATION_ID = "com.example.megasortesp";
  public static final String BUILD_TYPE = "debug";
  public static final int VERSION_CODE = 1;
  public static final String VERSION_NAME = "1.0";


build.gradle
buildscript {
    
    repositories {
        google()
        jcenter()
        
    }
    dependencies {
        classpath 'com.android.tools.build:gradle:4.1.0'
        

        // NOTE: Do not place your application dependencies here; they belong
        // in the individual module build.gradle files
    }
}

allprojects {
    repositories {
        google()
        jcenter()
        
    }
}

task clean(type: Delete) {
    delete rootProject.buildDir
}


Values.xml
<resources>
    <string name="app_name">MegaSorteSP</string>
    <string name="title_activity_login">Sign in</string>

</resources>


Styles.xml
<resources>

    
    <style name="AppTheme" parent="Theme.AppCompat.Light.DarkActionBar">
        <!-- Customize your theme here. -->
        <item name="colorPrimary">@color/colorPrimary</item>
        <item name="colorPrimaryDark">@color/colorPrimaryDark</item>
        <item name="colorAccent">@color/colorAccent</item>

    </style>

</resources>

Dimens.xml
<resources>
    <!-- Default screen margins, per the Android Design guidelines. -->
    <dimen name="activity_horizontal_margin">16dp</dimen>
    <dimen name="activity_vertical_margin">16dp</dimen>
</resources>
Color.xml
<?xml version="1.0" encoding="utf-8"?>
<resources>
    <color name="colorPrimary">#0AED16</color>
    <color name="colorPrimaryDark">#099710</color>
    <color name="colorAccent">#0AED16</color>
</resources>


Build.gradle

apply plugin: 'com.android.application'

android {
    compileSdkVersion 29
    buildToolsVersion "29.0.3"

    defaultConfig {
        applicationId "com.example.megasortesp"
        minSdkVersion 16
        targetSdkVersion 29
        versionCode 1
        versionName "1.0"

        testInstrumentationRunner "androidx.test.runner.AndroidJUnitRunner"
    }

    buildTypes {
        release {
            minifyEnabled false
            proguardFiles getDefaultProguardFile('proguard-android-optimize.txt'), 'proguard-rules.pro'
        }
    }

}

dependencies {
    implementation fileTree(dir: 'libs', include: ['*.jar'])

    implementation 'androidx.appcompat:appcompat:1.1.0'
    implementation 'androidx.constraintlayout:constraintlayout:1.1.3'
    implementation 'com.google.android.material:material:1.1.0'
    implementation 'androidx.annotation:annotation:1.1.0'
    implementation 'androidx.lifecycle:lifecycle-extensions:2.2.0'
    implementation 'androidx.legacy:legacy-support-v4:1.0.0'
    testImplementation 'junit:junit:4.12'
    androidTestImplementation 'androidx.test.ext:junit:1.1.1'
    androidTestImplementation 'androidx.test.espresso:espresso-core:3.2.0'
}
