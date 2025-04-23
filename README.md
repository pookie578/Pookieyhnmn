<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Happy Birthday Kushwaha Ji</title>
  <style>
    body {
      margin: 0;
      padding: 0;
      overflow: hidden;
      background-color: #ffccf5;
      font-family: 'Arial', sans-serif;
    }

    /* Hamster Animation */
    .hamster {
      position: absolute;
      animation: hamster-move 10s infinite;
    }

    @keyframes hamster-move {
      0% { top: 10%; left: 5%; }
      25% { top: 40%; left: 50%; }
      50% { top: 70%; left: 80%; }
      75% { top: 20%; left: 30%; }
      100% { top: 10%; left: 5%; }
    }

    /* Pop-up Birthday Text */
    .pop-up-text {
      font-size: 36px;
      font-weight: bold;
      color: #ff4d7f;
      position: absolute;
      top: 10%;
      left: 50%;
      transform: translateX(-50%);
      animation: text-appear 3s ease-in-out;
      text-shadow: 2px 2px 10px rgba(255, 255, 255, 0.8);
    }

    @keyframes text-appear {
      0% { opacity: 0; }
      100% { opacity: 1; }
    }

    /* Love Notes */
    .love-note {
      position: fixed;
      top: 80%;
      left: 50%;
      font-size: 22px;
      color: pink;
      transform: translateX(-50%);
      animation: float-notes 10s infinite;
      text-shadow: 1px 1px 10px rgba(255, 255, 255, 0.8);
    }

    @keyframes float-notes {
      0% { transform: translateX(-50%) translateY(0); }
      100% { transform: translateX(-50%) translateY(-100px); }
    }

    /* Floating Hearts Effect */
    .heart {
      position: absolute;
      font-size: 30px;
      animation: heart-float 3s infinite;
    }

    @keyframes heart-float {
      0% { transform: translateY(0); opacity: 1; }
      50% { transform: translateY(-50px); opacity: 0.7; }
      100% { transform: translateY(0); opacity: 1; }
    }

    /* Birthday Cake Flicker */
    .cake {
      width: 250px;
      height: 250px;
      position: absolute;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -50%);
      animation: cake-flicker 2s infinite;
    }

    @keyframes cake-flicker {
      0% { opacity: 1; }
      50% { opacity: 0.7; }
      100% { opacity: 1; }
    }

    /* Button Styles */
    button {
      background-color: #ff80bf;
      color: white;
      padding: 10px 20px;
      border: none;
      border-radius: 20px;
      cursor: pointer;
      font-size: 18px;
      transition: all 0.3s ease;
    }

    button:hover {
      background-color: #ff4d7f;
      transform: scale(1.1);
    }

    /* Balloon Styling */
    .balloon {
      position: absolute;
      cursor: pointer;
      font-size: 40px;
      transition: transform 0.3s ease;
    }

    .balloon:hover {
      transform: scale(1.2);
    }

    /* Sparkle effect */
    .sparkles {
      position: absolute;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      background: url('https://media.giphy.com/media/5WzX4glj9hbsM/giphy.gif') repeat;
      animation: sparkle 2s infinite;
    }

    @keyframes sparkle {
      0% { opacity: 0.5; }
      50% { opacity: 1; }
      100% { opacity: 0.5; }
    }
  </style>
</head>
<body>
  <!-- Pookie Hamsters -->
  <img src="https://media.giphy.com/media/Ns0uVbLx3hXAc/giphy.gif" class="hamster" style="animation-duration: 5s;">
  <img src="https://media.giphy.com/media/3o6Zt481isNVuQI1l6/giphy.gif" class="hamster" style="animation-duration: 7s;">
  <img src="https://media.giphy.com/media/3o6Zt6ML6BklcajjsA/giphy.gif" class="hamster" style="animation-duration: 6s;">
  
  <!-- Floating Hearts -->
  <div class="heart" style="top: 10%; left: 30%;">💖</div>
  <div class="heart" style="top: 20%; left: 70%;">💗</div>
  <div class="heart" style="top: 30%; left: 50%;">💝</div>

  <!-- Birthday Text Pop-up -->
  <div class="pop-up-text">It's your special dayy 😋✨🌷🎀</div>

  <!-- Love Notes -->
  <div class="love-note">For more years with you🎀💗🌷</div>
  <div class="love-note" style="animation-delay: 2s;">Mera pyara sa kuchupuchu</div>
  <div class="love-note" style="animation-delay: 4s;">You make me feel lucky yayaya, 🎀</div>
  <div class="love-note" style="animation-delay: 6s;">Lub lub lub you my adarniya balak💗😋</div>

  <!-- Birthday Cake -->
  <img src="https://media.giphy.com/media/98MaHVwJOmWMz4cz1K/giphy.gif" class="cake">

  <!-- Buttons for Light and Balloons -->
  <button id="open-light">Open Light</button>
  <button id="decorate">Decorate with Balloons</button>
  
  <!-- Balloon Container -->
  <div id="balloon-container" style="display:none;"></div>
  
  <!-- Sparkle effect -->
  <div class="sparkles"></div>

  <script>
    document.getElementById('open-light').onclick = function() {
      document.body.style.backgroundColor = '#ffffff';
    };
    
    document.getElementById('decorate').onclick = function() {
      let balloons = ['🎈', '🎈', '🎈', '🎈'];
      let balloonContainer = document.getElementById('balloon-container');
      balloonContainer.innerHTML = '';
      balloons.forEach((balloon, index) => {
        let balloonElement = document.createElement('div');
        balloonElement.textContent = balloon;
        balloonElement.className = 'balloon';
        balloonElement.style.left = `${(Math.random() * 90)}%`;
        balloonElement.style.top = `${(Math.random() * 80)}%`;
        balloonContainer.appendChild(balloonElement);
        balloonElement.onclick = () => alert('BOOP! POP!');
      });
      balloonContainer.style.display = 'block';
    };
  </script>
</body>
</html>