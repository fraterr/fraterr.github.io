---
layout: post
title:  "Random image generator"
categories: [tool]
description: "A random image generator to be used along with Quantum Wave Streaming and the likes"
---

This is an image generator that produces random, ever-changing images. The continuously refreshing images are intended for use with techniques like Quantum Wave Streaming that require a constantly shifting visual stimulus.

**How it works:** Every time you press the 'Generate Image' button, a new random photo is fetched from Unsplash.com. 

<html lang="it">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Generatore di immagini casuali</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #f0f0f0;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            min-height: 100vh;
            margin: 0;
        }

        .button {
            display: inline-block;
            padding: 10px 20px;
            font-size: 18px;
            cursor: pointer;
            text-align: center;
            text-decoration: none;
            outline: none;
            color: #fff;
            background-color: #007BFF;
            border: none;
            border-radius: 15px;
            box-shadow: 0 5px #0069D9;
            margin-bottom: 20px;
        }

        .button:hover {
            background-color: #0069D9
        }

        .button:active {
            background-color: #005CB2;
            box-shadow: 0 2px #005CB2;
            transform: translateY(4px);
        }

        #image-box {
            width: 80%;
            max-width: 500px;
            height: 0;
            padding-bottom: 100%;
            background-color: #e0e0e0;
            background-position: center;
            background-repeat: no-repeat;
            background-size: cover;
            border: 5px solid #007BFF;
            border-radius: 10px;
            margin-top: 20px;
            transition: background-image 0.5s ease-out, padding-bottom 0.5s ease-out;
        }

        #buttons-container {
            display: flex;
            justify-content: center;
            align-items: center;
            margin-top: 20px;
        }

        #resize-button {
            display: inline-block;
            padding: 10px 20px;
            font-size: 18px;
            cursor: pointer;
            text-align: center;
            text-decoration: none;
            outline: none;
            color: #fff;
            background-color: #007BFF;
            border: none;
            border-radius: 15px;
            box-shadow: 0 5px #0069D9;
            margin: 0 10px;
        }

        #resize-button:hover {
            background-color: #0069D9;
        }

        #resize-button:active {
            background-color: #005CB2;
            box-shadow: 0 2px #005CB2;
            transform: translateY(4px);
        }

        #increase-button {
            margin-right: 10px;
        }
    </style>
</head>

<body>
    <div style="display: flex; flex-direction: column; align-items: center;">
        <button id="generate-button" class="button">Generate Image</button>
        <div id="image-box"></div>
        <div id="buttons-container">
            <button id="increase-button" class="button" style="background-color: green;">+</button>
            <button id="decrease-button" class="button" style="background-color: red;">-</button>
        </div>
    </div>
    <script>
        const imageBox = document.getElementById('image-box');
        const generateButton = document.getElementById('generate-button');
        const increaseButton = document.getElementById('increase-button');
        const decreaseButton = document.getElementById('decrease-button');
        let paddingPercentage = 100;

        generateButton.addEventListener('click', () => {
            fetch('https://source.unsplash.com/random')
                .then(response => {
                    const img = new Image();
                    img.src = response.url;
                    img.onload = () => {
                        const aspectRatio = img.naturalWidth / img.naturalHeight;
                        paddingPercentage = 1 / aspectRatio * 100;
                        imageBox.style.paddingBottom = `${paddingPercentage}%`;
                        imageBox.style.backgroundImage = `url(${response.url})`;
                    };
                })
                .catch(error => {
                    console.log('Error fetching the image:', error);
                });
        });

        increaseButton.addEventListener('click', () => {
            paddingPercentage += 10;
            imageBox.style.paddingBottom = `${paddingPercentage}%`;
        });

        decreaseButton.addEventListener('click', () => {
            paddingPercentage -= 10;
            imageBox.style.paddingBottom = `${paddingPercentage}%`;
        });
    </script>
</body>
</html>