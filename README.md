<!DOCTYPE html>
<html lang="fr">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Piégé !</title>
  <style>
    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
    }

    body {
      font-family: Arial, sans-serif;
      background-color: #ff4d4d;
      color: white;
      height: 100vh;
      width: 100vw;
      display: flex;
      justify-content: center;
      align-items: center;
      text-align: center;
      animation: flashEffect 0.5s ease-out;
      overflow: hidden;
    }

    .container {
      max-width: 90%;
      width: 100%;
      background-color: rgba(255, 255, 255, 0.1);
      padding: 20px;
      border-radius: 12px;
    }

    h2 {
      font-size: 1.8rem;
      color: #fff200;
      margin-bottom: 1rem;
    }

    p {
      font-size: 1rem;
      margin-bottom: 1rem;
      line-height: 1.4;
    }

    .info-box {
      background: #fff3cd;
      color: #000;
      padding:
