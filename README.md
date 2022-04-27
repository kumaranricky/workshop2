# Show Image file sending data from one activity to another activity screenshot using android studio.

## AIM:
To Show Image file sending data from one activity to another activity screenshot using android studio.

## EQUIPMENTS REQUIRED: 
Android Studio(Min. required Artic Fox)

## ALGORITHM: 
Step 1: Open Android Stdio and then click on File -> New -> New project.

Step 2: Then type the Application name as “workshop 2″ and click Next.

Step 3: Then select the Minimum SDK as shown below and click Next.

Step 4: Then select the Empty Activity and click Next. Finally click Finish.

Step 5: Design layout in activity_main.xml.

stpe 6: Insert the image in drawable file

Step 7: Then select another empty activty.

Step 8: open google page using Implicit Intents and display factorial number using Explicit Intents in MainActivity file.

Step 9: Save and run the application.

## PROGRAM:
java

### activity_main.xml

<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity">


    <ImageView
        android:id="@+id/imageView"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.549"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent"
        app:srcCompat="@drawable/tiger" />

    <Button
        android:id="@+id/send"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Button"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toBottomOf="@+id/imageView" />

</androidx.constraintlayout.widget.ConstraintLayout>



### MainActivity.java

package com.example.workshop2;

import androidx.appcompat.app.AppCompatActivity;

import android.content.Intent;
import android.os.Bundle;
import android.view.View;
import android.widget.Button;

public class MainActivity extends AppCompatActivity {
    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
        Button Send = (Button) findViewById(R.id.send);

        Send.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                // add the image in putExtra
                // and send the data in next activity
                Intent intent = new Intent(MainActivity.this, MainActivity2.class);
                String name;
                intent.putExtra( name="myimage", R.drawable.tiger);
                startActivity(intent);
            }
        });
    }
}

###activity_main2.xml


<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity2">



    <ImageView
        android:id="@+id/img_second"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintStart_toStartOf="parent" />

    <TextView
        android:id="@+id/textView"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="second activity"
        tools:layout_editor_absoluteX="154dp"
        tools:layout_editor_absoluteY="577dp" />


</LinearLayout>



### MainActivity2.java
package com.example.workshop2;

import androidx.appcompat.app.AppCompatActivity;

import android.os.Bundle;
import android.widget.ImageView;

public class MainActivity2 extends AppCompatActivity {

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.main_activity);
        ImageView ImageView = (ImageView) findViewById(R.id.img_second);

        // check if any value sent from previous activity
        Bundle bundle = getIntent().getExtras();

        // if bundle is not null then get the image value
        if (bundle != null) {
            int res_image = bundle.getInt("myimage");
            ImageView.setImageResource(res_image);
        }

    }
}



### output

![Screenshot (91)](https://user-images.githubusercontent.com/75243072/165440275-e2be1a3a-8226-4225-baa6-971b5f14631d.png)
![Screenshot (92)](https://user-images.githubusercontent.com/75243072/165440306-cc2dd551-0fe9-47cf-8488-9136541a3312.png)


### result
Thus a Simple Android Application Show Image file sending data from one activity to another activity screenshot is developed and executed successfully.
