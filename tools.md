---
layout: page
title: Tools
permalink: /tools/
---

This section is dedicated to tools mainly concerning Kabbalah (QBLH).<br><br>
<b>Theosophic reduction</b> changes a number consisting of several figures into another composed of a smaller number of figures. This is accomplished by adding the digits of the number to be reduced. It is used to trace connections between Kabbalistic names and technical terms, and, according to some authors, it is a key to many puzzles in alchemical and Rosicrucian symbolism.<br><br> 
<b>Theosophic extension</b> is a mathematical operation that involves summing up a sequence of consecutive integers starting from 1, up to a specified integer. Sometimes called "theosophic addition". The result of this operation is known as the secret number.<br><br>
<b>Theosophic root</b> is the reverse operation of Theosophic extension.<br><br> 
<b>Articulation</b> is a method that divides a number into groups or into units (e.g. units, tens, hundreds, thousands, etc.). Its purpose is to study the occult meanings of each group in order to determine the significance of the number which is being analyzed.<br><br>
<b>Cabala Simplex Latina</b> is a Latin-based system of numerology that assigns numerical values to letters in the Latin alphabet, with each letter corresponding to a specific number.<br><br>


<h3>Theosophic Extension</h3>
<label for="input-text">Input a number:</label>
<input type="text" id="input-number">
<button onclick="calculateTeosophicExtension()">Theosophic ext</button>
<p id="result"></p>

<h3>Theosophic Root</h3>
<label for="input-text">Input a number:</label>
<input type="text" id="input">
<button id="btn">Theosophic Root</button>
<div id="output"></div>


<script>
function calculateTeosophicExtension() {
  var inputNumber = document.getElementById("input-number").value; // Recupera il valore inserito nella casella di testo
  var teosophicSum = 0;
  for (var i = 1; i <= inputNumber; i++) {
    teosophicSum += i;
  }
  document.getElementById("result").innerHTML = "The theosophic extension of " + inputNumber + " is " + teosophicSum;
}
function calculateTeosophicNumber(number) {
  let sum = 0;
  
  for (let i = 1; i <= number; i++) {
    sum += i;
    
    if (sum === number) {
      return i;
    }
  }
  
  return null; // se non viene trovato alcun numero, restituisce null
}

document.getElementById("btn").addEventListener("click", function() {
  let input = document.getElementById("input").value;
  let result = calculateTeosophicNumber(parseInt(input));
  
  if (result !== null) {
    document.getElementById("output").innerHTML = "The theosophic root of " + input + " is " + result;
  } else {
    document.getElementById("output").innerHTML = "The number " + input + " is not a theosophic extension";
  }
});
</script>

<h3>Gematria database</h3>
Input a number to find out hebrew words correspondences




<html>
<head>
	<title>Number Divider</title>
	<meta charset="UTF-8">
	<meta name="viewport" content="width=device-width, initial-scale=1.0">
  <h3>Articulation</h3>
	</head>
<body>
	<label for="input-text">Input a number:</label>
	<input type="text" id="number-input">
	<button id="calculate-button">Calculate</button>
	<p id="output1"></p>

	<script src="script.js"></script>
</body>
</html>

<script>


// Get the necessary elements from the DOM
const numberInput = document.getElementById("number-input");
const calculateButton = document.getElementById("calculate-button");
const outputElement = document.getElementById("output1");

// Add an event listener to the button
calculateButton.addEventListener("click", function() {
    // Get the input value and convert it to a number
    let inputValue = Number(numberInput.value);

    // Divide the number into units
    const units = [1000000000000, 100000000000, 10000000000, 1000000000, 100000000, 10000000, 10000000, 1000000, 100000, 10000, 1000, 100, 10, 1];
    let result = "";
    let foundNonZero = false;
    for (let i = 0; i < units.length; i++) {
        const unitValue = Math.floor(inputValue / units[i]);
        if (unitValue > 0 || foundNonZero) {
            foundNonZero = true;
            result += unitValue * units[i] + ";";
        }
        inputValue -= unitValue * units[i];
    }

    // Display the output
    if (!foundNonZero) {
        outputElement.textContent = inputValue;
    } else {
        outputElement.textContent = result.slice(0, -1); // Remove the last semicolon
    }
});
</script>

<html>

<body>
	<h3>Cabala Simplex Latina</h3>
	<label for="input-text">Input word or sentence:</label>
	<input type="text" id="input-text">
	<button onclick="calculate()">Calculate</button>
	<p id="output"></p>

	
</body>
</html>

<script>

		function calculate() {
			// Get the input text
			const inputText = document.getElementById("input-text").value.toUpperCase();

			// Map each letter to its corresponding number value
			const letterValues = {
				"A": 1,
				"B": 2,
				"C": 3,
				"D": 4,
				"E": 5,
				"F": 6,
				"G": 7,
				"H": 8,
				"I": 9,
				"L": 10,
				"M": 11,
				"N": 12,
				"O": 13,
				"P": 14,
				"Q": 15,
				"R": 16,
				"S": 17,
				"T": 18,
				"U": 19,
				"V": 20,
				"Z": 21
			};

			// Calculate the sum of the letter values
			let sum = 0;
			for (let i = 0; i < inputText.length; i++) {
				const letter = inputText.charAt(i);
				if (letter in letterValues) {
					sum += letterValues[letter];
				}
			}

			// Output the result
			document.getElementById("output").innerHTML = "Result: " + sum;
		}
</script>