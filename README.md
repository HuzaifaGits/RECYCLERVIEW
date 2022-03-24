# RECYCLERVIEW

JAVA FILE:


import android.os.Bundle;

import androidx.appcompat.app.AppCompatActivity;
import androidx.recyclerview.widget.LinearLayoutManager;
import androidx.recyclerview.widget.RecyclerView;

public class MainActivity extends AppCompatActivity {

    RecyclerView recyclerView;
    // Declare an adapter
    RecyclerView.Adapter programAdapter;
    RecyclerView.LayoutManager layoutmanager;
    // Next, prepare your data set. Create two string arrays for program name and program description respectively.
    String[] programNameList = {"Muzammil", "Omer", "Asim", "zulkefal", "saad", "basit", "obaid", "umar", "hammad", "capt jawad",
            "lt usama", "asad bhau", "musafa", "najam", "ads", "Pro snaps", "canva", "zong", "jazz", "Good hogya"};
    String[] programDescriptionList = {"fit apni suna", "Aoa", "snake",
            "thk hai na", "chak nikul",
            "ki hall hai", "ch saab", "hackur ",
            "kab jy ga", "ao ga mai", "chala gya hai",
            "okay thats good", "gg acha", "Never mind",
            "project done", "Post", "right now",
            "be yourself", "not available", "sahi hai"};
    // Define an integer array to hold the image recourse ids
    int[] programImages = {R.drawable.maxai, R.drawable.maxai,
            R.drawable.maxai, R.drawable.maxai, R.drawable.maxai,
            R.drawable.maxai, R.drawable.maxai, R.drawable.maxai,
            R.drawable.maxai, R.drawable.maxai, R.drawable.maxai,
            R.drawable.maxai, R.drawable.maxai, R.drawable.maxai,
            R.drawable.maxai, R.drawable.maxai, R.drawable.maxai,
            R.drawable.maxai, R.drawable.maxai, R.drawable.maxai};


    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
        // Obtain a handle for the RecyclerView
        recyclerView = findViewById(R.id.rvProgram);
        // You may use this setting to improve performance if you know that changes
        // in content do not change the layout size of the RecyclerView
        recyclerView.setHasFixedSize(true);
        // Use a linear layout manager
        layoutmanager = new LinearLayoutManager(this);
        recyclerView.setLayoutManager(layoutmanager);
        // Create an instance of ProgramAdapter. Pass context and all the array elements to the constructor
        programAdapter = new ProgramAdapter(this, programNameList, programDescriptionList, programImages);
        // Finally, attach the adapter with the RecyclerView
        recyclerView.setAdapter(programAdapter);
    }
}
