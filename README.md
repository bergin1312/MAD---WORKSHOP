# MAD---WORKSHOP


MAINACTIVITY.JAVA
```java package com.example.workshop;

import androidx.appcompat.app.AppCompatActivity;

import android.content.Intent;
import android.os.Bundle;
import android.view.View;
import android.widget.Button;
import android.widget.EditText;

public class MainActivity extends AppCompatActivity {
    private EditText editTextName, editTextAge, editTextEmail, editTextContact;
    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        editTextName = findViewById(R.id.editTextName);
        editTextAge = findViewById(R.id.editTextAge);
        editTextEmail = findViewById(R.id.editTextEmail);
        editTextContact = findViewById(R.id.editTextContact);

        Button buttonSubmit = findViewById(R.id.buttonSubmit);

        buttonSubmit.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View view) {
                String name = editTextName.getText().toString();
                String age = editTextAge.getText().toString();
                String email = editTextEmail.getText().toString();
                String contact = editTextContact.getText().toString();

                Intent intent = new Intent(MainActivity.this, MainActivity2.class);
                intent.putExtra("name", name);
                intent.putExtra("age", age);
                intent.putExtra("email", email);
                intent.putExtra("contact", contact);
                startActivity(intent);
            }
        });
    }
}
```
MAINACTIVITY2.JAVA
```java
package com.example.workshop;

import androidx.appcompat.app.AppCompatActivity;

import android.content.Intent;
import android.os.Bundle;
import android.widget.TextView;

public class MainActivity2 extends AppCompatActivity {

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main2);

        TextView textViewName = findViewById(R.id.textViewName);
        TextView textViewAge = findViewById(R.id.textViewAge);
        TextView textViewEmail = findViewById(R.id.textViewEmail);
        TextView textViewContact = findViewById(R.id.textViewContact);

        Intent intent = getIntent();

        if (intent != null) {
            String name = intent.getStringExtra("name");
            String age = intent.getStringExtra("age");
            String email = intent.getStringExtra("email");
            String contact = intent.getStringExtra("contact");

            textViewName.setText("Name: " + name);
            textViewAge.setText("Age: " + age);
            textViewEmail.setText("Email: " + email);
            textViewContact.setText("Contact: " + contact);
        }
    }
}
```
ACTIVITY_MAIN.XML
```xml
<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity">

    <RelativeLayout xmlns:android="http://schemas.android.com/apk/res/android"
        android:layout_width="match_parent"
        android:layout_height="match_parent">

        <EditText
            android:id="@+id/editTextName"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:hint="Enter Name" />

        <EditText
            android:id="@+id/editTextAge"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:layout_below="@id/editTextName"
            android:hint="Enter Age" />

        <EditText
            android:id="@+id/editTextEmail"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:layout_below="@id/editTextAge"
            android:hint="Enter Email" />

        <EditText
            android:id="@+id/editTextContact"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:layout_below="@id/editTextEmail"
            android:hint="Enter Contact Number" />

        <Button
            android:id="@+id/buttonSubmit"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:layout_below="@id/editTextContact"
            android:layout_centerHorizontal="true"
            android:text="Submit" />
    </RelativeLayout>

</androidx.constraintlayout.widget.ConstraintLayout>
```

# OUTPUT
![Screenshot (8)](https://github.com/bergin1312/MAD---WORKSHOP/assets/119404594/500844be-dbd0-4951-9363-25f3b2729165)
![Screenshot (9)](https://github.com/bergin1312/MAD---WORKSHOP/assets/119404594/40c6a92c-704b-48e6-974b-3c7b19020ad6)
![Screenshot (10)](https://github.com/bergin1312/MAD---WORKSHOP/assets/119404594/bf09d5b8-25c2-4a77-935d-e7b63237159c)

