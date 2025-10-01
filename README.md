<!DOCTYPE html>
<html lang="pl">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>AltHouse Gallery</title>
  <style>
    body { font-family: Arial, sans-serif; text-align: center; padding: 24px; }
    h1 { margin-top: 0; }
    .buttons { margin-bottom: 20px; }
    button {
      padding: 10px 20px; margin: 6px;
      font-size: 16px; cursor: pointer; border-radius: 8px;
      border: 1px solid #ccc; background: #fff;
    }
    button.red { border-color: #ff0000; }
    button.yellow { border-color: #ffd400; }
    button.blue { border-color: #3390ff; }
    img#ceiling {
      width: 420px; max-width: 95vw; height: auto;
      border: 2px solid #ccc; border-radius: 8px;
      box-shadow: 0 4px 18px rgba(0,0,0,.08);
    }
    .hint { color:#666; font-size:14px; margin-top:10px; }
  </style>
</head>
<body>

  <h1>Galeria Sufitów Napinanych</h1>

  <div class="buttons">
    <button class="red"    onclick="showImage('red')">Czerwony sufit</button>
    <button class="yellow" onclick="showImage('yellow')">Żółty sufit</button>
    <button class="blue"   onclick="showImage('blue')">Niebieski sufit</button>
  </div>

  <!-- Стартовая картинка (красный) -->
  <img id="ceiling"
       src="https://via.placeholder.com/600x360/ff0000/ffffff?text=Czerwony+sufit"
       alt="Sufit" />

  <p class="hint">Kliknij przycisk, aby zmienić kolor suﬁtu.</p>

  <script>
    // Здесь можно заменить URL на свои картинки (например, z /images/)
    const images = {
      red:    "https://via.placeholder.com/600x360/ff0000/ffffff?text=Czerwony+sufit",
      yellow: "https://via.placeholder.com/600x360/ffd400/000000?text=Żółty+sufit",
      blue:   "https://via.placeholder.com/600x360/3390ff/ffffff?text=Niebieski+sufit"
    };

    function showImage(color) {
      const el = document.getElementById("ceiling");
      el.src = images[color];
      el.alt = "Sufit - " + color;
    }
  </script>

  <noscript>Włącz JavaScript, aby korzystać z galerii.</noscript>
</body>
</html>
