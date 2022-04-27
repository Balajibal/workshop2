# workshop2
## TITLE: 
Show Image file sending data from one activity to another activity screenshot using android studio.

## PROCEDURE:
Step-1:Use Android StudioIDE to create an Android application and name it as My App under a package com.example.MyApp, with blank Activity. 
Step-2: Modify the default content of res/layout/activity_main.xml file to display the required content and design the layout. 
Step-3: Add the following code to src/MainActivity.java 
Step-4: Create an empty activity and add the following code.
Step-5: Run your application.
## PROGRAM:
### Mainactivity.java:
```java
package com.example.workshop2;
import android.content.Intent;
import androidx.appcompat.app.AppCompatActivity;
import android.os.Bundle;
import android.view.View;
import android.widget.Button;
import android.widget.EditText;
public class MainActivity extends AppCompatActivity {
 Button send_button;
 EditText send_text;
 @Override
 protected void onCreate(Bundle savedInstanceState)
 {
 super.onCreate(savedInstanceState);
 setContentView(R.layout.activity_main);
 send_button = (Button)findViewById(R.id.send_button_id);
 send_text = (EditText)findViewById(R.id.send_text_id);
 send_button.setOnClickListener(new View.OnClickListener() {
 @Override
 public void onClick(View v)
 {
 String str = send_text.getText().toString();
 Intent intent = new Intent(getApplicationContext(), 
Second_Activity.class);
 intent.putExtra("message_key", str);
 // start the Intent
 startActivity(intent);
 }
 });

```

### Activity_main.xml:
```xml
<?xml version="1.0" encoding="utf-8"?>
<RelativeLayout
 xmlns:android="http://schemas.android.com/apk/res/android"
 xmlns:tools="http://schemas.android.com/tools"
 android:layout_width="match_parent"
 android:layout_height="match_parent"
 tools:context=".MainActivity">
 <EditText
 android:id="@+id/send_text_id"
 android:layout_width="300dp"
 android:layout_height="wrap_content"
 android:textSize="25dp"
 android:hint="@string/input"
 android:textStyle="bold"
 android:layout_marginTop="20dp"
 android:layout_marginLeft="40dp"
 tools:ignore="Autofill,SpUsage,TextFields" />
 <Button
 android:id="@+id/send_button_id"
 android:layout_width="wrap_content"
 android:layout_height="40dp"
 android:text="@string/send"
 android:textStyle="bold"
 android:layout_marginTop="150dp"
 android:layout_marginLeft="150dp"/>
</RelativeLayout>
```

### Second_Activity.java:
```java
package com.example.workshop2;
import androidx.appcompat.app.AppCompatActivity;
import android.content.Intent;
import android.os.Bundle;
import android.widget.TextView;
public class Second_Activity extends AppCompatActivity {
 TextView receiver_msg;
 @Override
 protected void onCreate(Bundle savedInstanceState)
 {
 super.onCreate(savedInstanceState);
 setContentView(R.layout.activity_second);
 receiver_msg = (TextView)findViewById(R.id.received_value_id);
 Intent intent = getIntent();
 String str = intent.getStringExtra("message_key");
 receiver_msg.setText(str);
 }
}
```

