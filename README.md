 <!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Para Kai ✨</title>
  <style>
    * {
      box-sizing: border-box;
      font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
    }
    body {
      background: linear-gradient(135deg, #0f172a, #1e1b4b, #311042);
      color: #f8fafc;
      display: flex;
      justify-content: center;
      align-items: center;
      min-height: 100vh;
      margin: 0;
      padding: 20px;
    }
    .card {
      background: rgba(255, 255, 255, 0.07);
      backdrop-filter: blur(16px);
      border: 1px solid rgba(255, 255, 255, 0.15);
      padding: 30px;
      border-radius: 24px;
      max-width: 450px;
      width: 100%;
      text-align: center;
      box-shadow: 0 20px 40px rgba(0,0,0,0.4);
      animation: fadeIn 0.6s ease-out;
    }
    h1 { color: #a855f7; font-size: 1.8rem; margin-bottom: 10px; }
    p { font-size: 1.05rem; line-height: 1.6; color: #cbd5e1; }
    .btn {
      background: linear-gradient(90deg, #8b5cf6, #ec4899);
      color: white;
      border: none;
      padding: 12px 24px;
      border-radius: 12px;
      font-size: 1rem;
      font-weight: bold;
      cursor: pointer;
      margin-top: 15px;
      transition: transform 0.2s, box-shadow 0.2s;
      width: 100%;
    }
    .btn:hover {
      transform: translateY(-2px);
      box-shadow: 0 8px 20px rgba(236, 72, 153, 0.4);
    }
    .secret-box {
      background: rgba(255,255,255,0.05);
      border: 1px dashed #a855f7;
      padding: 12px;
      margin: 12px 0;
      border-radius: 10px;
      cursor: pointer;
      transition: background 0.3s;
    }
    .secret-box:hover { background: rgba(168, 85, 247, 0.15); }
    .hidden { display: none; }
    @keyframes fadeIn { from { opacity: 0; transform: translateY(10px); } to { opacity: 1; transform: translateY(0); } }
  </style>
</head>
<body>

  <!-- PANTALLA 1 -->
  <div id="step1" class="card">
    <h1>Hola, Kai ✨</h1>
    <p>Hay un mensaje guardado aquí para ti, pero está protegido bajo cierto nivel de misterio...</p>
    <button class="btn" onclick="nextStep(1, 2)">Abrir mensaje 🔓</button>
  </div>

  <!-- PANTALLA 2 -->
  <div id="step2" class="card hidden">
    <h1>Test de Curiosidad 🕵️‍♀️</h1>
    <p>Antes de continuar... del 1 al 10, ¿qué tan curiosa te consideras en este momento?</p>
    <button class="btn" onclick="nextStep(2, 3)">10/10 (Necesito saber) 🧐</button>
    <button class="btn" style="background: #334155;" onclick="nextStep(2, 3)">100/10 (Dimelo ya) 🔥</button>
  </div>

  <!-- PANTALLA 3 -->
  <div id="step3" class="card hidden">
    <h1>Toca para revelar 🤫</h1>
    <p>Haz clic en cada casilla para desbloquear las pistas:</p>
    
    <div class="secret-box" onclick="toggleSecret('s1')">
      <strong>✨ Razón #1 de esta carta</strong>
      <p id="s1" class="hidden">Porque me pareció una excelente forma de sacarte una sonrisa hoy.</p>
    </div>

    <div class="secret-box" onclick="toggleSecret('s2')">
      <strong>✨ Razón #2</strong>
      <p id="s2" class="hidden">Porque hablar contigo siempre le sube el nivel al día.</p>
    </div>

    <div class="secret-box" onclick="toggleSecret('s3')">
      <strong>✨ Un secreto sutil</strong>
      <p id="s3" class="hidden">Pondría una confesión aquí... pero prefiero dejarte con la duda un tiempo más. 😼</p>
    </div>

    <button class="btn" onclick="nextStep(3, 4)">Continuar ➔</button>
  </div>

  <!-- PANTALLA 4 -->
  <div id="step4" class="card hidden">
    <h1>En resumen, Kai... ❤️‍🔥</h1>
    <p>Eres una persona increíblemente especial y me encanta tenerte cerca. Ahora la pregunta es...</p>
    <p><strong>¿Qué hacemos con este misterio?</strong></p>
    
    <button class="btn" onclick="alert('¡Trato hecho! Pongo el café/salida y tú pones la conversación 😉')">Me debes una explicación ☕</button>
    <button class="btn" style="background: #334155; margin-top: 10px;" onclick="alert('El misterio continúa... pero no por mucho tiempo ⏱️')">Dejarlo en misterio 🤫</button>
  </div>

  <script>
    function nextStep(current, next) {
      document.getElementById('step' + current).classList.add('hidden');
      document.getElementById('step' + next).classList.remove('hidden');
    }
    function toggleSecret(id) {
      const el = document.getElementById(id);
      el.classList.toggle('hidden');
    }
  </script>
</body>
</html>
