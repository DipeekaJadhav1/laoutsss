
<?xml version="1.0" encoding="utf-8"?>
<TableLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools"
    android:id="@+id/tableLayout"
    android:layout_width="match_parent"
    android:layout_height="wrap_content"
    android:stretchColumns="*"
    android:padding="16dp"
    tools:context=".MainActivity">

    <!-- Header Row -->
    <TableRow>
        <TextView
            android:text="Name"
            android:textStyle="bold"
            android:padding="8dp"
            android:background="#D1C4E9" />

        <TextView
            android:text="Age"
            android:textStyle="bold"
            android:padding="8dp"
            android:background="#D1C4E9" />

        <TextView
            android:text="City"
            android:textStyle="bold"
            android:padding="8dp"
            android:background="#D1C4E9" />
    </TableRow>

    <!-- Row 1 -->
    <TableRow>
        <TextView android:text="John" android:padding="8dp" />
        <TextView android:text="25" android:padding="8dp" />
        <TextView android:text="New York" android:padding="8dp" />
    </TableRow>

    <!-- Row 2 -->
    <TableRow>
        <TextView android:text="Emma" android:padding="8dp" />
        <TextView android:text="30" android:padding="8dp" />
        <TextView android:text="London" android:padding="8dp" />
    </TableRow>

    <!-- Row 3 -->
    <TableRow>
        <TextView android:text="Liam" android:padding="8dp" />
        <TextView android:text="22" android:padding="8dp" />
        <TextView android:text="Paris" android:padding="8dp" />
    </TableRow>

</TableLayout>



package com.example.myapplication;

import android.os.Bundle;
import android.widget.TableLayout;
import android.widget.TableRow;
import android.widget.TextView;
import android.widget.Toast;
import androidx.appcompat.app.AppCompatActivity;

public class MainActivity extends AppCompatActivity {

    TableLayout tableLayout;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        tableLayout = findViewById(R.id.tableLayout);

        // Example: Add new row dynamically from Java
        TableRow newRow = new TableRow(this);

        TextView name = new TextView(this);
        name.setText("Ava");
        name.setPadding(8, 8, 8, 8);

        TextView age = new TextView(this);
        age.setText("28");
        age.setPadding(8, 8, 8, 8);

        TextView city = new TextView(this);
        city.setText("Tokyo");
        city.setPadding(8, 8, 8, 8);

        newRow.addView(name);
        newRow.addView(age);
        newRow.addView(city);

        tableLayout.addView(newRow); // Add the new row to the TableLayout

        // Toast to confirm
        Toast.makeText(this, "Row added dynamically", Toast.LENGTH_SHORT).show();
    }
}

