<!DOCTYPE html>
<html lang="fr">
<head>
  <meta charset="UTF-8">
  <title>Ahah !</title>
  <style>
    body {
      font-family: 'Arial', sans-serif;
      display: flex;
      justify-content: center;
      align-items: center;
      background-color: #ff6666; /* Fond rouge */
      height: 100vh;
      text-align: center;
      padding: 20px;
      animation: shake 1s ease-in-out infinite; /* Animation de secousse */
    }

    .message {
      max-width: 500px;
      color: white;
      padding: 1rem;
      border-radius: 12px;
      box-shadow: 0 4px 12px rgba(0,0,0,0.2);
      background-color: rgba(0, 0, 0, 0.6);
    }

    h2 {
      font-size: 3rem;
      font-weight: bold;
      color: #ffcc00; /* Jaune vif */
      animation: flash 1s ease-in-out infinite alternate;
    }

    p {
      font-size: 1.3rem;
      margin-top: 1rem;
      color: #fff;
    }

    .info-box {
      margin-top: 2rem;
      text-align: left;
      background: #fff3cd;
      padding: 1rem 1.5rem;
      border-left: 5px solid #ffc107;
      border-radius: 6px;
      font-size: 1.1rem;
      color: #333;
      animation: fadeIn 2s ease-in-out;
    }

    .info-box strong {
      display: block;
      margin-top: 1rem;
    }

    .loading {
      font-style: italic;
      color: #888;
    }

    /* Animation de secousse */
    @keyframes shake {
      0% { transform: rotate(0deg); }
      25% { transform: rotate(-5deg); }
      50% { transform: rotate(5deg); }
      75% { transform: rotate(-5deg); }
      100% { transform: rotate(0deg); }
    }

    /* Flash effect sur le titre */
    @keyframes flash {
      0% { color: #ffcc00; }
      50% { color: #ff0000; }
      100% { color: #ffcc00; }
    }

    /* Effet de fade-in pour le box */
    @keyframes fadeIn {
      0% { opacity: 0; }
      100% { opacity: 1; }
    }

    /* Arrêt de l'animation de secousse après 5 secondes */
    @keyframes stopShake {
      0% { transform: rotate(0deg); }
      100% { transform: rotate(0deg); }
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
      <strong>🌍 Adresse IP :</strong> <span id="ip">en cours...</span>
      <strong>🖥️ Résolution de l'écran :</strong> <span id="screen">Chargement...</span>
    </div>
  </div>

  <script>
    // Récupération immédiate des infos connues
    document.getElementById('agent').textContent = navigator.userAgent;
    document.getElementById('time').textContent = new Date().toLocaleString();

    // Propriétés de l'écran
    document.getElementById('screen').textContent = `Largeur: ${window.screen.width}px, Hauteur: ${window.screen.height}px (Fenêtre: ${window.innerWidth}x${window.innerHeight}px)`;

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

    // Récupération de l'IP via ipinfo.io
    fetch('https://ipinfo.io/json?token=YOUR_API_TOKEN')  // Remplace "YOUR_API_TOKEN" par ton token ipinfo.io
      .then(response => response.json())
      .then(data => {
        document.getElementById('ip').textContent = data.ip || 'Non disponible';
      })
      .catch(() => {
        document.getElementById('ip').textContent = 'Impossible de récupérer l\'IP';
      });

    // Arrêter l'animation de secousse après 5 secondes
    setTimeout(() => {
      document.body.style.animation = 'stopShake 1s ease-in-out';
