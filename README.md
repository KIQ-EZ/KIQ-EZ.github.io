<!DOCTYPE html>
<html lang="ru">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>Arsen Lox</title>
  <style>
    html, body {
      height: 100%;
      margin: 0;
    }
    body {
      display: flex;
      align-items: center;
      justify-content: center;
      background: linear-gradient(135deg, red, orange, yellow, green, blue, indigo, violet);
      background-size: 400% 400%;
      animation: gradient 10s ease infinite;
      color: white;
      text-align: center;
      font: 700 clamp(28px, 8vw, 96px)/1.1 system-ui, -apple-system, "Segoe UI",
            Roboto, Arial, "Helvetica Neue", sans-serif;
      letter-spacing: .02em;
    }
    h1 {
      margin: 0;
      text-shadow: 0 0 10px rgba(0,0,0,0.5);
    }
    @keyframes gradient {
      0% {background-position: 0% 50%;}
      50% {background-position: 100% 50%;}
      100% {background-position: 0% 50%;}
    }
  </style>
</head>
<body>
  <h1>Arsen Lox</h1>
</body>
</html>