### Activity_second.xml:
```xml
<?xml version="1.0" encoding="utf-8"?>
<RelativeLayout xmlns:android="http://schemas.android.com/apk/res/android"
 xmlns:app="http://schemas.android.com/apk/res-auto"
 xmlns:tools="http://schemas.android.com/tools"
 android:layout_width="match_parent"
 android:layout_height="match_parent"
 tools:context=".Second_Activity">
 <TextView
 android:id="@+id/received_value_id"
 android:layout_width="300dp"
 android:layout_height="50dp"
 android:textStyle="bold"
 android:textSize="40dp"
 android:layout_marginTop="20dp"
 android:layout_marginLeft="40dp"/>
</RelativeLayout>
```
## OUTPUT:
 ![image](https://user-images.githubusercontent.com/75235334/165352020-bc96fcd0-83e7-4223-aac8-6fbd382bb6aa.png)
![image](https://user-images.githubusercontent.com/75235334/165352070-3ca792e1-8e05-4acd-aa0f-12f3697ccb30.png)







# arithmetic operations 



## Aim:
Display the output for arithmetic operations using android studio
## Procedure :
Step-1:Use Android StudioIDE to create an Android application and name it as My App under a package com.example.MyApp, with blank Activity. 
Step-2: Modify the default content of res/layout/activity_main.xml file to display the required content and design the layout. 
Step-3: Add the following code to src/MainActivity.java 
Step-4: Create an empty activity and add the following code for arthimetic operations
Step-5: Run your application
## Source code
### MainActivity.java
```java
package com.example.firstproject;

import android.os.Bundle;
import android.view.View;
import android.widget.EditText;
import android.widget.TextView;
import androidx.appcompat.app.AppCompatActivity;
public class MainActivity extends AppCompatActivity {
    EditText e1, e2;
    TextView t1;
    int num1, num2;
    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
    }
    public boolean getNumbers() {
        e1 = (EditText) findViewById(R.id.num1);
        e2 = (EditText) findViewById(R.id.num2);
        t1 = (TextView) findViewById(R.id.result);
        String s1 = e1.getText().toString();
        String s2 = e2.getText().toString();
        if ((s1.equals(null) && s2.equals(null))
                || (s1.equals("") && s2.equals(""))) {
            String result = "Please enter a value";
            t1.setText(result);
            return false;
        } else {
            num1 = Integer.parseInt(s1);
            num2 = Integer.parseInt(s2);
        }
        return true;
    }
    public void doSum(View v) {
        if (getNumbers()) {
            int sum = num1 + num2;
            t1.setText(num1+"+"+num2+"="+Integer.toString(sum));
        }
    }
    public void doSub(View v) {
        if (getNumbers()) {
            int sub = num1 - num2;
            t1.setText(num1+"-"+num2+"="+Integer.toString(sub));
        }
    }
    public void doMul(View v) {
        if (getNumbers()) {
            int mul = num1 * num2;
            t1.setText(num1+"*"+num2+"="+Integer.toString(mul));
        }
    }
    public void doDiv(View v) {
        if (getNumbers()) {
            double div = num1 / (num2 * 1.0);
            t1.setText(num1+"/"+num2+"="+Double.toString(div));
        }
    }
}

```

### Activity-main.xml
```xml
<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:background="#8BC34A"
    android:backgroundTint="@android:color/darker_gray"
    tools:context=".MainActivity">

    <TextView
        android:layout_width="194dp"
        android:layout_height="43dp"
        android:layout_marginStart="114dp"
        android:layout_marginTop="58dp"
        android:layout_marginEnd="103dp"
        android:layout_marginBottom="502dp"
        android:scrollbarSize="30dp"
        android:text=" Calculator"
        android:textAppearance="@style/TextAppearance.AppCompat.Body1"
        android:textSize="30dp"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.0"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent"
        app:layout_constraintVertical_bias="0.0" />

    <EditText
        android:id="@+id/num1"
        android:layout_width="364dp"
        android:layout_height="28dp"
        android:layout_marginStart="72dp"
        android:layout_marginTop="70dp"
        android:layout_marginEnd="71dp"
        android:layout_marginBottom="416dp"
        android:background="@android:color/white"
        android:ems="10"
        android:hint="Enter Number 1"
        android:inputType="number"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent" />
    <EditText
        android:id="@+id/num2"
        android:layout_width="363dp"
        android:layout_height="30dp"
        android:layout_marginStart="72dp"
        android:layout_marginTop="112dp"
        android:layout_marginEnd="71dp"
        android:layout_marginBottom="374dp"
        android:background="@android:color/white"
        android:ems="10"
        android:hint="Enter Number 2"
        android:inputType="number"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent" />
    <TextView
        android:id="@+id/result"
        android:layout_width="356dp"
        android:layout_height="71dp"
        android:layout_marginStart="41dp"
        android:layout_marginTop="151dp"
        android:layout_marginEnd="48dp"
        android:layout_marginBottom="287dp"
        android:background="@android:color/white"
        android:text="Result"
        android:textColorLink="#673AB7"
        android:textSize="25sp"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent" />
    <Button
        android:id="@+id/sum"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginStart="16dp"
        android:layout_marginTop="292dp"
        android:layout_marginEnd="307dp"
        android:layout_marginBottom="263dp"
        android:backgroundTint="@android:color/holo_red_light"
        android:onClick="doSum"
        android:text="+"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent" />
    <Button
        android:id="@+id/sub"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginStart="210dp"
        android:layout_marginTop="292dp"
        android:layout_marginEnd="113dp"
        android:layout_marginBottom="263dp"
        android:backgroundTint="@android:color/holo_red_light"
        android:onClick="doSub"
        android:text="-"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent" />
    <Button
        android:id="@+id/div"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginStart="307dp"
        android:layout_marginTop="292dp"
        android:layout_marginEnd="16dp"
        android:layout_marginBottom="263dp"
        android:backgroundTint="@android:color/holo_red_light"
        android:onClick="doDiv"
        android:text="/"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.0"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent" />
    <Button
        android:id="@+id/mul"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginStart="113dp"
        android:layout_marginTop="292dp"
        android:layout_marginEnd="210dp"
        android:layout_marginBottom="263dp"
        android:backgroundTint="@android:color/holo_red_light"
        android:onClick="doMul"
        android:text="x"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent" />
</androidx.constraintlayout.widget.ConstraintLayout>


```
## OUTPUT:
![image](https://user-images.githubusercontent.com/75235334/165478430-1e701798-3ed5-4375-b188-6ce98dfd792f.png)
![image](https://user-images.githubusercontent.com/75235334/165478478-58074ee8-0a68-4ae3-b07d-c9c59f32f28a.png)



