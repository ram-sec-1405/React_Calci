# Ex04 Simple Calculator - React Project
## Date:28/03/2025

## REG NO: 212223220086

## AIM
To  develop a Simple Calculator using React.js with clean and responsive design, ensuring a smooth user experience across different screen sizes.

## ALGORITHM
### STEP 1
Create a React App.

### STEP 2
Open a terminal and run:
  <ul><li>npx create-react-app simple-calculator</li>
  <li>cd simple-calculator</li>
  <li>npm start</li></ul>

### STEP 3
Inside the src/ folder, create a new file Calculator.js and define the basic structure.

### STEP 4
Plan the UI: Display screen, number buttons (0-9), operators (+, -, *, /), clear (C), and equal (=).

### STEP 5
Create a new file Calculator.css in src/ and add the styling.

### STEP 6
Open src/App.js and modify it.

### STEP 7
Start the development server.
  npm start

### STEP 8
Open http://localhost:3000/ in the browser.

### STEP 9
Test the calculator by entering numbers and operations.

### STEP 10
Fix styling issues and refine content placement.

### STEP 11
Deploy the website.

### STEP 12
Upload to GitHub Pages for free hosting.

## PROGRAM

### calculator.js

```
import React, { useState, useEffect } from 'react';
import './App.css';

function App() {
  const [input, setInput] = useState('');
  const [result, setResult] = useState('');

  // Handle button clicks
  const handleClick = (value) => {
    if (value === '=') {
      calculateResult();
    } else if (value === 'C') {
      clearInput();
    } else if (value === '⌫') {
      setInput((prevInput) => prevInput.slice(0, -1));
    } else {
      setInput((prevInput) => prevInput + value);
    }
  };

  // Calculate the result
  const calculateResult = () => {
    try {
      if (input.includes('/0')) {
        setResult('Error: Division by zero');
      } else {
        setResult(eval(input).toString());
      }
    } catch (error) {
      setResult('Error');
    }
  };

  // Clear input and result
  const clearInput = () => {
    setInput('');
    setResult('');
  };

  // Handle keyboard input
  useEffect(() => {
    const handleKeyDown = (event) => {
      const key = event.key;
      if (/[0-9+\-*/.=C]|Backspace|Enter|Escape/.test(key)) {
        event.preventDefault();
        if (key === 'Enter' || key === '=') {
          calculateResult();
        } else if (key === 'Backspace') {
          setInput((prevInput) => prevInput.slice(0, -1));
        } else if (key === 'Escape' || key === 'C') {
          clearInput();
        } else {
          setInput((prevInput) => prevInput + key);
        }
      }
    };

    window.addEventListener('keydown', handleKeyDown);
    return () => window.removeEventListener('keydown', handleKeyDown);
  }, [input]);

  return (
    <div className="calculator">
      <h1>CALCI</h1>
      <div className="display">
        <input type="text" value={input} readOnly />
        <div className="result">{result}</div>
      </div>
      <div className="buttons">
        {['C', '%', '⌫', '/', '7', '8', '9', '*', '4', '5', '6', '-', '1', '2', '3', '+', '0', '.', '='].map((button) => (
          <button
            key={button}
            onClick={() => handleClick(button)}
            className={button === '=' ? 'equals' : button === 'C' ? 'clear' : button === '⌫' ? 'backspace' : ''}
          >
            {button}
          </button>
        ))}
      </div>
      <footer className="footer">
        <p>&copy; Developed by: RAMPRASATH.R</p>
        <p>Register Number: 212223220086</p>
      </footer>
    </div>
    
  );
  
}

export default App;
```

### calculator.css
```
body {
  margin: 0;
  font-family: 'Arial', sans-serif;
  background: linear-gradient(135deg, #235fb8, #c3cfe2);
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
}

.calculator {
  background: #2c3e50;
  padding: 20px;
  border-radius: 15px;
  box-shadow: 0px 10px 20px rgba(0, 0, 0, 0.2);
  width: 320px;
}

h1 {
  color: #ecf0f1;
  text-align: center;
  margin-bottom: 20px;
  font-size: 24px;
}

.display {
  background: #34495e;
  padding: 15px;
  border-radius: 10px;
  margin-bottom: 20px;
}

.display input {
  width: 100%;
  height: 40px;
  font-size: 24px;
  text-align: right;
  padding: 5px;
  box-sizing: border-box;
  border: none;
  background: transparent;
  color: #ecf0f1;
}

.result {
  font-size: 20px;
  text-align: right;
  padding: 5px;
  color: #bdc3c7;
}

.buttons {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 10px;
}

button {
  width: 100%;
  height: 60px;
  font-size: 20px;
  cursor: pointer;
  border: none;
  background: #34495e;
  color: #ecf0f1;
  border-radius: 10px;
  transition: background 0.3s ease;
}

button:hover {
  background: #1abc9c;
}

button:active {
  background: #16a085;
}

.equals {
  grid-column: span 2;
  background: #e67e22;
}

.equals:hover {
  background: #d35400;
}

.clear {
  background: #e74c3c;
}

.clear:hover {
  background: #c0392b;
}

.backspace {
  background: #3498db;
}

.backspace:hover {
  background: #2980b9;
}
.footer {
  margin-top: 20px;
  padding: 10px;
  text-align: center;
  font-size: 14px;
  color: #666;
  border-top: 1px solid #eee;
}

.footer p {
  margin: 5px 0;
}
```



## OUTPUT
![WhatsApp Image 2025-03-28 at 22 51 53_8219b635](https://github.com/user-attachments/assets/08d80260-254e-41f3-9a7b-1d6fdf65dd98)




## RESULT
The program for developing a simple calculator in React.js is executed successfully.
