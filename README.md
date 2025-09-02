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
      flex-direction: column;
      justify-content: center;
      align-items: center;
      background: linear-gradient(135deg, red, orange, yellow, green, blue, indigo, violet);
      background-size: 400% 400%;
      animation: gradient 10s ease infinite;
      text-align: center;
    }

    h1, h2 {
      margin: 0;
      font: 900 clamp(28px, 8vw, 96px)/1.1 system-ui, -apple-system, "Segoe UI",
            Roboto, Arial, "Helvetica Neue", sans-serif;
      letter-spacing: .02em;
      background: linear-gradient(90deg, red, orange, yellow, green, blue, indigo, violet);
      background-size: 400% 400%;
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
      animation: rainbow 5s linear infinite;
    }

    h2 {
      margin-top: 40px;
      font-size: clamp(18px, 4vw, 48px);
    }

    @keyframes gradient {
      0% {background-position: 0% 50%;}
      50% {background-position: 100% 50%;}
      100% {background-position: 0% 50%;}
    }

    @keyframes rainbow {
      0% {background-position: 0%;}
      100% {background-position: 100%;}
    }
  </style>
</head>
<body>
  <h1>Arsen Lox</h1>
  <h2>Sosal?</h2>
</body>
</html>