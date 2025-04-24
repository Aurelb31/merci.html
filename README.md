<!DOCTYPE html>
<html lang="fr">
<head>
  <meta charset="UTF-8">
  <title>Ahah !</title>
  <style>
    * {
      box-sizing: border-box;
    }

    body {
      font-family: 'Arial', sans-serif;
      background-color: #ff6666;
      margin: 0;
      padding: 0;
      height: 100vh;
      overflow: auto;
      animation: flashPage 0.5s ease-out, shake 0.5s ease-in-out;
    }

    .message {
      max-width: 600px;
      margin: 0 auto;
      padding: 40px 20px;
      color: white;
      text-align: center;
    }

    h2 {
      font-size: 2.5rem;
      font-weight: bold;
      color: #ffcc00;
    }

    p {
      font-size: 1.2rem;
      margin-top: 1rem;
    }

    .info-box {
      margin-top: 2rem;
      background: #fff3cd;
      color: #333;
      padding: 1rem 1.5rem;
      border-left: 5px solid #ffc107;
      border-radius: 6px;
      font-size: 1.1rem;
      text-align: left;
    }

    .info-box p {
      margin: 0.5rem 0;
    }

    @keyframes flashPage {
      0% { background-color: #ffffff; }
      100% { background-color: #ff6666; }
    }

    @keyframes shake {
      0% { transform: translate(0, 0); }
      20% { transform: translate(-2px, 2px); }
      40% { transform: translate(2px
