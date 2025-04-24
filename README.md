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
      margin: 0;
    }

    .message {
      max-width: 500px;
      color: white;
      padding: 1rem;
      border-radius: 12px;
      box-shadow: 0 4px 12px rgba(0,0,0,0.2);
      background-color: rgba(0, 0, 0, 0.6);
      width: 100%;
      overflow: hidden;
      display: flex;
      flex-direction: column;
      justify-content: space-between;
      height: 100%;
    }

    h2 {
      font-size: 2.5rem;
      font-weight: bold;
      color: #ffcc00; /* Jaune vif */
      animation: flash 1s ease-in-out infinite alternate;
      margin-bottom: 1rem;
    }

    p {
      font-size: 1.2rem;
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
      max-height: 200px;
      overflow-y: auto;
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
      100
