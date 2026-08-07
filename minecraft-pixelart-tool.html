<!DOCTYPE html>
<html lang="de">
<head>
<meta charset="UTF-8">
<title>Minecraft Wolle Pixel Art Generator</title>
<style>
  :root{
    --bg: #1b1d17;
    --panel: #24261e;
    --panel-2: #2c2f24;
    --line: #3a3d30;
    --text: #ecebe2;
    --muted: #a5a798;
    --accent: #80c71f; /* lime wool */
    --accent-2: #3ab3da; /* light blue wool */
  }
  *{box-sizing:border-box;}
  body{
    margin:0;
    font-family: "Segoe UI", system-ui, sans-serif;
    background: var(--bg);
    color: var(--text);
    background-image:
      linear-gradient(var(--bg), var(--bg)),
      repeating-linear-gradient(45deg, rgba(255,255,255,0.015) 0 2px, transparent 2px 8px);
  }
  header{
    padding: 28px 24px 18px;
    border-bottom: 4px solid var(--line);
    background: linear-gradient(180deg, #23251c, #1b1d17);
  }
  header h1{
    margin:0 0 6px;
    font-size: 1.5rem;
    letter-spacing: 0.5px;
  }
  header h1 span{ color: var(--accent); }
  header p{ margin:0; color: var(--muted); font-size:0.92rem; }

  main{
    max-width: 1100px;
    margin: 0 auto;
    padding: 24px;
    display: grid;
    gap: 20px;
  }

  .panel{
    background: var(--panel);
    border: 2px solid var(--line);
    border-radius: 4px;
    padding: 18px 20px;
  }

  .controls{
    display:flex;
    flex-wrap:wrap;
    gap: 16px;
    align-items:flex-end;
  }
  .field{ display:flex; flex-direction:column; gap:6px; }
  .field label{ font-size: 0.8rem; color: var(--muted); }
  .field input[type=number]{
    width: 90px;
    padding: 8px 10px;
    background: var(--panel-2);
    border: 2px solid var(--line);
    border-radius: 3px;
    color: var(--text);
    font-size: 0.95rem;
  }
  input[type=file]{
    color: var(--muted);
    font-size: 0.85rem;
  }
  .lockratio{ display:flex; align-items:center; gap:6px; font-size:0.8rem; color:var(--muted); }

  button{
    padding: 10px 18px;
    background: var(--accent);
    color: #16220a;
    border: none;
    border-radius: 3px;
    font-weight: 700;
    font-size: 0.9rem;
    cursor: pointer;
    letter-spacing: 0.3px;
  }
  button:hover{ filter: brightness(1.08); }
  button.secondary{
    background: var(--panel-2);
    color: var(--text);
    border: 2px solid var(--line);
  }

  .status{ color: var(--muted); font-size:0.85rem; min-height: 1.2em; }

  .result-grid{
    display:grid;
    grid-template-columns: 1fr;
    gap: 20px;
  }
  @media(min-width: 780px){
    .result-grid{ grid-template-columns: 1.3fr 1fr; }
  }

  canvas#output{
    width:100%;
    image-rendering: pixelated;
    border: 2px solid var(--line);
    border-radius: 3px;
    background: repeating-conic-gradient(#2a2c22 0% 25%, #24261e 0% 50%) 50% / 20px 20px;
  }

  .legend{
    display:flex;
    flex-direction:column;
    gap:8px;
    max-height: 480px;
    overflow-y:auto;
    padding-right: 4px;
  }
  .legend-row{
    display:flex;
    align-items:center;
    gap:10px;
    padding: 6px 8px;
    border-radius: 3px;
    background: var(--panel-2);
    border: 1px solid var(--line);
    font-size: 0.88rem;
  }
  .swatch{
    width: 22px; height:22px;
    border-radius: 3px;
    border: 2px solid rgba(255,255,255,0.15);
    flex-shrink:0;
  }
  .legend-row .name{ flex:1; }
  .legend-row .count{ color: var(--accent-2); font-weight:700; }

  .hint{ font-size:0.8rem; color: var(--muted); margin-top:4px; }
  .actions{ display:flex; gap:10px; flex-wrap:wrap; margin-top:14px;}
  .total{ font-size:0.85rem; color: var(--muted); margin-top:10px; }
</style>
</head>
<body>

<header>
  <h1>Wolle-<span>Pixelart</span> Generator</h1>
  <p>Bild hochladen → Rastergröße wählen → auf die 16 Minecraft-Wollfarben reduzieren → Bauvorlage & Materialliste erhalten.</p>
</header>

<main>
  <section class="panel controls">
    <div class="field">
      <label for="fileInput">Bild (lokal)</label>
      <input type="file" id="fileInput" accept="image/*">
    </div>
    <div class="field" style="flex:1; min-width:220px;">
      <label for="urlInput">...oder Bild-URL</label>
      <div style="display:flex; gap:8px;">
        <input type="text" id="urlInput" placeholder="https://beispiel.de/bild.png" style="flex:1; padding:8px 10px; background:var(--panel-2); border:2px solid var(--line); border-radius:3px; color:var(--text); font-size:0.9rem;">
        <button class="secondary" id="loadUrlBtn" type="button">Laden</button>
      </div>
    </div>
    <div class="field">
      <label for="widthInput">Breite (Blöcke)</label>
      <input type="number" id="widthInput" value="16" min="1" max="128">
    </div>
    <div class="field">
      <label for="heightInput">Höhe (Blöcke)</label>
      <input type="number" id="heightInput" value="10" min="1" max="128">
    </div>
    <div class="field">
      <label>&nbsp;</label>
      <button id="generateBtn">Pixelart erzeugen</button>
    </div>
    <div class="field">
      <label>&nbsp;</label>
      <span class="status" id="status">Noch kein Bild geladen.</span>
    </div>
  </section>

  <section class="panel result-grid" id="resultSection" style="display:none;">
    <div>
      <canvas id="output"></canvas>
      <div class="actions">
        <button class="secondary" id="downloadPngBtn">PNG herunterladen</button>
        <button class="secondary" id="downloadListBtn">Materialliste (.txt)</button>
      </div>
      <p class="hint">Jedes Kästchen entspricht einem Wollblock. Die Textur ist bewusst grob gerastert, damit du sie 1:1 in Minecraft nachlegen kannst.</p>
    </div>
    <div>
      <h3 style="margin-top:0;">Materialliste</h3>
      <div class="legend" id="legend"></div>
      <div class="total" id="totalBlocks"></div>
    </div>
  </section>
</main>

<script>
// Offizielle Minecraft-Farbstoff-/Wollfarben (16 Standardfarben)
const WOOL_COLORS = [
  { name: "Weiß (White)",        hex: "#f9ffff" },
  { name: "Hellgrau (Light Gray)", hex: "#9c9d97" },
  { name: "Grau (Gray)",         hex: "#474f52" },
  { name: "Schwarz (Black)",     hex: "#1d1c21" },
  { name: "Braun (Brown)",       hex: "#825432" },
  { name: "Rot (Red)",           hex: "#b02e26" },
  { name: "Orange (Orange)",     hex: "#f9801d" },
  { name: "Gelb (Yellow)",       hex: "#ffd83d" },
  { name: "Hellgrün (Lime)",     hex: "#80c71f" },
  { name: "Grün (Green)",        hex: "#5d7c15" },
  { name: "Cyan (Cyan)",         hex: "#169c9d" },
  { name: "Hellblau (Light Blue)", hex: "#3ab3da" },
  { name: "Blau (Blue)",         hex: "#3c44a9" },
  { name: "Rosa (Pink)",         hex: "#f38caa" },
  { name: "Magenta (Magenta)",   hex: "#c64fbd" },
  { name: "Lila (Purple)",       hex: "#8932b7" },
];

function hexToRgb(hex){
  const n = parseInt(hex.slice(1), 16);
  return { r: (n>>16)&255, g: (n>>8)&255, b: n&255 };
}
const WOOL_RGB = WOOL_COLORS.map(c => ({...c, rgb: hexToRgb(c.hex)}));

function nearestWool(r,g,b){
  let best = null, bestDist = Infinity;
  for(const c of WOOL_RGB){
    const dr = r - c.rgb.r, dg = g - c.rgb.g, db = b - c.rgb.b;
    const dist = dr*dr + dg*dg + db*db;
    if(dist < bestDist){ bestDist = dist; best = c; }
  }
  return best;
}

let loadedImage = null;
const fileInput = document.getElementById('fileInput');
const urlInput = document.getElementById('urlInput');
const loadUrlBtn = document.getElementById('loadUrlBtn');
const widthInput = document.getElementById('widthInput');
const heightInput = document.getElementById('heightInput');
const generateBtn = document.getElementById('generateBtn');
const statusEl = document.getElementById('status');
const resultSection = document.getElementById('resultSection');
const outputCanvas = document.getElementById('output');
const legendEl = document.getElementById('legend');
const totalBlocksEl = document.getElementById('totalBlocks');
const downloadPngBtn = document.getElementById('downloadPngBtn');
const downloadListBtn = document.getElementById('downloadListBtn');

let lastGrid = null; // { w, h, cells: [{name,hex,rgb}...] }

fileInput.addEventListener('change', (e) => {
  const file = e.target.files[0];
  if(!file) return;
  loadedImage = null;
  statusEl.textContent = "Bild wird geladen …";
  const reader = new FileReader();
  reader.onload = (ev) => {
    const img = new Image();
    img.onload = () => {
      loadedImage = img;
      statusEl.textContent = `Bild geladen (${img.width}×${img.height}px). Bereit zum Erzeugen.`;
    };
    img.onerror = () => {
      statusEl.textContent = "Das Bild konnte nicht gelesen werden. Bitte ein anderes Format probieren (PNG/JPG).";
    };
    img.src = ev.target.result;
  };
  reader.onerror = () => {
    statusEl.textContent = "Datei konnte nicht gelesen werden.";
  };
  reader.readAsDataURL(file);
});

loadUrlBtn.addEventListener('click', () => {
  const url = urlInput.value.trim();
  if(!url){
    statusEl.textContent = "Bitte eine Bild-URL eingeben.";
    return;
  }
  loadedImage = null;
  statusEl.textContent = "Bild wird von der URL geladen …";
  const img = new Image();
  img.crossOrigin = "anonymous"; // nötig, um später Pixel auslesen zu dürfen
  img.onload = () => {
    loadedImage = img;
    statusEl.textContent = `Bild von URL geladen (${img.width}×${img.height}px). Bereit zum Erzeugen.`;
  };
  img.onerror = () => {
    statusEl.textContent = "Konnte das Bild nicht laden. Manche Seiten blockieren externen Zugriff (CORS) — probier einen direkten Bildlink (endet meist auf .png/.jpg) oder lade das Bild lokal hoch.";
  };
  img.src = url;
});

generateBtn.addEventListener('click', () => {
  if(!loadedImage){
    statusEl.textContent = fileInput.files[0]
      ? "Bild wird noch geladen – bitte kurz warten und erneut klicken."
      : "Bitte zuerst ein Bild auswählen.";
    return;
  }
  const gw = Math.max(1, Math.min(128, parseInt(widthInput.value) || 16));
  const ghh = Math.max(1, Math.min(128, parseInt(heightInput.value) || 10));

  // 1. Downscale image to gw x gh using an offscreen canvas (browser does averaging via smoothing)
  const small = document.createElement('canvas');
  small.width = gw;
  small.height = ghh;
  const sctx = small.getContext('2d');
  sctx.imageSmoothingEnabled = true;
  sctx.imageSmoothingQuality = 'high';
  sctx.drawImage(loadedImage, 0, 0, gw, ghh);
  const data = sctx.getImageData(0, 0, gw, ghh).data;

  // 2. Map each cell to nearest wool color
  const cells = [];
  for(let i = 0; i < gw*ghh; i++){
    const r = data[i*4], g = data[i*4+1], b = data[i*4+2];
    cells.push(nearestWool(r,g,b));
  }
  lastGrid = { w: gw, h: ghh, cells };

  // 3. Render blocky output
  const cellSize = Math.max(6, Math.floor(720 / Math.max(gw, ghh)));
  outputCanvas.width = gw * cellSize;
  outputCanvas.height = ghh * cellSize;
  const octx = outputCanvas.getContext('2d');
  for(let y = 0; y < ghh; y++){
    for(let x = 0; x < gw; x++){
      const c = cells[y*gw + x];
      octx.fillStyle = c.hex;
      octx.fillRect(x*cellSize, y*cellSize, cellSize, cellSize);
    }
  }
  // grid lines
  octx.strokeStyle = "rgba(0,0,0,0.25)";
  octx.lineWidth = 1;
  for(let x = 0; x <= gw; x++){
    octx.beginPath();
    octx.moveTo(x*cellSize, 0);
    octx.lineTo(x*cellSize, ghh*cellSize);
    octx.stroke();
  }
  for(let y = 0; y <= ghh; y++){
    octx.beginPath();
    octx.moveTo(0, y*cellSize);
    octx.lineTo(gw*cellSize, y*cellSize);
    octx.stroke();
  }

  // 4. Legend / material list
  const counts = new Map();
  for(const c of cells){
    counts.set(c.name, (counts.get(c.name)||{count:0, hex:c.hex}));
    counts.get(c.name).count++;
    counts.get(c.name).hex = c.hex;
  }
  const sorted = [...counts.entries()].sort((a,b) => b[1].count - a[1].count);
  legendEl.innerHTML = '';
  for(const [name, info] of sorted){
    const row = document.createElement('div');
    row.className = 'legend-row';
    row.innerHTML = `<div class="swatch" style="background:${info.hex}"></div>
      <div class="name">${name}</div>
      <div class="count">${info.count}×</div>`;
    legendEl.appendChild(row);
  }
  totalBlocksEl.textContent = `Gesamt: ${gw*ghh} Blöcke (${gw} × ${ghh})`;

  resultSection.style.display = 'grid';
  statusEl.textContent = `Fertig: ${gw}×${ghh} Wolle-Pixelart erzeugt.`;
});

downloadPngBtn.addEventListener('click', () => {
  const link = document.createElement('a');
  link.download = 'minecraft-wolle-pixelart.png';
  link.href = outputCanvas.toDataURL('image/png');
  link.click();
});

downloadListBtn.addEventListener('click', () => {
  if(!lastGrid) return;
  const counts = new Map();
  for(const c of lastGrid.cells){
    counts.set(c.name, (counts.get(c.name)||0) + 1);
  }
  const sorted = [...counts.entries()].sort((a,b) => b[1]-a[1]);
  let text = `Minecraft Wolle Pixelart – Materialliste\n`;
  text += `Größe: ${lastGrid.w} x ${lastGrid.h} (${lastGrid.w*lastGrid.h} Blöcke)\n\n`;
  for(const [name, count] of sorted){
    text += `${count}x  ${name}\n`;
  }
  const blob = new Blob([text], { type: 'text/plain' });
  const link = document.createElement('a');
  link.download = 'materialliste.txt';
  link.href = URL.createObjectURL(blob);
  link.click();
});
</script>

</body>
</html>
