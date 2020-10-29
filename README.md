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
