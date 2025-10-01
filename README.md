<!DOCTYPE html>
<html lang="pl">
<head>
  <meta charset="UTF-8">
  <title>AltHouse Gallery</title>
  <style>
    body { font-family: Arial, sans-serif; text-align: center; padding: 20px; }
    .buttons { margin-bottom: 20px; }
    button { padding: 10px 20px; margin: 5px; font-size: 16px; cursor: pointer; }
    img { width: 400px; height: auto; border: 2px solid #ccc; border-radius: 8px; }
  </style>
</head>
<body>
  <h1>Galeria Sufitów Napinanych</h1>
  <div class="buttons">
    <button onclick="showImage('red')">Czerwony sufit</button>
    <button onclick="showImage('yellow')">Żółty sufit</button>
    <button onclick="showImage('blue')">Niebieski sufit</button>
  </div>
  <div>
    <img id="ceiling" src="https://via.placeholder.com/400x250/cccccc/000000?text=Wybierz+kolor" alt="Sufit">
  </div>

  <script>
    function showImage(color) {
      const images = {
        red: "https://via.placeholder.com/400x250/ff0000/ffffff?text=Czerwony+Sufit",
        yellow: "https://via.placeholder.com/400x250/ffff00/000000?text=Żółty+Sufit",
        blue: "https://via.placeholder.com/400x250/0000ff/ffffff?text=Niebieski+Sufit"
      };
      document.getElementById("ceiling").src = images[color];
    }
  </script>
</body>
</html>
