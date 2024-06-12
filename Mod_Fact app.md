## Simple android application to calculate the Mod ( a % b ) and factorial (n!) of a number.

### MainActivity.java
```java
package com.example.mod_fact;

import android.os.Bundle;
import android.view.View;
import android.widget.Button;
import android.widget.EditText;
import android.widget.TextView;

import androidx.appcompat.app.AppCompatActivity;

public class MainActivity extends AppCompatActivity {

    EditText editTextNumber1, editTextNumber2;
    Button buttonFactorial, buttonModulus;
    TextView textViewResult;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        editTextNumber1 = findViewById(R.id.editTextNumber1);
        editTextNumber2 = findViewById(R.id.editTextNumber2);
        buttonFactorial = findViewById(R.id.buttonFactorial);
        buttonModulus = findViewById(R.id.buttonModulus);
        textViewResult = findViewById(R.id.textViewResult);

        buttonFactorial.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                calculateFactorial();
            }
        });

        buttonModulus.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                calculateModulus();
            }
        });
    }

    private void calculateFactorial() {
        String num1Str = editTextNumber1.getText().toString();

        if (!num1Str.isEmpty()) {
            int num1 = Integer.parseInt(num1Str);
            long factorial = calculateFactorial(num1);
            textViewResult.setText("Factorial of " + num1 + " is " + factorial);
        } else {
            textViewResult.setText("Please enter a number.");
        }
    }

    private void calculateModulus() {
        String num1Str = editTextNumber1.getText().toString();
        String num2Str = editTextNumber2.getText().toString();

        if (!num1Str.isEmpty() && !num2Str.isEmpty()) {
            int num1 = Integer.parseInt(num1Str);
            int num2 = Integer.parseInt(num2Str);
            int modulus = num1 % num2;
            textViewResult.setText("Modulus of " + num1 + " and " + num2 + " is " + modulus);
        } else {
            textViewResult.setText("Please enter both numbers.");
        }
    }
    private long calculateFactorial(int n) {
        if (n == 0 || n == 1)
            return 1;
        else
            return n * calculateFactorial(n - 1);
    }
}

```

### AndroidManifest.xml

```xml
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
        android:theme="@style/Theme.MOD_FACT"
        tools:targetApi="31">
        <activity
            android:name=".MainActivity"
            android:exported="true">
            <intent-filter>
                <action android:name="android.intent.action.MAIN" />

                <category android:name="android.intent.category.LAUNCHER" />
            </intent-filter>
        </activity>
    </application>

</manifest>
```

### Output

Test cases for Mod calculator

> 23 % 12 = 11

![image](https://github.com/udayk01/Android-Security/assets/52235763/423c3e3d-cc91-428b-bf42-56a8506faec0)

> 57 % 25 = 7

![image](https://github.com/udayk01/Android-Security/assets/52235763/dd0b5d00-1019-49c2-aab6-9e1b9136d629)

Test cases for factorial 

> 5! = 120

![image](https://github.com/udayk01/Android-Security/assets/52235763/73e57e36-159d-4078-b0ae-75336b0363a4)

> 7! = 5040

![image](https://github.com/udayk01/Android-Security/assets/52235763/5a73c602-2c5a-439d-868d-dba20dbb70eb)
