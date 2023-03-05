---
layout: post
title:  "Theosophic operations"
---

<input type="text" id="input-number">
<button onclick="calculateTeosophicExtension()">Theosophic ext</button>
<p id="result"></p>
<input type="text" id="input">
<button id="btn">Theosophic Root</button>
<div id="output"></div>




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
