#Assignment Activities for Module 3 Intents & Multiple Activities 


Lab Create Project with Multiple Activities (RGB – Red Green Blue)

Objectives:

    Familiar with Android Studio
    Implement simple GUI design
    Learn event driven programming
    Implement intent
    Create multiple activities


Outcome:

               You will create three activities (Main, Green, and Blue). Put a button on each activity. When the button is clicked it will launch the next activity. Let the cycle be Main (i.e., Red), Green, Blue and back to Main (i.e., Red) and cycle again and again.

Steps:
Step 1: Create a new Android Studio project and name it as “RGBcolors” by using Empty Activity template (Make sure Java is the language for this project)
Step 2: Open the interface file, activity_main.xml, in the Code Editor (The full path for the interface file is app/res/layout/activity_main.xml)
“Hello World” TextView is the only element in the interface file. Go to Code mode (by clicking the Code mode link on the upper right hand corner) to verity that.
Step 3: On the upper right hand corner click Design mode button (i.e., back to Design mode for activity_main.xml)
Step 4: On the left in the Design screen you will see Palette panel on the top of Component Tree panel.
Step 5: Click "Common" inside Palette and you see Button on the right under TextView. Click and hold “Button” and drag it down to Component Tree under the TextView (which is in a ConstraintLayout)
Note: You can achieve the same effect by dragging a Button to the Design View.
Step 6: On the layout you will see BUTTON is on the upper left hand corner at location (0, 0) while Hello World TextView is in the middle.
Step 7: Click the Code mode link (we may use Button or link interchangeably) on the upper right hand corner to back to the code screen to see the xml code.
Step 8: In the code you see the Hello World TextView with the following 4 lines of XML code:
app:layout_constraintBottom_toBottomOf="parent"
app:layout_constraintLeft_toLeftOf="parent"
app:layout_constraintRight_toRightOf="parent"
app:layout_constraintTop_toTopOf="parent"

These layout elements are used to place this TextView in the middle of the screen.
Step 9: Make sure you highlight the whole TextView code as follows:
<TextView
android:layout_width="wrap_content"
android:layout_height="wrap_content"
android:text="Hello World!"
app:layout_constraintBottom_toBottomOf="parent"
app:layout_constraintLeft_toLeftOf="parent"
app:layout_constraintRight_toRightOf="parent"
app:layout_constraintTop_toTopOf="parent" />

And click Delete button to delete this TextView element.
Now put the 4 layout lines into Button and let it looks as:

<Button
android:id="@+id/button"
android:layout_width="wrap_content"
android:layout_height="wrap_content"
app:layout_constraintBottom_toBottomOf="parent"
app:layout_constraintLeft_toLeftOf="parent"
app:layout_constraintRight_toRightOf="parent"
app:layout_constraintTop_toTopOf="parent"
android:text="Button" />

Step 10: Change the id and the text for this Button and make it looks like:
<Button
android:id="@+id/btn_green"
android:layout_width="wrap_content"
android:layout_height="wrap_content"
app:layout_constraintBottom_toBottomOf="parent"
app:layout_constraintLeft_toLeftOf="parent"
app:layout_constraintRight_toRightOf="parent"
app:layout_constraintTop_toTopOf="parent"
android:text="Green" />

Make sure the id is btn_green and text is Green. I put them in red here to draw your attention. You don’t need to put them in red.
If you do not follow this step exactly, your project will not work later on.
Step 11: Run the app (i.e., launch the project) to make sure a button with "Green" as its text sitting in the middle of the emulator screen.
There are couple of approaches to launch the project. One approach is to click “Run” menu item and select Run ‘app’ to launch the project.
Of course I assume you have your Android Virtual Device (AVD) setup already.
If not, you need to follow the steps mentioned in the Get Started lab to create an AVD.
Step 12: Right click com.example.rgbcolors under app/java (it has to be the first subfolder under java folder)  and select New > Activity > Empty Activity
I have seen students clicking on one of the other two subfolders under the java folder to create the second activity. If you do it that way, your project will not work the way as we plan.
So don’t do that.
Step 13: On the New Android Activity put “GreenActivity” into the Activity Name field and make sure the check for Generate a Layout File is on and the source Language is Java then click Finish button.
This will create the second activity, GreenActivity.java, with its layout file, activity_green.xml.
You should see these two newly created files in your editor screen along with acticity_main.xml and MainActivity.java.
Step 14: You can either click the activity_green.xml on the screen or double click activity_green.xml under layout folder to make it focus and display on your screen.
Step 15: You will see the following basic code in the editor screen:
<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android"
xmlns:app="http://schemas.android.com/apk/res-auto"
xmlns:tools="http://schemas.android.com/tools"
android:layout_width="match_parent"
android:layout_height="match_parent"
tools:context=".GreenActivity">

