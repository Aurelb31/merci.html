<!DOCTYPE html>
<html lang="fr">
<head>
  <meta charset="UTF-8">
  <title>Piégé !</title>
  <style>
    body {
      margin: 0;
      padding: 0;
      font-family: Arial, sans-serif;
      background-color: #ff6666;
      animation: flashPage 0.5s ease-out;
      color: white;
    }

    .container {
      max-width: 600px;
      margin: 50px auto;
      padding: 30px;
      background-color: rgba(255, 255, 255, 0.1);
      border-radius: 10px;
      text-align: center;
    }

    h2 {
      font-size: 2em;
      color: #fff200;
    }

    .info-box {
      background: #fff3cd;
      color: #000;
      margin-top: 20px;
      padding: 15px;
      border-radius: 8px;
      text-align: left;
    }

    .info-box p {
      margin: 10px 0;
    }

    @keyframes flashPage {
      0% { background-color: white; }
      100% { background-color: #ff6666; }
    }
  </style>
</head>
<body>
  <div class="container">
    <h2>🎯 Piégé !</h2>
    <p>Tu viens de donner ton nom et prénom à un QR code inconnu.<br><br>
    Et si j’avais été un pirate, hein ? 🏴‍☠️<br><br>
    Heureusement, ce piège était juste un exercice...<br>
    <strong>Voici ce qu’un simple QR code aurait pu collecter immédiatement sur toi :</strong></p>

    <div class="info-box">
      <p><strong>📱 Appareil :</strong> <span id="agent">Chargement...</span></p>
      <p><strong>🕒 Heure :</strong> <span id="time">Chargement...</span></p>
      <p><strong>🖥️ Résolution :</strong> <span id="screen">Chargement...</span></p>
      <p><strong>📍 Localisation :</strong> <span id="geo">Chargement...</span></p>
    </div>
  </div>

  <script>
    // Données de base
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
