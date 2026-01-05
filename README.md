<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Página larga con estilo diferente</title>
  <style>
    body {
      margin: 0;
      font-family: "Segoe UI", Tahoma, sans-serif;
      background: #f9fafb;
      color: #1f2937;
      line-height: 1.6;
    }
    header {
      padding: 2rem;
      text-align: center;
      background: #3b82f6;
      color: white;
      box-shadow: 0 2px 6px rgba(0,0,0,0.2);
    }
    .bloque {
      margin: 2rem auto;
      max-width: 700px;
      padding: 1.5rem;
      border-radius: 12px;
      background: white;
      box-shadow: 0 4px 12px rgba(0,0,0,0.1);
    }
    .bloque h2 {
      color: #2563eb;
    }
    .spacer {
      height: 400vh; /* espacio largo para scroll */
      background: linear-gradient(180deg, #f9fafb, #e0f2fe);
      margin: 2rem 0;
    }
    footer {
      max-width: 700px;
      margin: 0 auto;
      padding: 3rem 1rem;
      text-align: center;
      border-top: 2px solid #93c5fd;
    }
    button {
      padding: 1rem 1.5rem;
      border: none;
      border-radius: 8px;
      background: #10b981;
      color: white;
      font-weight: bold;
      cursor: pointer;
      box-shadow: 0 6px 16px rgba(16,185,129,0.3);
      transition: transform 0.2s ease, background 0.2s ease;
    }
    button:disabled {
      background: #9ca3af;
      cursor: not-allowed;
      box-shadow: none;
    }
    button:hover:enabled { transform: scale(1.05); background: #059669; }
    button:active:enabled { transform: scale(0.95); }
  </style>
</head>
<body>
  <header>
    <h1>Página con estilo renovado</h1>
    <p>Desplázate mucho para encontrar el botón.</p>
  </header>

  <div class="bloque">
    <h2>Bloque 1</h2>
    <p>Texto de prueba para alargar la página.</p>
  </div>

  <div class="bloque">
    <h2>Bloque 2</h2>
    <p>Más texto de prueba para que el scroll sea largo.</p>
  </div>

  <div class="bloque">
    <h2>Bloque 3</h2>
    <p>Contenido adicional para extender la página.</p>
  </div>

  <div class="spacer"></div>

  <div class="bloque">
    <h2>Último bloque</h2>
    <p>Ya casi llegas al botón.</p>
  </div>

  <footer>
    <button id="cta" disabled>Botón disponible en 30s</button>
    <p>¡Llegaste al final!</p>
  </footer>

  <script>
    const btn = document.getElementById('cta');
    let tiempo = 30;

    btn.disabled = true;
    btn.textContent = `Botón disponible en ${tiempo}s`;

    const intervalo = setInterval(() => {
      tiempo--;
      btn.textContent = `Botón disponible en ${tiempo}s`;
      if (tiempo <= 0) {
        clearInterval(intervalo);
        btn.disabled = false;
        btn.textContent = "Botón al fondo";
      }
    }, 1000);

    btn.addEventListener('click', () => {
      alert('¡Has presionado el botón al fondo!');
    });
  </script>
</body>
</html>
