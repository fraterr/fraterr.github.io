---
layout: page
title: Tools
permalink: /tools/
---

This section is dedicated to tools mainly concerning Kabbalah (QBLH).<br><br>
<b>Theosophic reduction</b>changes a number consisting of several figures into another composed of a smaller number of figures. This is accomplished by adding the digits of the number to be reduced. It is used to trace connections between Kabbalistic names and technical terms, and, according to some authors, it is a key to many puzzles in alchemical and Rosicrucian symbolism.<br> 
<b>Theosophic extension</b> is a mathematical operation that involves summing up a sequence of consecutive integers starting from 1, up to a specified integer. Sometimes called "theosophic addition". The result of this operation is known as the secret number.<br>
<b>Theosophic root</b> is the reverse operation of Theosophic extension.<br> 
<b>Articulation</b> is a method that divides a number into groups or into units (e.g. units, tens, hundreds, thousands, etc.). Its purpose is to study the occult meanings of each group in order to determine the significance of the number which is being analyzed.<br><br>


<h3>Theosophic Extension</h3>

<input type="text" id="input-number">
<button onclick="calculateTeosophicExtension()">Theosophic ext</button>
<p id="result"></p>

<h3>Theosophic Root</h3>

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