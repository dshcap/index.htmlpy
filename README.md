<!doctype html>
<html lang="pl">
<head>
  <meta charset="utf-8" />
  <title>AltHouse – Galeria (test 3 kolory)</title>
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <style>
    body{margin:0;font-family:system-ui,Arial,sans-serif;background:#f7f8fb;color:#222}
    .wrap{max-width:960px;margin:0 auto;padding:24px}
    h1{margin:0 0 12px;font-size:26px}
    .viewer{background:#fff;border:1px solid #e6e9f2;border-radius:14px;box-shadow:0 6px 18px rgba(0,0,0,.05);padding:16px}
    .img{width:100%;height:clamp(220px,48vw,520px);object-fit:cover;border-radius:10px;border:1px solid #dfe3ef;background:#fff}
    .buttons{display:flex;gap:10px;margin-top:14px;flex-wrap:wrap}
    .btn{
      border:1px solid #cfd6e6;border-radius:999px;padding:10px 14px;
      font-weight:600;color:#fff;cursor:pointer;user-select:none;
      box-shadow:0 2px 8px rgba(0,0,0,.05);transition:.15s
    }
    .btn:hover{transform:translateY(-1px)}
    .btn.is-active{outline:2px solid rgba(0,0,0,.15)}
    .caption{margin-top:8px;color:#58607a;font-size:14px}
  </style>
</head>
<body>
  <div class="wrap">
    <h1>Galeria Sufitów — test (3 kolory)</h1>

    <div class="viewer">
      <img id="photo" class="img" alt="Sufit napinany" />
      <div class="buttons" id="buttons"></div>
      <div class="caption" id="caption"></div>
    </div>
  </div>

  <script>
    // Три образца
    const items = [
      {
        id: 'g110',
        label: 'G110',
        file: '500 G 110 Light Blue.png',
        // светло-голубой
        color: '#86C5FF'
      },
      {
        id: 'g156',
        label: 'G156',
        file: '500 G 156 Blue.png',
        // средний синий
        color: '#4DA3FF'
      },
      {
        id: 'g160',
        label: 'G160',
        file: '500 G 160 Blue.png',
        // более глубокий синий
        color: '#2D7FFF'
      }
    ];

    const $img = document.getElementById('photo');
    const $cap = document.getElementById('caption');
    const $btns = document.getElementById('buttons');

    function activate(id){
      document.querySelectorAll('.btn').forEach(b => {
        b.classList.toggle('is-active', b.dataset.id === id);
      });
    }

    function show(id){
      const it = items.find(x => x.id === id) || items[0];
      // Файлы лежат в корне репозитория — путь просто относительный
      $img.src = it.file;
      $img.alt = Sufit — ${it.label};
      $cap.textContent = Kolor: ${it.label};
      activate(id);
    }

    // Рисуем кнопки
    items.forEach(it => {
      const b = document.createElement('button');
      b.className = 'btn';
      b.dataset.id = it.id;
      b.textContent = it.label;
      b.style.background = it.color;
      b.onclick = () => show(it.id);
      $btns.appendChild(b);
    });

    // Первый показ
    show(items[0].id);
  </script>
</body>
</html>
