<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Sorry Mashhuda</title>
  <style>
    body {
      margin: 0;
      padding: 0;
      background: linear-gradient(135deg, #ff9a9e, #fad0c4);
      font-family: 'Arial', sans-serif;
      overflow: hidden;
      display: flex;
      justify-content: center;
      align-items: center;
      flex-direction: column;
      height: 100vh;
    }
    h1 {
      font-size: 2rem;
      color: #fff;
      margin-bottom: 1rem;
      text-align: center;
      text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.3);
    }
    .sorry-container {
      position: relative;
      width: 100%;
      height: 100%;
    }
    .sorry {
      position: absolute;
      font-size: 2rem;
      font-weight: bold;
      color: rgba(255, 0, 0, 0.8);
      animation: fade 1.5s infinite ease-in-out;
    }
    @keyframes fade {
      0% {
        opacity: 0;
        transform: translateY(20px);
      }
      50% {
        opacity: 1;
        transform: translateY(0);
      }
      100% {
        opacity: 0;
        transform: translateY(-20px);
      }
    }

    /* Heart Animation */
    .heart {
      position: absolute;
      width: 20px;
      height: 20px;
      background: #ff6b6b;
      transform: rotate(45deg);
      animation: float 3s infinite ease-in-out;
    }
    .heart::before,
    .heart::after {
      content: '';
      width: 20px;
      height: 20px;
      background: #ff6b6b;
      border-radius: 50%;
      position: absolute;
    }
    .heart::before {
      top: -10px;
      left: 0;
    }
    .heart::after {
      left: 10px;
      top: 0;
    }
    @keyframes float {
      0% {
        transform: translateY(0) rotate(45deg);
        opacity: 1;
      }
      50% {
        opacity: 0.7;
      }
      100% {
        transform: translateY(-100vh) rotate(45deg);
        opacity: 0;
      }
    }
  </style>
</head>
<body>
  <h1>I'm Sorry, Mashhuda</h1>
  <div class="sorry-container" id="sorryContainer"></div>

  <script>
    // Function to create "Sorry" text animations
    function createSorry() {
      const container = document.getElementById('sorryContainer');
      const sorry = document.createElement('div');
      sorry.className = 'sorry';
      sorry.textContent = 'Sorry';
      sorry.style.left = `${Math.random() * 90}vw`; // Random horizontal position
      sorry.style.top = `${Math.random() * 90}vh`; // Random vertical position
      container.appendChild(sorry);

      // Remove the "Sorry" after its animation ends
      setTimeout(() => {
        sorry.remove();
      }, 1500);
    }

    // Function to create floating hearts
    function createHeart() {
      const heart = document.createElement('div');
      heart.className = 'heart';
      heart.style.left = `${Math.random() * 100}vw`; // Random horizontal position
      heart.style.animationDuration = `${Math.random() * 1.5 + 1.5}s`; // Faster floating duration
      document.body.appendChild(heart);

      // Remove the heart after its animation ends
      setTimeout(() => {
        heart.remove();
      }, 3000);
    }

    // Create "Sorry" text and hearts continuously
    setInterval(createSorry, 200); // New "Sorry" every 200ms
    setInterval(createHeart, 150); // New heart every 150ms
  </script>
</body>
</html>
