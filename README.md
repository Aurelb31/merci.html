<!DOCTYPE html>
<html lang="fr">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Piégé !</title>
  <style>
    * {
      box-sizing: border-box;
    }

    body {
      margin: 0;
      padding: 0;
      font-family: Arial, sans-serif;
      background-color: #ff6666;
      color: white;
      display: flex;
      align-items: center;
      justify-content: center;
      min-height: 100vh;
      animation: flashPage 0.5s ease-out;
    }

    .container {
      max-width: 95%;
      width: 100%;
      max-width: 500px;
      background-color: rgba(255, 255, 255, 0.08);
      padding: 20px;
      border-radius: 12px;
      box-shadow: 0 0 12px rgba(0, 0, 0, 0.2);
      text-align: center;
    }

    h2 {
      font-size: 2rem;
      margin-bottom: 1rem;
      color: #fff200;
    }

    p {
      font-size: 1.1rem;
      line-height: 1.5;
    }

    .info-box {
      background: #fff3cd;
      color: #000;
