# Ex-06 BMI Calculator
## Date:21-11-2025

## AIM
To create a BMI calculator using React Router 

## ALGORITHM
### STEP 1 State Initialization
Manage the current page (Home or Calculator) using React Router.

### STEP 2 User Input
Accept weight and height inputs from the user.

### STEP 3 BMI Calculation
Calculate the BMI based on user input.

### STEP 4 Categorization
Classify the BMI result into categories (Underweight, Normal weight, Overweight, Obesity).

### STEP 5 Navigation
Navigate between pages using React Router.

## PROGRAM
```
import { useState } from "react";

export default function App() {
  const [height, setHeight] = useState("");
  const [weight, setWeight] = useState("");
  const [bmi, setBmi] = useState(null);
  const [status, setStatus] = useState("");

  const calculateBMI = () => {
    if (!height || !weight) {
      alert("Enter height and weight");
      return;
    }

    const h = height / 100; // convert cm to meters
    const result = (weight / (h * h)).toFixed(2);
    setBmi(result);

    if (result < 18.5) setStatus("Underweight");
    else if (result >= 18.5 && result < 24.9) setStatus("Normal");
    else if (result >= 25 && result < 29.9) setStatus("Overweight");
    else setStatus("Obese");
  };

  const styles = {
    container: {
      height: "100vh",
      width: "100vw",
      background: "#0f172a",
      color: "white",
      display: "flex",
      justifyContent: "center",
      alignItems: "center",
    },
    card: {
      background: "#1e293b",
      padding: 20,
      borderRadius: 12,
      width: "320px",
      textAlign: "center",
    },
    input: {
      width: "100%",
      padding: 10,
      marginBottom: 12,
      borderRadius: 8,
      border: "none",
      outline: "none",
    },
    btn: {
      marginTop: 10,
      padding: "10px 14px",
      width: "100%",
      borderRadius: 8,
      border: "none",
      background: "#4F46E5",
      color: "white",
      cursor: "pointer",
      fontWeight: "bold",
    },
    result: {
      marginTop: 14,
      fontSize: "22px",
      fontWeight: "bold",
    },
  };

  return (
    <div style={styles.container}>
      <div style={styles.card}>
        <h2>BMI Calculator</h2>

        <input
          type="number"
          style={styles.input}
          placeholder="Height in cm"
          value={height}
          onChange={(e) => setHeight(e.target.value)}
        />

        <input
          type="number"
          style={styles.input}
          placeholder="Weight in kg"
          value={weight}
          onChange={(e) => setWeight(e.target.value)}
        />

        <button style={styles.btn} onClick={calculateBMI}>
          Calculate BMI
        </button>

        {bmi && (
          <div style={styles.result}>
            BMI: {bmi} <br />
            Status: <span>{status}</span>
          </div>
        )}
      </div>
    </div>
  );
}

```

## OUTPUT
<img width="1910" height="994" alt="image" src="https://github.com/user-attachments/assets/3a75be81-bfb8-4679-8a9b-d9d1077a3e20" />


## RESULT
The program for creating BMI Calculator using React Router is executed successfully.
