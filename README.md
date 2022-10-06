# Dice_Roll
//new repository
//activity_main.xml
<?xml version="1.0" encoding="utf-8"?>
<android.support.constraint.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context="com.codinginflow.diceexample.MainActivity">

    <ImageView
        android:id="@+id/image_view_dice"
        android:layout_width="300dp"
        android:layout_height="300dp"
        android:src="@drawable/dice1"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintLeft_toLeftOf="parent"
        app:layout_constraintRight_toRightOf="parent"
        app:layout_constraintTop_toTopOf="parent" />

</android.support.constraint.ConstraintLayout>
MainActivity.java
package com.codinginflow.diceexample;

import android.support.v7.app.AppCompatActivity;
import android.os.Bundle;
import android.view.View;
import android.widget.ImageView;

import java.util.Random;

public class MainActivity extends AppCompatActivity {
    private ImageView imageViewDice;
    private Random rng = new Random();

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        imageViewDice = findViewById(R.id.image_view_dice);
        imageViewDice.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                rollDice();
            }
        });
    }

    private void rollDice() {
        int randomNumber = rng.nextInt(6) + 1;

        switch (randomNumber) {
            case 1:
                imageViewDice.setImageResource(R.drawable.dice1);
                break;
            case 2:
                imageViewDice.setImageResource(R.drawable.dice2);
                break;
            case 3:
                imageViewDice.setImageResource(R.drawable.dice3);
                break;
            case 4:
                imageViewDice.setImageResource(R.drawable.dice4);
                break;
            case 5:
                imageViewDice.setImageResource(R.drawable.dice5);
                break;
            case 6:
                imageViewDice.setImageResource(R.drawable.dice6);
                break;
        }
    }
}


//KOTLIN


import android.R
import android.os.Bundle
import android.support.v7.app.AppCompatActivity
import android.widget.ImageView
import java.util.*

class MainActivity : AppCompatActivity() {
    private var imageViewDice: ImageView? = null
    private val rng = Random()
    protected fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        setContentView(R.layout.activity_main)
        imageViewDice = findViewById(R.id.image_view_dice)
        imageViewDice!!.setOnClickListener { rollDice() }
    }

    private fun rollDice() {
        val randomNumber = rng.nextInt(6) + 1
        when (randomNumber) {
            1 -> imageViewDice!!.setImageResource(R.drawable.dice1)
            2 -> imageViewDice!!.setImageResource(R.drawable.dice2)
            3 -> imageViewDice!!.setImageResource(R.drawable.dice3)
            4 -> imageViewDice!!.setImageResource(R.drawable.dice4)
            5 -> imageViewDice!!.setImageResource(R.drawable.dice5)
            6 -> imageViewDice!!.setImageResource(R.drawable.dice6)
        }
    }
}
