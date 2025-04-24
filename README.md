<!DOCTYPE html>
<html lang="fr">
<head>
  <meta charset="UTF-8">
  <title>Ahah !</title>
  <style>
    body {
      font-family: sans-serif;
      display: flex;
      justify-content: center;
      align-items: center;
      background-color: #fefae0;
      height: 100vh;
      text-align: center;
      padding: 20px;
    }
    .message {
      max-width: 500px;
    }
    h2 {
      font-size: 2rem;
    }
    p {
      font-size: 1.1rem;
      margin-top: 1rem;
    }
    .info-box {
      margin-top: 2rem;
      text-align: left;
      background: #fff3cd;
      padding: 1rem 1.5rem;
      border-left: 5px solid #ffc107;
      border-radius: 6px;
      font-size: 0.95rem;
      color: #333;
    }
    .info-box strong {
      display: block;
      margin-top: 1rem;
    }
    .loading {
      font-style: italic;
      color: #888;
    }
  </style>
</head>
<body>
  <div class="message">
    <h2>🎯 Piégé !</h2>
    <p>Tu viens de donner ton nom et prénom à un QR code inconnu.<br><br>
    Et si j’avais été un pirate, hein ? 🏴‍☠️<br><br>
    Heureusement, ce piège était juste un exercice... mais tu viens de faire perdre 10 points à ton équipe 😬<br>
    <strong>Moralité : méfie-toi toujours des QR codes sauvages !</strong></p>

    <div class="info-box" id="info-box">
      <p class="loading">⏳ Récupération des informations techniques...</p>
    </div>
  </div>

  <script>
    const box = document.getElementById('info-box');
    const userAgent = navigator.userAgent;
    const time = new Date().toLocaleString();

    let infoHTML = `
      <em>Voici ce qu’un simple QR code aurait pu collecter sur toi :</em>
      <strong>📱 Appareil / Navigateur :</strong> ${userAgent}
      <strong>🕒
