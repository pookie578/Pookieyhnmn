<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Happy Birthday Pookie!</title>
  <style>
    body, html {
      margin: 0;
      padding: 0;
      overflow: hidden;
      font-family: 'Comic Sans MS', cursive;
    }

    #start {
      position: absolute;
      width: 100%;
      height: 100%;
      background: pink url('https://media.tenor.com/2roX3uxz_68AAAAM/cute-dance.gif') repeat;
      background-size: 200px;
      display: flex;
      justify-content: center;
      align-items: center;
      flex-direction: column;
      z-index: 10;
    }

    #notif {
      background: white;
      border-radius: 20px;
      padding: 20px 30px;
      box-shadow: 0 0 15px hotpink;
      font-size: 1.5em;
      animation: popIn 1s ease forwards;
      opacity: 0;
      position: relative;
    }

    @keyframes popIn {
      to { opacity: 1; transform: scale(1); }
    }

    .flowers {
      position: absolute;
      width: 100%;
      height: 100%;
      pointer-events: none;
      z-index: 5;
    }

    .flower {
      position: absolute;
      width: 50px;
      height: 50px;
      background: url('https://pngimg.com/uploads/flower/flower_PNG129.png') no-repeat center;
      background-size: contain;
      animation: bloom 2s ease-out;
    }

    @keyframes bloom {
      from { transform: scale(0); opacity: 0; }
      to { transform: scale(1); opacity: 1; }
    }

    #heartMsg {
      display: none;
      margin-top: 30px;
      background: pink;
      border-radius: 50%;
      padding: 30px;
      font-size: 1.2em;
      box-shadow: 0 0 20px hotpink;
      animation: popIn 1s ease forwards;
    }

    #blank {
      display: none;
      position: absolute;
      background: black;
      width: 100%;
      height: 100%;
      z-index: 8;
      justify-content: center;
      align-items: center;
      flex-direction: column;
      color: white;
    }

    button {
      padding: 10px 20px;
      font-size: 1.2em;
      border: none;
      background: hotpink;
      color: white;
      border-radius: 10px;
      cursor: pointer;
      box-shadow: 0 0 10px white;
    }

    #stars {
      display: none;
      position: absolute;
      width: 100%;
      height: 100%;
      background: #ffd1dc;
      overflow: hidden;
      z-index: 6;
    }

    .star {
      width: 5px;
      height: 5px;
      background: white;
      position: absolute;
      animation: twinkle 2s infinite;
    }

    @keyframes twinkle {
      0%, 100% { opacity: 0.5; }
      50% { opacity: 1; }
    }

    #decorate, #popText {
      display: none;
      z-index: 7;
      position: absolute;
      bottom: 50px;
      left: 50%;
      transform: translateX(-50%);
      color: hotpink;
      font-size: 1.5em;
    }

    .balloon {
      width: 60px;
      height: 80px;
      background: radial-gradient(circle at 30% 30%, #ff69b4, #ff1493);
      border-radius: 50% 50% 50% 50%;
      position: absolute;
      bottom: -100px;
      cursor: pointer;
      animation: floatUp 6s linear forwards;
    }

    @keyframes floatUp {
      to {
        bottom: 110%;
      }
    }

    .pop {
      animation: pop 0.4s forwards;
    }

    @keyframes pop {
      to {
        transform: scale(0);
        opacity: 0;
      }
    }
  </style>
</head>
<body>

<div id="start">
  <div id="notif">It’s your special dayy😋✨🌷🎀</div>
  <div class="flowers" id="flowerContainer"></div>
  <div id="heartMsg">Have a look, Kushwaha ji</div>
</div>

<div id="blank" class="centered">
  <button onclick="turnOnLight()">Open Light</button>
</div>

<div id="stars"></div>
<div id="decorate"><button onclick="releaseBalloons()">Decorate</button></div>
<div id="popText">Pop the balloons!</div>

<script>
  // Create flower animation
  setTimeout(() => {
    for (let i = 0; i < 10; i++) {
      let flower = document.createElement('div');
      flower.className = 'flower';
      flower.style.top = Math.random() * 100 + '%';
      flower.style.left = Math.random() * 100 + '%';
      document.getElementById('flowerContainer').appendChild(flower);
    }
  }, 1000);

  // Show heart text after flowers
  setTimeout(() => {
    document.getElementById('heartMsg').style.display = 'block';
  }, 2500);

  // Blank screen and light button
  setTimeout(() => {
    document.getElementById('start').style.display = 'none';
    document.getElementById('blank').style.display = 'flex';
  }, 5000);

  // Stars appear and decorate option
  function turnOnLight() {
    document.getElementById('blank').style.display = 'none';
    document.getElementById('stars').style.display = 'block';

    for (let i = 0; i < 100; i++) {
      let star = document.createElement('div');
      star.className = 'star';
      star.style.top = Math.random() * 100 + '%';
      star.style.left = Math.random() * 100 + '%';
      document.getElementById('stars').appendChild(star);
    }

    document.getElementById('decorate').style.display = 'block';
  }

  // Release balloons
  function releaseBalloons() {
    document.getElementById('decorate').style.display = 'none';
    document.getElementById('popText').style.display = 'block';
    for (let i = 0; i < 20; i++) {
      let balloon = document.createElement('div');
      balloon.className = 'balloon';
      balloon.style.left = Math.random() * 90 + '%';
      balloon.onclick = function () {
        this.classList.add('pop');
        setTimeout(() => this.remove(), 400);
      };
      document.body.appendChild(balloon);
    }
  }
</script> u
</body>
</html>
