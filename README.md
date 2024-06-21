import React, { useState } from 'react';
import './calculator.css';


const Calculator = () => {
  const [displayValue, setDisplayValue] = useState('');

  const handleButtonClick = (value) => {
    switch (value) {
      case 'C':
        setDisplayValue('');
        break;
      case '=':
        try {
          const result = eval(displayValue); 
          setDisplayValue(result.toString());
        } catch (error) {
          setDisplayValue('Error');
        }
        break;
      default:
        setDisplayValue((prevValue) => prevValue + value);
        break;
    }
  };

  return (
    <div className="calculator">
      <div className="display">{displayValue}</div>
      <button onClick={() => handleButtonClick('(')}>(</button>
      <button onClick={() => handleButtonClick(')')}>)</button>
      <button onClick={() => handleButtonClick('mc')}>mc</button>
      <button onClick={() => handleButtonClick('m+')}>m+</button>
      <button onClick={() => handleButtonClick('m-')}>m-</button>
      <button onClick={() => handleButtonClick('mr')}>mr</button>
      <button onClick={() => handleButtonClick('C')}>C</button>
      <button className="operator" onClick={() => handleButtonClick('*')}>*</button>
      <button className="operator" onClick={() => handleButtonClick('-')}>-</button>
      <button className="operator" onClick={() => handleButtonClick('%')}>%</button>
      <button className="operator" onClick={() => handleButtonClick('÷')}>÷</button>
      <button onClick={() => handleButtonClick('2nd')}>2nd</button>
      <button onClick={() => handleButtonClick('x2')}>x2</button>
      <button onClick={() => handleButtonClick('x3')}>x3</button>
      <button onClick={() => handleButtonClick('xy')}>xy</button>
      <button onClick={() => handleButtonClick('ex')}>ex</button>
      <button onClick={() => handleButtonClick('10x')}>10x</button>
      <button onClick={() => handleButtonClick('7')}>7</button>
      <button onClick={() => handleButtonClick('8')}>8</button>
      <button onClick={() => handleButtonClick('9')}>9</button>
      <button className="operator" onClick={() => handleButtonClick('x')}>x</button>
      <button onClick={() => handleButtonClick('1/x')}>1/x</button>
      <button onClick={() => handleButtonClick('√x')}>√x</button>
      <button onClick={() => handleButtonClick('3√x')}>3√x</button>
      <button onClick={() => handleButtonClick('√x')}>√x</button>
      <button onClick={() => handleButtonClick('ln')}>ln</button>
      <button onClick={() => handleButtonClick('log10')}>log10</button>
      <button onClick={() => handleButtonClick('4')}>4</button>
      <button onClick={() => handleButtonClick('5')}>5</button>
      <button onClick={() => handleButtonClick('6')}>6</button>
      <button className="operator" onClick={() => handleButtonClick('-')}>-</button>
      <button onClick={() => handleButtonClick('x!')}>x!</button>
      <button onClick={() => handleButtonClick('sin')}>sin</button>
      <button onClick={() => handleButtonClick('cos')}>cos</button>
      <button onClick={() => handleButtonClick('tan')}>tan</button>
      <button onClick={() => handleButtonClick('e')}>e</button>
      <button onClick={() => handleButtonClick('EE')}>EE</button>
      <button onClick={() => handleButtonClick('1')}>1</button>
      <button onClick={() => handleButtonClick('2')}>2</button>
      <button onClick={() => handleButtonClick('3')}>3</button>
      <button className="operator" onClick={() => handleButtonClick('+')}>+</button>
      <button onClick={() => handleButtonClick('Rad')}>Rad</button>
      <button onClick={() => handleButtonClick('sinh')}>sinh</button>
      <button onClick={() => handleButtonClick('cosh')}>cosh</button>
      <button onClick={() => handleButtonClick('tanh')}>tanh</button>
      <button onClick={() => handleButtonClick('π')}>π</button>
      <button onClick={() => handleButtonClick('Rand')}>Rand</button>
      <button onClick={() => handleButtonClick('0')}>0</button>
      <button onClick={() => handleButtonClick('.')}>.</button>
      <button className="operator" onClick={() => handleButtonClick('=')}>=</button>
    </div>
  );
};

export default Calculator;

CSS Code
body {
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
    background-color: #f0f0f5;
    margin: 0;
    font-family: 'Helvetica Neue', Arial, sans-serif;
}

.calculator {
    width: 320px;
    border-radius: 20px;
    box-shadow: 0 10px 25px rgba(0, 0, 0, 0.2);
    background-color: #333;
    padding: 20px;
}

.display {
    background-color: #222;
    padding: 10px;
    border-radius: 10px;
    margin-bottom: 20px;
    text-align: right;
}

.display input {
    width: 100%;
    border: none;
    background: none;
    color: #fff;
    font-size: 2em;
    text-align: right;
    outline: none;
}

.buttons {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    grid-gap: 10px;
}

button {
    width: 100%;
    padding: 20px;
    border: none;
    border-radius: 10px;
    background-color: #444;
    color: white;
    font-size: 1.2em;
    cursor: pointer;
    transition: background-color 0.3s;
}

button:active {
    background-color: #555;
}

button:nth-child(4n+4),
button:nth-last-child(-n+3) {
    background-color: #f7931e;
    color: white;
}

button:nth-child(4n+4):active,
button:nth-last-child(-n+3):active {
    background-color: #ffa500;
}
