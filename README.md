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
      background-color: #ff6666; /* Fond rouge initial */
      height: 100vh;
      text-align: center;
      padding: 20px;
      margin: 0;
      overflow: hidden;
      animation: flash 0.3s ease-out forwards; /* Flash effect */
    }

    .message {
      max-width: 500px;
      color: white;
      padding: 1rem;
      border-radius: 12px;
      box-shadow: 0 4px 12px rgba(0,0,0,0.2);
      background-color: rgba(0, 0, 0, 0.6);
      width: 100%;
      display: flex;
      flex-direction: column;
      justify-content: space
