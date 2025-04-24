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
      <p><em>Voici ce qu’un simple QR code aurait pu collecter sur toi :</em></p>
      <strong>📱 Appareil / Navigateur :</strong> <span id="agent">Chargement...</span>
      <strong>🕒 Heure locale :</strong> <span id="time">Chargement...</span>
      <strong>📍 Localisation :</strong> <span id="geo">en cours...</span>
    </div>
  </div>

  <script>
    // Récupération immédiate des infos connues
    document.getElementById('agent').textContent = navigator.userAgent;
    document.getElementById('time').textContent = new Date().toLocaleString();

    // Géolocalisation (bonus)
    if (navigator.geolocation) {
      navigator.geolocation.getCurrentPosition(
        position => {
          const { latitude, longitude } = position.coords;
          document.getElementById('geo').textContent = `Latitude ${latitude.toFixed(3)}, Longitude ${longitude.toFixed(3)}`;
        },
        () => {
          document.getElementById('geo').textContent = `refusée par l'utilisateur.`;
        }
      );
    } else {
      document.getElementById('geo').textContent = `non disponible.`;
    }
  </script>
</body>
</html>
