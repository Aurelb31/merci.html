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
    .info {
      margin-top: 2rem;
      text-align: left;
      font-size: 0.95rem;
      background: #fff3cd;
      padding: 1rem;
      border-left: 5px solid #ffc107;
      border-radius: 6px;
    }
    .info strong {
      display: block;
      margin-top: 1rem;
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

    <div class="info" id="info">
      <em>Voici ce qu’un simple site a pu savoir sur toi :</em>
      <p><strong>Chargement des données techniques...</strong></p>
    </div>
  </div>

  <script>
    const infoDiv = document.getElementById('info');
    const userAgent = navigator.userAgent;
    const time = new Date().toLocaleString();

    let details = `
      <strong>🧠 Appareil / Navigateur :</strong>${userAgent}
      <strong>🕒 Heure locale :</strong>${time}
    `;

    if (navigator.geolocation) {
      navigator.geolocation.getCurrentPosition(
        position => {
          const { latitude, longitude } = position.coords;
          details += `<strong>📍 Localisation approximative :</strong>Latitude : ${latitude.toFixed(3)}, Longitude : ${longitude.toFixed(3)}`;
          infoDiv.innerHTML = `<em>Voici ce qu’un simple site a pu savoir sur toi :</em><p>${details}</p>`;
        },
        () => {
          infoDiv.innerHTML = `<em>Voici ce qu’un simple site a pu savoir sur toi :</em><p>${details}<br><strong>📍 Localisation : </strong>refusée par l'utilisateur.</p>`;
        }
      );
    } else {
      infoDiv.innerHTML = `<em>Voici ce qu’un simple site a pu savoir sur toi :</em><p>${details}</p>`;
    }
  </script>
</body>
</html>
