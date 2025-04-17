<!DOCTYPE html>
<html lang="ru">
<head>
  <meta charset="UTF-8">
  <title>Bisultan ne natural</title>
  <style>
    body {
      margin: 0;
      height: 100vh;
      background: linear-gradient(135deg, red, orange, yellow, green, blue, indigo, violet);
      display: flex;
      justify-content: center;
      align-items: center;
      font-family: 'Comic Sans MS', cursive, sans-serif;
      animation: rainbowBG 10s infinite alternate;
    }

    h1 {
      color: white;
      font-size: 4em;
      text-shadow: 2px 2px 8px hotpink;
      animation: sparkle 1.5s infinite alternate;
    }

    @keyframes sparkle {
      0% { text-shadow: 2px 2px 5px hotpink; transform: scale(1); }
      100% { text-shadow: 4px 4px 15px deeppink; transform: scale(1.05); }
    }

    @keyframes rainbowBG {
      0% { filter: hue-rotate(0deg); }
      100% { filter: hue-rotate(360deg); }
    }
  </style>
</head>
<body>
  <h1>Bisultan ne natural</h1>
</body>
</html>
