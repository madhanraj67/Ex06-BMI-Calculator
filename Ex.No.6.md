# Ex06 BMI Calculator
## Date:22:05:2025

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
index.html
```

<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>BMI Calculator</title>
  <link rel="stylesheet" href="style.css">
</head>
<body>
  <div class="container">
    <h1>Body Mass Index<br>Calculator</h1>
    <input type="number" id="height" placeholder="Height (cm)">
    <input type="number" id="weight" placeholder="Weight (kg)">
    <button onclick="calculateBMI()">Calculate BMI</button>
    <p id="result"></p>
    <p id="category"></p>
  </div>

  <script>
    function calculateBMI() {
      const height = parseFloat(document.getElementById('height').value) / 100;
      const weight = parseFloat(document.getElementById('weight').value);

      if (!height || !weight || height <= 0 || weight <= 0) {
        document.getElementById('result').innerText = "Please enter valid values.";
        document.getElementById('category').innerText = "";
        return;
      }

      const bmi = (weight / (height * height)).toFixed(1);
      document.getElementById('result').innerHTML = `<strong>Your BMI:</strong> ${bmi}`;

      let category = '';
      if (bmi < 18.5) category = 'Underweight';
      else if (bmi < 24.9) category = 'Normal weight';
      else if (bmi < 29.9) category = 'Overweight';
      else category = 'Obesity';

      document.getElementById('category').innerHTML = `<strong>Category:</strong> ${category}`;
    }
  </script>
</body>
</html>

```

style.css
```
body {
  background-color: rgb(62, 25, 68);
  color: white;
  font-family: Arial, sans-serif;
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
  margin: 0;
}

.container {
  background: #493330;
  border: 2px solid rgb(49, 232, 189);
  box-shadow: 0 0 20px rgb(239, 109, 209);
  padding: 30px;
  border-radius: 15px;
  text-align: center;
  max-width: 350px;
  width: 100%;
}

h1 {
  color: rgb(153, 152, 219);
  text-shadow: 0 0 5px rgb(46, 14, 14);
  margin-bottom: 20px;
}

input {
  width: 90%;
  padding: 10px;
  margin: 10px 0;
  border: none;
  border-radius: 8px;
  outline: none;
  font-size: 16px;
}

button {
  background-color: rgb(44, 117, 144);
  color: white;
  border: none;
  padding: 12px 20px;
  border-radius: 10px;
  font-size: 16px;
  cursor: pointer;
  margin-top: 10px;
  transition: 0.3s;
}

button:hover {
  background-color: rgb(123, 11, 125);
}

#result, #category {
  margin-top: 15px;
  font-size: 18px;
}

```


## OUTPUT
![Screenshot (60)](https://github.com/user-attachments/assets/78343fdc-c38f-4c74-a8e9-81b39f1a1fb3)



## RESULT
The program for creating BMI Calculator using React Router is executed successfully.
