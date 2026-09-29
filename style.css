<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>¿Dónde está Toby? | Boceto Animado a Lápiz</title>
  <style>
    @import url('https://fonts.googleapis.com/css2?family=Caveat:wght@600;700&family=Patrick+Hand&display=swap');

    :root {
      --paper-bg: #f5eedc;
      --paper-line: #e3d5be;
      --pencil: #2a2829;
      --pencil-light: #5a5658;
      --graphite-shade: #787376;
      --highlight: #d94e34;
      --notebook-shadow: 0 12px 35px rgba(45, 38, 30, 0.25);
    }

    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
    }

    body {
      background-color: #2b2622;
      background-image: 
        radial-gradient(#3a332d 15%, transparent 16%), 
        radial-gradient(#3a332d 15%, transparent 16%);
      background-size: 30px 30px;
      background-position: 0 0, 15px 15px;
      color: var(--pencil);
      font-family: 'Patrick Hand', cursive, sans-serif;
      min-height: 100vh;
      display: flex;
      flex-direction: column;
      align-items: center;
      padding: 16px;
    }

    /* FILTRO SVG PARA TRAZO DE LÁPIZ ORGÁNICO RUGOSO */
    svg.filters {
      position: absolute;
      width: 0;
      height: 0;
    }

    header {
      width: 100%;
      max-width: 880px;
      background: var(--paper-bg);
      padding: 14px 24px;
      border: 3px solid var(--pencil);
      border-radius: 4px 14px 6px 12px;
      box-shadow: 4px 5px 0px var(--pencil);
      display: flex;
      justify-content: space-between;
      align-items: center;
      margin-bottom: 14px;
      transform: rotate(-0.4deg);
    }

    h1 {
      font-family: 'Caveat', cursive;
      font-size: 2.2rem;
      letter-spacing: 1px;
      color: var(--pencil);
    }

    .controls-bar {
      display: flex;
      gap: 10px;
    }

    button {
      cursor: pointer;
      background: #fdfaf3;
      border: 2px solid var(--pencil);
      border-radius: 6px 12px 4px 8px;
      font-family: 'Patrick Hand', cursive;
      font-size: 1.15rem;
      padding: 6px 14px;
      color: var(--pencil);
      box-shadow: 2px 3px 0px var(--pencil);
      transition: all 0.15s ease;
      display: inline-flex;
      align-items: center;
      gap: 6px;
    }

    button:hover {
      transform: translate(-1px, -2px);
      box-shadow: 4px 5px 0px var(--highlight);
      border-color: var(--highlight);
      color: var(--highlight);
    }

    button:active {
      transform: translate(2px, 2px);
      box-shadow: 0px 0px 0px var(--pencil);
    }

    /* CONTENEDOR TIPO CUADERNO DE BOCETOS */
    .notebook {
      width: 100%;
      max-width: 880px;
      background: var(--paper-bg);
      /* Textura papel artesanal cuadriculado tenue */
      background-image: 
        linear-gradient(to right, rgba(160, 140, 115, 0.15) 1px, transparent 1px),
        linear-gradient(to bottom, rgba(160, 140, 115, 0.15) 1px, transparent 1px);
      background-size: 24px 24px;
      border: 3px solid var(--pencil);
      border-radius: 6px 16px 8px 14px;
      box-shadow: var(--notebook-shadow), 6px 8px 0px var(--pencil);
      overflow: hidden;
      display: flex;
      flex-direction: column;
      position: relative;
    }

    /* ESPACIO DE VISUALIZACIÓN ILUSTRADO / ANIMADO */
    .viewport {
      width: 100%;
      height: 420px;
      position: relative;
      border-bottom: 3px dashed var(--pencil-light);
      background: #faf4e8;
      overflow: hidden;
      display: flex;
      align-items: center;
      justify-content: center;
    }

    /* EFECTO BOILING LINE (Vibración de lápiz cuadro a cuadro tradicional) */
    .sketch-svg {
      width: 100%;
      height: 100%;
      filter: url(#pencil-texture);
      animation: lineBoil 0.35s steps(2) infinite;
    }

    @keyframes lineBoil {
      0% { transform: translate(0, 0) scale(1); }
      50% { transform: translate(-0.8px, 0.7px) scale(1.002); }
      100% { transform: translate(0.6px, -0.6px) scale(0.999); }
    }

    /* Elementos animados dibujados */
    .anim-wag-pencil {
      transform-origin: 395px 260px;
      animation: wagPencil 0.5s steps(3) infinite alternate;
    }

    @keyframes wagPencil {
      from { transform: rotate(-12deg); }
      to { transform: rotate(18deg); }
    }

    .anim-bob-pencil {
      animation: bobPencil 0.7s steps(2) infinite alternate;
    }

    @keyframes bobPencil {
      0% { transform: translateY(0); }
      100% { transform: translateY(-7px); }
    }

    /* Lupa / Marcador interactivo en lápiz rojo (Control Exploratorio 1) */
    .sketch-hotspot {
      position: absolute;
      width: 48px;
      height: 48px;
      border: 3px dashed var(--highlight);
      border-radius: 50%;
      background: rgba(217, 78, 52, 0.15);
      cursor: pointer;
      display: flex;
      align-items: center;
      justify-content: center;
      font-size: 1.5rem;
      animation: hotspotJiggle 0.6s infinite alternate ease-in-out;
      z-index: 10;
    }

    @keyframes hotspotJiggle {
      0% { transform: scale(1) rotate(-4deg); }
      100% { transform: scale(1.15) rotate(5deg); }
    }

    /* Reproductor de Video para los 3 Nodos Audiovisuales */
    .video-canvas {
      width: 100%;
      height: 100%;
      position: relative;
      display: none;
      background: #111;
    }

    video {
      width: 100%;
      height: 100%;
      object-fit: cover;
    }

    .video-tag {
      position: absolute;
      top: 14px;
      left: 14px;
      background: var(--paper-bg);
      border: 2px solid var(--pencil);
      padding: 4px 10px;
      font-size: 0.95rem;
      font-weight: bold;
      box-shadow: 2px 2px 0px var(--pencil);
    }

    /* CONTENIDO DEL TEXTO NARRATIVO */
    .content-area {
      padding: 24px;
    }

    .status-row {
      display: flex;
      justify-content: space-between;
      border-bottom: 2px solid var(--paper-line);
      padding-bottom: 6px;
      margin-bottom: 12px;
      font-size: 1.25rem;
      color: var(--highlight);
      font-family: 'Caveat', cursive;
    }

    .narrative-text {
      font-size: 1.45rem;
      line-height: 1.5;
      color: var(--pencil);
      margin-bottom: 24px;
      min-height: 60px;
    }

    .options-label {
      font-family: 'Caveat', cursive;
      font-size: 1.4rem;
      color: var(--pencil-light);
      margin-bottom: 8px;
    }

    .choices-row {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
      gap: 12px;
    }

    .choice-card {
      background: #fffdf9;
      border: 2px solid var(--pencil);
      border-radius: 6px 12px 5px 10px;
      padding: 12px 18px;
      font-size: 1.25rem;
      color: var(--pencil);
      cursor: pointer;
      text-align: left;
      box-shadow: 3px 3px 0px var(--pencil);
      transition: all 0.15s ease;
      display: flex;
      justify-content: space-between;
      align-items: center;
    }

    .choice-card:hover {
      background: var(--paper-bg);
      border-color: var(--highlight);
      color: var(--highlight);
      transform: translateY(-2px);
      box-shadow: 4px 5px 0px var(--highlight);
    }

    /* MODALES DE MAPA Y PISTAS */
    .modal-overlay {
      display: none;
      position: fixed;
      inset: 0;
      background: rgba(30, 25, 20, 0.75);
      z-index: 100;
      align-items: center;
      justify-content: center;
      padding: 16px;
    }

    .modal-sheet {
      background: var(--paper-bg);
      border: 3px solid var(--pencil);
      border-radius: 6px 16px 8px 14px;
      max-width: 650px;
      width: 100%;
      padding: 24px;
      box-shadow: 8px 10px 0px #000;
    }

    .modal-sheet h2 {
      font-family: 'Caveat', cursive;
      font-size: 2rem;
      margin-bottom: 10px;
    }

    .map-grid {
      display: flex;
      flex-wrap: wrap;
      gap: 8px;
      margin: 16px 0;
    }

    .node-tag {
      border: 2px solid var(--pencil);
      background: #faf4e8;
      padding: 6px 12px;
      border-radius: 6px;
      font-size: 1.1rem;
    }

    .node-tag.current {
      background: var(--highlight);
      color: #fff;
      border-color: var(--highlight);
    }

    .node-tag.visited {
      border-color: #2b7a4b;
      color: #2b7a4b;
      font-weight: bold;
    }
  </style>
</head>
<body>

  <!-- Filtro SVG para simular textura rugosa y granulada de grafito/papel -->
  <svg class="filters">
    <filter id="pencil-texture">
      <feTurbulence type="fractalNoise" baseFrequency="0.04" numOctaves="4" result="noise" />
      <feDisplacementMap in="SourceGraphic" in2="noise" scale="3.2" xChannelSelector="R" yChannelSelector="G" />
    </filter>
  </svg>

  <header>
    <h1>📓 ¿Dónde está Toby? (Boceto a Lápiz)</h1>
    <div class="controls-bar">
      <button onclick="toggleAudio()" id="audioBtn">✏️ Sonido: Trazo ON</button>
      <button onclick="openModal('mapModal')">🗺️ Mapa de Nodos</button>
      <button onclick="openModal('cluesModal')">🎒 Pistas (<span id="clueCount">0</span>)</button>
    </div>
  </header>

  <main class="notebook">
    <!-- Ventana visual: Animación 2D a lápiz o Video Embebido -->
    <div class="viewport" id="viewport">
      <div id="sketchContainer" style="width: 100%; height: 100%;"></div>

      <!-- Contenedor para los 3 videos de producción propia -->
      <div class="video-canvas" id="videoCanvas">
        <span class="video-tag">🎬 Pieza Audiovisual Propia</span>
        <video id="sceneVideo" controls playsinline></video>
      </div>

      <!-- Hotspot exploratorio interactivo estilo marca de lápiz rojo -->
      <div class="sketch-hotspot" id="hotspot" style="display:none;" onclick="inspectClue()">✏️</div>
    </div>

    <!-- Texto narrativo hipertextual -->
    <div class="content-area">
      <div class="status-row">
        <span id="nodeTitle">Nodo 1: La desaparición</span>
        <span id="nodeDepth">Profundidad: Nivel 1</span>
      </div>
      <p class="narrative-text" id="nodeDesc">Cargando trazo...</p>

      <div class="options-label">¿Hacia dónde buscas ahora?</div>
      <div class="choices-row" id="choicesRow"></div>
    </div>
  </main>

  <!-- MODAL MAPA HIPERTEXTUAL (Control Exploratorio 2) -->
  <div class="modal-overlay" id="mapModal" onclick="closeModal(event, 'mapModal')">
    <div class="modal-sheet" onclick="event.stopPropagation()">
      <h2>🗺️ Mapa de Rutas Trazadas</h2>
      <p>Visualiza el esquema del diagrama y los nodos que ya has explorado a lápiz:</p>
      <div class="map-grid" id="mapGrid"></div>
      <button onclick="document.getElementById('mapModal').style.display='none'">Volver a la historia</button>
    </div>
  </div>

  <!-- MODAL BITÁCORA DE PISTAS (Control Exploratorio 3) -->
  <div class="modal-overlay" id="cluesModal" onclick="closeModal(event, 'cluesModal')">
    <div class="modal-sheet" onclick="event.stopPropagation()">
      <h2>🎒 Pistas Anotadas en la Libreta</h2>
      <ul id="cluesList" style="margin: 16px 0 16px 24px; font-size: 1.3rem; line-height: 1.6;">
        <li>Aún no has anotado pistas en esta página. Busca los círculos con lápiz rojo ✏️.</li>
      </ul>
      <button onclick="document.getElementById('cluesModal').style.display='none'">Guardar libreta</button>
    </div>
  </div>

  <script>
    // Sintetizador Web Audio API: Sonido de rasgado de lápiz sobre papel y ladridos rústicos
    let audioCtx = null;
    let soundEnabled = true;

    function initAudio() {
      if (!audioCtx) {
        audioCtx = new (window.AudioContext || window.webkitAudioContext)();
      }
    }

    function playPaperPencilSound() {
      if (!soundEnabled) return;
      initAudio();
      
      // Simula fricción de grafito sobre papel
      const bufferSize = audioCtx.sampleRate * 0.12;
      const buffer = audioCtx.createBuffer(1, bufferSize, audioCtx.sampleRate);
      const output = buffer.getChannelData(0);
      for (let i = 0; i < bufferSize; i++) {
        output[i] = Math.random() * 2 - 1;
      }
      const whiteNoise = audioCtx.createBufferSource();
      whiteNoise.buffer = buffer;

      const filter = audioCtx.createBiquadFilter();
      filter.type = 'bandpass';
      filter.frequency.value = 1200;
      filter.Q.value = 3.0;

      const gain = audioCtx.createGain();
      gain.gain.setValueAtTime(0.2, audioCtx.currentTime);
      gain.gain.linearRampToValueAtTime(0.01, audioCtx.currentTime + 0.12);

      whiteNoise.connect(filter);
      filter.connect(gain);
      gain.connect(audioCtx.destination);
      whiteNoise.start();
    }

    function toggleAudio() {
      soundEnabled = !soundEnabled;
      document.getElementById('audioBtn').innerText = soundEnabled ? '✏️ Sonido: Trazo ON' : '🔇 Sonido: OFF';
    }

    // ILUSTRACIONES 2D EN ESTILO BOCETO A LÁPIZ Y PAPEL (SVG Hand-drawn)
    const pencilScenes = {
      patio: `
        <svg class="sketch-svg" viewBox="0 0 800 450" xmlns="http://www.w3.org/2000/svg">
          <!-- Textura de fondo con rayado de sombreado -->
          <line x1="0" y1="280" x2="800" y2="280" stroke="#2a2829" stroke-width="3" stroke-linecap="round"/>
          <line x1="10" y1="290" x2="790" y2="290" stroke="#5a5658" stroke-width="1.5" stroke-dasharray="8 6"/>
          
          <!-- Cerco de madera dibujado a mano alzada -->
          <g stroke="#2a2829" stroke-width="2.5" fill="none" stroke-linecap="round" stroke-linejoin="round">
            <path d="M 60 280 L 65 190 L 78 175 L 90 190 L 95 280 Z"/>
            <path d="M 110 280 L 115 185 L 128 170 L 140 185 L 145 280 Z"/>
            <path d="M 160 280 L 165 195 L 178 180 L 190 195 L 195 280 Z"/>
            <line x1="50" y1="210" x2="210" y2="210" stroke-width="3"/>
            <line x1="50" y1="250" x2="210" y2="250" stroke-width="3"/>
          </g>

          <!-- Portón de madera abierto con bisagra torcida -->
          <g stroke="#2a2829" stroke-width="3" fill="none" stroke-linecap="round">
            <path d="M 560 140 L 680 165 L 675 310 L 560 280 Z"/>
            <line x1="560" y1="140" x2="675" y2="310"/>
            <!-- Sombreado a lápiz (cross-hatching) en el hueco -->
            <path d="M 570 180 L 660 200 M 575 220 L 665 240 M 580 260 L 660 275" stroke="#787376" stroke-width="1.5"/>
          </g>

          <!-- Plato de comida vacío dibujado -->
          <ellipse cx="370" cy="350" rx="55" ry="18" stroke="#2a2829" stroke-width="3" fill="none"/>
          <ellipse cx="370" cy="347" rx="45" ry="12" stroke="#5a5658" stroke-width="1.5" fill="none"/>
          <text x="345" y="353" font-family="'Patrick Hand', cursive" font-size="20" fill="#2a2829">"TOBY"</text>

          <!-- Pequeñas briznas de hierba a mano alzada -->
          <path d="M 240 330 L 243 315 M 245 330 L 252 318 M 470 340 L 473 325" stroke="#2a2829" stroke-width="2"/>
        </svg>`,

      calle: `
        <svg class="sketch-svg" viewBox="0 0 800 450" xmlns="http://www.w3.org/2000/svg">
          <!-- Casas del vecindario en boceto arquitectónico rápido -->
          <g stroke="#2a2829" stroke-width="2.5" fill="none" stroke-linecap="round" stroke-linejoin="round">
            <!-- Casa 1 -->
            <polygon points="80,190 160,110 240,190"/>
            <rect x="95" y="190" width="130" height="90"/>
            <rect x="145" y="220" width="30" height="60"/>
            <rect x="110" y="210" width="25" height="25"/>
            <!-- Casa 2 -->
            <polygon points="260,190 340,125 420,190"/>
            <rect x="275" y="190" width="130" height="90"/>
          </g>

          <!-- Cordón de vereda y perspectiva de la calle -->
          <line x1="0" y1="280" x2="800" y2="280" stroke="#2a2829" stroke-width="3"/>
          <line x1="0" y1="320" x2="800" y2="320" stroke="#2a2829" stroke-width="2.5"/>
          <line x1="120" y1="370" x2="220" y2="370" stroke="#5a5658" stroke-width="4" stroke-dasharray="30 20"/>
          <line x1="360" y1="370" x2="480" y2="370" stroke="#5a5658" stroke-width="4" stroke-dasharray="30 20"/>

          <!-- Poste de luz en grafito con cables curvados -->
          <line x1="620" y1="70" x2="625" y2="280" stroke="#2a2829" stroke-width="4"/>
          <line x1="590" y1="85" x2="650" y2="85" stroke="#2a2829" stroke-width="3"/>
          <path d="M 0 110 Q 300 170 600 85" stroke="#787376" stroke-width="1.5" fill="none"/>
        </svg>`,

      huellas: `
        <svg class="sketch-svg" viewBox="0 0 800 450" xmlns="http://www.w3.org/2000/svg">
          <text x="240" y="60" font-family="'Caveat', cursive" font-size="34" fill="#2a2829">Boceto: Rastro de huellas en la tierra...</text>
          
          <!-- Huellas de perro dibujadas con grafito oscuro -->
          <g fill="#2a2829" stroke="#2a2829" stroke-width="1">
            <!-- Par de huellas 1 -->
            <g transform="translate(160, 320) rotate(-10)">
              <ellipse cx="20" cy="22" rx="14" ry="11"/>
              <circle cx="8" cy="5" r="4.5"/><circle cx="19" cy="2" r="4.5"/><circle cx="31" cy="5" r="4.5"/><circle cx="39" cy="14" r="4"/>
            </g>
            <!-- Par de huellas 2 -->
            <g transform="translate(290, 240) rotate(5)">
              <ellipse cx="20" cy="22" rx="14" ry="11"/>
              <circle cx="8" cy="5" r="4.5"/><circle cx="19" cy="2" r="4.5"/><circle cx="31" cy="5" r="4.5"/><circle cx="39" cy="14" r="4"/>
            </g>
            <!-- Par de huellas 3 -->
            <g transform="translate(430, 180) rotate(-15)">
              <ellipse cx="20" cy="22" rx="14" ry="11"/>
              <circle cx="8" cy="5" r="4.5"/><circle cx="19" cy="2" r="4.5"/><circle cx="31" cy="5" r="4.5"/><circle cx="39" cy="14" r="4"/>
            </g>
            <!-- Par de huellas 4 rumbo a la plaza -->
            <g transform="translate(560, 110) rotate(8)">
              <ellipse cx="20" cy="22" rx="13" ry="10"/>
              <circle cx="8" cy="5" r="4"/><circle cx="19" cy="2" r="4"/><circle cx="31" cy="5" r="4"/><circle cx="39" cy="14" r="3.5"/>
            </g>
          </g>

          <!-- Trazos de sombreado y texturas de tierra suelta -->
          <path d="M 120 370 L 190 365 M 340 290 L 400 285 M 500 220 L 580 215" stroke="#787376" stroke-width="2" stroke-dasharray="5 5"/>
        </svg>`,

      plaza: `
        <svg class="sketch-svg" viewBox="0 0 800 450" xmlns="http://www.w3.org/2000/svg">
          <!-- Árboles en bosquejo circular a mano alzada -->
          <g stroke="#2a2829" stroke-width="2.5" fill="none" stroke-linecap="round">
            <!-- Árbol izquierdo -->
            <path d="M 140 310 Q 150 220 130 170 Q 120 220 110 310"/>
            <path d="M 70 170 C 60 110, 130 90, 160 110 C 200 90, 230 140, 200 180 C 210 220, 130 240, 90 200 Z"/>
            <!-- Sombreado a lápiz en copa -->
            <path d="M 90 150 Q 140 160 180 150 M 100 170 Q 140 180 170 170" stroke="#787376" stroke-width="1.5"/>

            <!-- Árbol derecho -->
            <path d="M 640 310 Q 645 220 635 160"/>
            <path d="M 580 150 C 570 100, 640 80, 670 100 C 710 90, 730 150, 690 180 C 700 210, 610 220, 590 180 Z"/>
          </g>

          <!-- Banco de plaza en grafito -->
          <g stroke="#2a2829" stroke-width="2.5" fill="none">
            <line x1="330" y1="280" x2="470" y2="280" stroke-width="4"/>
            <line x1="330" y1="292" x2="470" y2="292" stroke-width="4"/>
            <line x1="345" y1="295" x2="340" y2="330" stroke-width="3"/>
            <line x1="455" y1="295" x2="450" y2="330" stroke-width="3"/>
          </g>

          <!-- Sendero que serpentea -->
          <path d="M 0 350 Q 380 320 800 350" stroke="#2a2829" stroke-width="2" stroke-dasharray="10 6" fill="none"/>
        </svg>`,

      preguntar: `
        <svg class="sketch-svg" viewBox="0 0 800 450" xmlns="http://www.w3.org/2000/svg">
          <!-- Vecina dibujada a estilo tira cómica de lápiz -->
          <g stroke="#2a2829" stroke-width="2.5" fill="none" stroke-linecap="round">
            <!-- Cabeza y peinado -->
            <circle cx="520" cy="170" r="30"/>
            <path d="M 490 160 Q 520 120 550 160 Q 560 190 535 185"/>
            <!-- Ojos y sonrisa en boceto -->
            <circle cx="510" cy="165" r="2" fill="#2a2829"/>
            <circle cx="525" cy="165" r="2" fill="#2a2829"/>
            <path d="M 512 180 Q 520 188 528 180"/>
            <!-- Cuerpo y brazos gesticulando -->
            <path d="M 520 200 L 520 310"/>
            <path d="M 520 230 L 470 200 L 440 215"/>
            <path d="M 520 230 L 565 240 L 585 270"/>
          </g>

          <!-- Globo de diálogo rotulado a mano -->
          <g stroke="#2a2829" stroke-width="2.5" fill="#faf4e8">
            <path d="M 180 80 L 420 80 Q 440 80 440 100 L 440 180 Q 440 200 420 200 L 320 200 L 280 240 L 295 200 L 180 200 Q 160 200 160 180 L 160 100 Q 160 80 180 80 Z"/>
          </g>
          <text x="185" y="125" font-family="'Patrick Hand', cursive" font-size="24" fill="#2a2829">"¡Hola! Sí, vi pasar corriendo a un</text>
          <text x="185" y="160" font-family="'Patrick Hand', cursive" font-size="24" fill="#2a2829">perrito con collar rojo hacia el sur!"</text>
        </svg>`,

      seguir: `
        <svg class="sketch-svg" viewBox="0 0 800 450" xmlns="http://www.w3.org/2000/svg">
          <!-- Sendero en perspectiva de dibujo en perspectiva con fuga -->
          <line x1="400" y1="180" x2="150" y2="450" stroke="#2a2829" stroke-width="3" stroke-linecap="round"/>
          <line x1="420" y1="180" x2="680" y2="450" stroke="#2a2829" stroke-width="3" stroke-linecap="round"/>
          <!-- Rayado de sombras en el camino -->
          <path d="M 360 230 L 440 230 M 320 280 L 490 280 M 260 350 L 560 350" stroke="#787376" stroke-width="2" stroke-dasharray="10 8"/>
          <!-- Césped y matorrales a los lados -->
          <path d="M 110 390 L 120 360 M 130 390 L 145 365 M 690 390 L 680 355 M 710 390 L 725 360" stroke="#2a2829" stroke-width="2.5"/>
          <text x="250" y="90" font-family="'Caveat', cursive" font-size="34" fill="#2a2829">Avanzando en silencio por el sendero...</text>
        </svg>`,

      correr: `
        <svg class="sketch-svg" viewBox="0 0 800 450" xmlns="http://www.w3.org/2000/svg">
          <!-- Líneas de velocidad y dinamismo a lápiz fuerte -->
          <g stroke="#2a2829" stroke-linecap="round">
            <line x1="40" y1="100" x2="380" y2="100" stroke-width="4" stroke-dasharray="60 30"/>
            <line x1="120" y1="180" x2="620" y2="180" stroke-width="5" stroke-dasharray="100 40"/>
            <line x1="60" y1="260" x2="480" y2="260" stroke-width="3.5" stroke-dasharray="50 25"/>
            <line x1="150" y1="340" x2="700" y2="340" stroke-width="4" stroke-dasharray="80 35"/>
          </g>
          <!-- Nube de polvo de carrera en bosquejo -->
          <path d="M 180 380 Q 150 350 180 330 Q 210 310 240 340 Q 280 330 290 360 Q 300 390 250 390 Z" stroke="#787376" stroke-width="2" fill="none"/>
          <text x="260" y="80" font-family="'Caveat', cursive" font-size="44" font-weight="bold" fill="#d94e34">¡CORRIENDO TRAS LOS LADRIDOS!</text>
        </svg>`,

      esperar: `
        <svg class="sketch-svg" viewBox="0 0 800 450" xmlns="http://www.w3.org/2000/svg">
          <!-- Silueta escuchando con ondas de sonido en grafito -->
          <circle cx="560" cy="200" r="40" stroke="#2a2829" stroke-width="2" fill="none" stroke-dasharray="6 6"/>
          <circle cx="560" cy="200" r="90" stroke="#2a2829" stroke-width="2.5" fill="none" stroke-dasharray="8 8"/>
          <circle cx="560" cy="200" r="140" stroke="#787376" stroke-width="2" fill="none" stroke-dasharray="10 10"/>
          
          <text x="210" y="90" font-family="'Caveat', cursive" font-size="34" fill="#2a2829">Detenerse... afinar el oído y esperar...</text>
          <text x="540" y="205" font-family="'Caveat', cursive" font-size="32" font-weight="bold" fill="#d94e34">¡Guau!</text>
        </svg>`,

      final_seguir: `
        <svg class="sketch-svg" viewBox="0 0 800 450" xmlns="http://www.w3.org/2000/svg">
          <!-- Protagonista y Toby caminando juntos dibujados a mano -->
          <g stroke="#2a2829" stroke-width="3" fill="none" stroke-linecap="round">
            <!-- Humano -->
            <circle cx="320" cy="180" r="22"/>
            <path d="M 320 202 L 315 285"/>
            <line x1="315" y1="285" x2="295" y2="345"/>
            <line x1="315" y1="285" x2="335" y2="345"/>
            <!-- Brazo sosteniendo la correa -->
            <path d="M 320 225 L 360 260"/>
            
            <!-- Correa de lápiz punteada -->
            <path d="M 360 260 Q 400 295 440 270" stroke="#d94e34" stroke-width="2.5" stroke-dasharray="6 4"/>

            <!-- Toby dibujado a lápiz -->
            <g class="anim-bob-pencil">
              <!-- Cuerpo y cabeza de Toby -->
              <ellipse cx="465" cy="285" rx="35" ry="20"/>
              <circle cx="505" cy="265" r="16"/>
              <ellipse cx="512" cy="268" rx="4" ry="7" fill="#2a2829"/> <!-- Oreja caída -->
              <!-- Patas -->
              <line x1="445" y1="305" x2="442" y2="340"/>
              <line x1="455" y1="305" x2="452" y2="340"/>
              <line x1="480" y1="305" x2="482" y2="340"/>
              <line x1="490" y1="305" x2="492" y2="340"/>
              <!-- Cola animada batiendo alegremente -->
              <path class="anim-wag-pencil" d="M 432 280 Q 410 260 415 245" stroke-width="3.5"/>
            </g>
          </g>

          <line x1="200" y1="345" x2="600" y2="345" stroke="#2a2829" stroke-width="3"/>
          <text x="250" y="80" font-family="'Caveat', cursive" font-size="36" fill="#2a2829">¡De vuelta a casa, juntos otra vez!</text>
        </svg>`
    };

    // Estructura de los 12 Nodos del diagrama de flujo
    const nodes = {
      1: {
        title: "Nodo 1: La desaparición",
        depth: "Nivel 1 de interacción",
        desc: "Llegas a casa y notas que el portón del patio está entornado. El plato con agua está en su lugar, pero Toby no vino a recibirte. ¡Ha desaparecido!",
        isVideo: true,
        videoUrl: "https://commondatastorage.googleapis.com/gtv-videos-bucket/sample/ForBiggerBlazes.mp4",
        hotspot: { top: "58%", left: "46%", text: "Marcas frescas de tierra y pelos atrapados en el cerrojo del portón." },
        choices: [
          { text: "Buscar en el patio", target: 2 },
          { text: "Salir a la calle", target: 3 }
        ]
      },
      2: {
        title: "Nodo 2: El patio",
        depth: "Nivel 2 de interacción",
        desc: "Inspeccionas el rincón de las plantas y la cucha. En la tierra húmeda del cantero distingues unas pisadas caninas que apuntan a la salida.",
        svgKey: "patio",
        hotspot: { top: "60%", left: "48%", text: "Huellas de patas dirigiéndose claramente al exterior." },
        choices: [
          { text: "Seguir las huellas", target: 4 }
        ]
      },
      3: {
        title: "Nodo 3: La calle",
        depth: "Nivel 2 de interacción",
        desc: "Sales a la vereda y oteas ambas direcciones. El viento suave levanta hojas secas sobre el asfalto. A lo lejos se divisan los árboles de la plaza.",
        svgKey: "calle",
        hotspot: { top: "62%", left: "68%", text: "Una vecina podando arbustos unos metros más adelante." },
        choices: [
          { text: "Caminar hacia la plaza", target: 5 }
        ]
      },
      4: {
        title: "Nodo 4: Seguir las huellas",
        depth: "Nivel 3 de interacción",
        desc: "Agachas la vista y vas tras las marcas de patas impresas en el barro blando. El rastro cruza la vereda y avanza sin vacilar hacia el espacio verde.",
        svgKey: "huellas",
        choices: [
          { text: "Entrar a la plaza", target: 5 }
        ]
      },
      5: {
        title: "Nodo 5: La plaza",
        depth: "Nivel 3 de interacción",
        desc: "Llegas a la plaza principal. Es un lugar amplio con bancos y senderos entrecruzados donde juegan niños y pasean vecinos.",
        svgKey: "plaza",
        choices: [
          { text: "Preguntar a una persona", target: 6 },
          { text: "Seguir buscando en solitario", target: 7 }
        ]
      },
      6: {
        title: "Nodo 6: Preguntar",
        depth: "Nivel 4 de interacción",
        desc: "Te acercas a una señora que descansa en un banco y le describes a Toby. Ella señala con el dedo hacia el sector sur de la plaza.",
        svgKey: "preguntar",
        hotspot: { top: "32%", left: "58%", text: "Testimonio: 'Un perrito con collar rojo pasó corriendo hacia la zona de juegos'." },
        choices: [
          { text: "Ir a ver esa pista", target: 8 }
        ]
      },
      7: {
        title: "Nodo 7: Seguir",
        depth: "Nivel 4 de interacción",
        desc: "Optas por internarte por tu cuenta en el sendero arbolado, mirando con atención los matorrales y silbando su nombre.",
        svgKey: "seguir",
        choices: [
          { text: "Inspeccionar los alrededores", target: 8 }
        ]
      },
      8: {
        title: "Nodo 8: Pista",
        depth: "Nivel 4 de interacción",
        desc: "¡Ahí en el pasto brilla algo conocido! Es la pelota de goma roja favorita de Toby, abandonada junto a unas ramas.",
        isVideo: true,
        videoUrl: "https://commondatastorage.googleapis.com/gtv-videos-bucket/sample/ForBiggerEscapes.mp4",
        hotspot: { top: "52%", left: "50%", text: "La pelota roja de Toby con marcas de mordiscos recientes." },
        choices: [
          { text: "Correr hacia los ruidos", target: 9 },
          { text: "Esperar y escuchar atentamente", target: 10 }
        ]
      },
      9: {
        title: "Nodo 9: Correr",
        depth: "Nivel 5 de interacción",
        desc: "Echas a correr a toda prisa sorteando ramas y bancos, guiado por los ladridos distantes que resuenan entre los eucaliptos.",
        svgKey: "correr",
        choices: [
          { text: "Alcanzar el claro", target: 11 }
        ]
      },
      10: {
        title: "Nodo 10: Esperar",
        depth: "Nivel 5 de interacción",
        desc: "Contienes la respiración y guardas absoluto reposo. Entre el rumor de las copas de los árboles, distingues con claridad un gemido alegre.",
        svgKey: "esperar",
        choices: [
          { text: "Acercarte despacio", target: 11 }
        ]
      },
      11: {
        title: "Nodo 11: ¡Encuentro!",
        depth: "Nivel 5 de interacción",
        desc: "¡Es él! Detrás de un grueso tronco asoma Toby, moviendo la cola de un lado a otro y corriendo a tus brazos.",
        isVideo: true,
        videoUrl: "https://commondatastorage.googleapis.com/gtv-videos-bucket/sample/ForBiggerFun.mp4",
        choices: [
          { text: "Llevar a Toby de regreso a casa", target: 12 }
        ]
      },
      12: {
        title: "Nodo 12: Regreso seguro",
        depth: "Desenlace final",
        desc: "Le abrochas la correa con alivio. El sol empieza a caer mientras caminan juntos de vuelta a casa. Toby está a salvo.",
        svgKey: "final_seguir",
        choices: [
          { text: "🔄 Volver a empezar la historia", target: 1 }
        ]
      }
    };

    let currentNode = 1;
    let visitedNodes = new Set([1]);
    let collectedClues = new Set();

    function renderNode(id) {
      currentNode = id;
      visitedNodes.add(id);
      const data = nodes[id];

      document.getElementById('nodeTitle').innerText = data.title;
      document.getElementById('nodeDepth').innerText = data.depth;
      document.getElementById('nodeDesc').innerText = data.desc;

      const sketchContainer = document.getElementById('sketchContainer');
      const videoCanvas = document.getElementById('videoCanvas');
      const videoElem = document.getElementById('sceneVideo');
      const hotspot = document.getElementById('hotspot');

      if (data.isVideo) {
        sketchContainer.style.display = 'none';
        videoCanvas.style.display = 'block';
        videoElem.src = data.videoUrl;
        videoElem.play().catch(() => {});
      } else {
        videoCanvas.style.display = 'none';
        videoElem.pause();
        sketchContainer.style.display = 'block';
        sketchContainer.innerHTML = pencilScenes[data.svgKey] || '';
      }

      // Hotspot interactivo (Control Exploratorio 1)
      if (data.hotspot) {
        hotspot.style.display = 'flex';
        hotspot.style.top = data.hotspot.top;
        hotspot.style.left = data.hotspot.left;
      } else {
        hotspot.style.display = 'none';
      }

      // Opciones bifurcadas
      const choicesRow = document.getElementById('choicesRow');
      choicesRow.innerHTML = '';
      data.choices.forEach(choice => {
        const btn = document.createElement('button');
        btn.className = 'choice-card';
        btn.innerHTML = `<span>${choice.text}</span> <span>✍️</span>`;
        btn.onclick = () => {
          playPaperPencilSound();
          renderNode(choice.target);
        };
        choicesRow.appendChild(btn);
      });

      updateMap();
    }

    function inspectClue() {
      const data = nodes[currentNode];
      if (data.hotspot) {
        playPaperPencilSound();
        collectedClues.add(data.hotspot.text);
        document.getElementById('clueCount').innerText = collectedClues.size;
        updateCluesList();
        alert(`✏️ Anotado en la libreta:\n\n${data.hotspot.text}`);
      }
    }

    function updateCluesList() {
      const list = document.getElementById('cluesList');
      if (collectedClues.size === 0) {
        list.innerHTML = '<li>Aún no has anotado pistas en esta página.</li>';
      } else {
        list.innerHTML = Array.from(collectedClues).map(c => `<li>✎ ${c}</li>`).join('');
      }
    }

    function updateMap() {
      const grid = document.getElementById('mapGrid');
      grid.innerHTML = '';
      Object.keys(nodes).forEach(key => {
        const nId = parseInt(key);
        const tag = document.createElement('div');
        tag.className = 'node-tag';
        if (nId === currentNode) tag.classList.add('current');
        else if (visitedNodes.has(nId)) tag.classList.add('visited');
        tag.innerText = nodes[nId].title;
        grid.appendChild(tag);
      });
    }

    function openModal(id) {
      document.getElementById(id).style.display = 'flex';
    }

    function closeModal(e, id) {
      document.getElementById(id).style.display = 'none';
    }

    // Iniciar en el primer nodo
    renderNode(1);
  </script>
</body>
</html>
