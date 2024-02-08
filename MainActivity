package com.example.gpa_haquee1_calculator;

import android.graphics.Color;
import android.os.Bundle;
import android.view.View;
import android.widget.Button;
import android.widget.EditText;
import android.widget.TextView;

import androidx.appcompat.app.AppCompatActivity;

public class MainActivity extends AppCompatActivity {
    Button computeButton;
    EditText editTextGrade1, editTextGrade2, editTextGrade3, editTextGrade4, editTextGrade5;
    TextView resultTextView;
    int clickCount = 0;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
// Req: At least five labels (textviews) and text fields that accept grades for 5 courses.
        computeButton = findViewById(R.id.b);
        editTextGrade1 = findViewById(R.id.e1);
        editTextGrade2 = findViewById(R.id.e2);
        editTextGrade3 = findViewById(R.id.e3);
        editTextGrade4 = findViewById(R.id.e4);
        editTextGrade5 = findViewById(R.id.e5);
        resultTextView = findViewById(R.id.t);
// Req: Your app should display a red background if GPA is less than 60, Yellow for 61-79, and Green for 80 to 100.
        resultTextView.setBackgroundColor(Color.WHITE);

        computeButton.setOnClickListener(new View.OnClickListener() {
            @Override
            // Req: The text on the compute button should be changed to clear the form once clicked.
            public void onClick(View v) {
                if (clickCount % 2 == 0) {
                    calculateGPA();
                } else {
                    clearForm();
                }
            }
        });
    }

    private void calculateGPA() {
        float grade1, grade2, grade3, grade4, grade5;
// Req: Your app should not accept empty fields.
        if (areFieldsEmpty()) {
            resultTextView.setText("");
        } else {
            grade1 = Float.parseFloat(editTextGrade1.getText().toString());
            grade2 = Float.parseFloat(editTextGrade2.getText().toString());
            grade3 = Float.parseFloat(editTextGrade3.getText().toString());
            grade4 = Float.parseFloat(editTextGrade4.getText().toString());
            grade5 = Float.parseFloat(editTextGrade5.getText().toString());

            float average = (grade1 + grade2 + grade3 + grade4 + grade5) / 5;

            if (average < 60) {
                resultTextView.setText(String.valueOf(average));
                resultTextView.setBackgroundColor(Color.RED);
            } else if (average >= 60 && average < 80) {
                resultTextView.setText(String.valueOf(average));
                resultTextView.setBackgroundColor(Color.YELLOW);
            } else if (average >= 80 && average <= 100) {
                resultTextView.setText(String.valueOf(average));
                resultTextView.setBackgroundColor(Color.GREEN);
            }
            // Req: The text on the compute button should be changed to clear the form once clicked.
            clickCount++;
            computeButton.setText("Clear");
        }
    }

    private void clearForm() {
        editTextGrade1.setText("");
        editTextGrade2.setText("");
        editTextGrade3.setText("");
        editTextGrade4.setText("");
        editTextGrade5.setText("");
        resultTextView.setText("");
        computeButton.setText("Compute GPA");
        resultTextView.setBackgroundColor(Color.WHITE);
        clickCount++;
    }

    private boolean areFieldsEmpty() {
        return editTextGrade1.getText().toString().isEmpty() ||
                editTextGrade2.getText().toString().isEmpty() ||
                editTextGrade3.getText().toString().isEmpty() ||
                editTextGrade4.getText().toString().isEmpty() ||
                editTextGrade5.getText().toString().isEmpty();
    }
}
