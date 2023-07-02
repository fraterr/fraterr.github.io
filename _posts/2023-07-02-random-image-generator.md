---
layout: post
title:  "Random image generator"
categories: [tool]
description: "A random image generator to be used along with Quantum Wave Streaming and the likes"
---

This is an image generator that produces random, ever-changing images. The continuously refreshing images are intended for use with techniques like Quantum Wave Streaming that require a constantly shifting visual stimulus.

**How it works:** Every time you press the 'Generate Image' button, a new random photo is fetched from Unsplash.com. The background of the target box changes to display this fresh image. By continuously pressing the button, a flow of different pictures is produced.

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
            width: 100%;
            max-width: 1000px;
            height: 0px;
            padding-bottom: 100%;
            background-color: #e0e0e0;
            background-position: auto;
            background-repeat: no-repeat;
            background-size: cover;
            border: 5px solid #007BFF;
            border-radius: 10px;
            margin-top: 20px;
            transition: background-image 0.5s ease-out;
        }
    </style>
</head>

<body>
    <div style="display: flex; flex-direction: column; align-items: center;">
        <button id="generate-button" class="button">Generate Image</button>
        <div id="image-box"></div>
    </div>
    <script>
        document.getElementById('generate-button').addEventListener('click', () => {
            const imageBox = document.getElementById('image-box');
            fetch('https://source.unsplash.com/random')
                .then(response => {
                    imageBox.style.backgroundImage = `url(${response.url})`;
                })
                .catch(error => {
                    console.log('Error fetching the image:', error);
                });
        });
    </script>
</body>
</html>