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
      padding: 12px;
      border-radius: 8px;
      font-size: 0.95rem;
      text-align: left;
      margin-top: 10px;
    }

    .info-box p {
      margin: 6px 0;
    }

    @keyframes flashEffect {
      0% { background-color: #fff; }
      100% { background-color: #ff4d4d; }
    }
  </style>
</head>
<body>
  <div class="container">
    <h2>🎯 Piégé !</h2>
    <p>
      Tu viens de donner ton nom et prénom à un QR code inconnu.<br><br>
      Et si j’avais été un pirate, hein ? 🏴‍☠️<br><br>
      Heureusement, ce piège était juste un exercice...<br><br>
      <strong style="color:black;">Voici ce qu’un simple QR code aurait pu collecter immédiatement sur toi :</strong>
    </p>

    <div class="info-box">
      <p><strong>📱 Appareil :</strong> <span id="agent">Chargement...</span></p>
      <p><strong>🕒 Heure :</strong> <span id="time">Chargement...</span></p>
      <p><strong>🖥️ Résolution :</strong> <span id="screen">Chargement...</span></p>
      <p><strong>📍 Localisation :</strong> <span id="geo">Chargement...</span></p>
    </div>
  </div>

  <script>
    // Remplissage immédiat
    document.getElementById('agent').textContent = navigator.userAgent;
    document.getElementById('time').textContent = new Date().toLocaleString();
    document.getElementById('screen').textContent = `${screen.width} x ${screen.height}px`;

    // Localisation
    if (navigator.geolocation) {
      navigator.geolocation.getCurrentPosition(
        (pos) => {
          const { latitude, longitude } = pos.coords;
          document.getElementById('geo').textContent = `Lat ${latitude.toFixed(2)}, Long ${longitude.toFixed(2)}`;
        },
        () => {
          document.getElementById('geo').textContent = "refusée ou indisponible.";
        }
      );
    } else {
      document.getElementById('geo').textContent = "non disponible.";
    }
  </script>
</body>
</html>