</androidx.constraintlayout.widget.ConstraintLayout>

You can see there is no UI element in this newly created layout file.
We need to create a button for this layout just as we created the button for the MainActivity.
There are couples of approaches to do it. For example, drag and drop a button from the palette as we have done for MainActivity above or write your XML statements directly.
For simplicity we will copy the code for button used at step 10 with modification (change the id and text) and insert it into the template so that the code should look like:
<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android"
xmlns:app="http://schemas.android.com/apk/res-auto"
xmlns:tools="http://schemas.android.com/tools"
android:layout_width="match_parent"
android:layout_height="match_parent"
tools:context=".GreenActivity">

    <Button
        android:id="@+id/btn_blue"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintLeft_toLeftOf="parent"
        app:layout_constraintRight_toRightOf="parent"
        app:layout_constraintTop_toTopOf="parent"
        android:text="Blue" />

</androidx.constraintlayout.widget.ConstraintLayout>

Pay attention to the “tools:context” attribute above. It is “.GreenActivity”
Why? Because I had seen students copying the whole XML file from activity_main.xml and forgot to change it accordingly. Remember we have moved to the Green activity. In this Green activity, we need to prepare to invoke the BLUE activity when a button is clicked.
Now let’s copy the element for the button and make the necessary changes (e.g., id and text in red above).
Step 16: Now let’s change the button background color for main activity (i.e., activity_main.xml) to be Green.
Add the following line
android:backgroundTint="#ff008000"

into the activity_main.xml for the button so it may look like the following:
<Button
android:id="@+id/btn_green"
android:layout_width="wrap_content"
android:layout_height="wrap_content"
android:backgroundTint="#ff008000"
app:layout_constraintBottom_toBottomOf="parent"
app:layout_constraintLeft_toLeftOf="parent"
app:layout_constraintRight_toRightOf="parent"
app:layout_constraintTop_toTopOf="parent"
android:text="Green" />

Step 17: See if you can follow the same idea to change the button background for activity_green.xml to be Blue.
Hint: #ff0000ff
Step 18: Run your app to see if the button background for the MainActivity displays correctly.
If you click the button, nothing changes because we have not defined any action for the button yet. We need to put code to handle the click event.
Sample code is provided below for your reference. You can Google the following “android how to start new activity on button click” to get more detail.
The following steps will define the java code to connect to the layout file and define the action for onClick event.
Step 19: Put the following code in the MainActivity.java
Step 19.1: Include needed libraries. The following import statements should be put before the class declaration
import android.content.Intent;
import android.view.View;
import android.widget.Button;

Step 19.2: Declare variable for button (Inside the class)
private Button btn_green;

Step 19.3: In the onCreate() method wire up the button with the onClick() event:
Put the following code after setContentView(R.layout.activity_main);
You should key in the code character by character to see how the smart editor can help you to finish your code by providing template to you while you are typing.
btn_green = findViewById(R.id.btn_green);
btn_green.setOnClickListener(new View.OnClickListener(){
@Override
public void onClick(View v){
Intent redirect = new Intent(v.getContext(), GreenActivity.class);
startActivity(redirect);
}
});
Attention: Here I use v to be the parameter for onClick() method. If you use the code completion by Android Studio you might see view instead. If that is the case, you need to change the code accordingly. Just make sure they are consistent.
After this step your code should look similar to the following:
package com.example.rgbcolors;

import androidx.appcompat.app.AppCompatActivity;

import android.content.Intent;
import android.os.Bundle;
import android.view.View;
import android.widget.Button;

public class MainActivity extends AppCompatActivity {

    private Button btn_green;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        btn_green = findViewById(R.id.btn_green);
        btn_green.setOnClickListener(new View.OnClickListener(){
            @Override
            public void onClick(View v){
                Intent redirect = new Intent(v.getContext(), GreenActivity.class);
                startActivity(redirect);
            }
        });
    }
}

Now you can run your app and click the Green button on MainActivity to go to GreenActivity.
So far I show you how to go from MainActivity to GreenActivity.
You need to apply the same approach to finish this lab by create Blue activity and change the interface file (xml file) and put in the java code to java files to create a cycle for jumping from GreenActivity to BlueActivity. After that follow the same approach to create a button on BlueActivity to allow a click on that button to start MainActivity.  The idea is to work on one jump at a time so that it will be easier to debug if needed.
Submission:
Upload manifest, with 3 java files and 3 layout files along with the screenshots for the 3 activities running on the emulator.

Challenge:
Now some food for thought to you. What happens on back stack? If you keep clicking on those buttons will there be multiple instances of MainActivity, GreenActivity and BlueActivity in the stack? 
 
