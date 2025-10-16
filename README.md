[fisica.html](https://github.com/user-attachments/files/22938142/fisica.html)
<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Física 9º2 — Cohetes de Agua</title>
  <style>
    /* 🎨 Colores y estilo general */
    :root {
      --celeste: #b3e5fc;
      --azul: #0288d1;
      --blanco: #ffffff;
      --gris: #f5f5f5;
      --gris-oscuro: #333;
    }

    body {
      font-family: 'Segoe UI', sans-serif;
      background: linear-gradient(180deg, var(--celeste), var(--blanco));
      margin: 0;
      padding: 0;
      color: var(--gris-oscuro);
    }

    header {
      background: var(--azul);
      color: var(--blanco);
      text-align: center;
      padding: 2rem 1rem;
      box-shadow: 0 4px 10px rgba(0, 0, 0, 0.2);
    }

    h1 {
      margin: 0;
      font-size: 2.5rem;
      letter-spacing: 1px;
    }

    nav {
      display: flex;
      justify-content: center;
      gap: 1rem;
      background: var(--blanco);
      border-bottom: 2px solid var(--celeste);
      padding: 0.5rem 0;
    }

    nav a {
      text-decoration: none;
      color: var(--azul);
      font-weight: bold;
      transition: 0.2s;
    }

    nav a:hover {
      color: var(--gris-oscuro);
    }

    section {
      max-width: 900px;
      margin: 2rem auto;
      background: var(--blanco);
      border-radius: 15px;
      padding: 2rem;
      box-shadow: 0 4px 12px rgba(0, 0, 0, 0.1);
    }

    h2 {
      color: var(--azul);
      border-bottom: 2px solid var(--celeste);
      padding-bottom: 0.5rem;
    }

    label {
      font-weight: bold;
      display: block;
      margin-top: 1rem;
    }

    input, select {
      width: 100%;
      padding: 0.5rem;
      border-radius: 8px;
      border: 1px solid #ccc;
      margin-top: 0.3rem;
    }

    button {
      background: var(--azul);
      color: white;
      padding: 0.7rem 1.2rem;
      border: none;
      border-radius: 8px;
      font-weight: bold;
      margin-top: 1rem;
      cursor: pointer;
      transition: 0.2s;
    }

    button:hover {
      background: #01579b;
    }

    .resultado {
      background: var(--gris);
      border-radius: 10px;
      padding: 1rem;
      margin-top: 1rem;
    }

    footer {
      text-align: center;
      background: var(--azul);
      color: white;
      padding: 1rem;
      margin-top: 3rem;
    }
  </style>
</head>
<body>

  <header>
    <h1>Física 9º2 — Cohetes de Agua 🚀</h1>
    <p>Diseña, calcula y construye tu propio cohete</p>
  </header>

  <nav>
    <a href="#diseno">Diseño</a>
    <a href="#calculos">Cálculos</a>
    <a href="#instrucciones">Construcción</a>
  </nav>

  <section id="diseno">
    <h2>Diseña tu cohete</h2>
    <p>Selecciona las características del cohete para simular su diseño.</p>

    <label for="longitud">Longitud del cuerpo (cm):</label>
    <input type="number" id="longitud" value="30" />

    <label for="aletas">Número de aletas:</label>
    <select id="aletas">
      <option value="3">3</option>
      <option value="4" selected>4</option>
      <option value="5">5</option>
    </select>

    <label for="diametro">Diámetro del cuerpo (cm):</label>
    <input type="number" id="diametro" value="8" />

    <label for="agua">Cantidad de agua (% del volumen):</label>
    <input type="number" id="agua" value="40" />

    <button onclick="calcular()">Calcular rendimiento</button>

    <div class="resultado" id="resultado"></div>
  </section>

  <section id="instrucciones">
    <h2>Cómo construirlo en casa</h2>
    <ol>
      <li>Usa una botella plástica de 2 litros (PET).</li>
      <li>Recorta aletas simétricas con cartón o plástico rígido.</li>
      <li>Pégalas con cinta fuerte o pegamento resistente al agua.</li>
      <li>Agrega una punta cónica para mejorar la aerodinámica.</li>
      <li>Llénalo con un 30–40% de agua y utiliza una bomba de aire.</li>
      <li>Apunta en un lugar abierto y seguro, y ¡lanza tu cohete!</li>
    </ol>
  </section>

  <footer>
    Proyecto escolar — Física 9º2 © 2025
  </footer>

  <script>
    function calcular() {
      const longitud = parseFloat(document.getElementById("longitud").value);
      const aletas = parseInt(document.getElementById("aletas").value);
      const diametro = parseFloat(document.getElementById("diametro").value);
      const agua = parseFloat(document.getElementById("agua").value);

      // 🧮 Cálculos aproximados simulados
      const volumen = Math.PI * Math.pow(diametro / 2, 2) * longitud;
      const masaAgua = volumen * (agua / 100) * 0.001; // en kg
      const presion = 3 + (agua / 20); // presión relativa
      const altitud = Math.round((presion * masaAgua * 20) / (diametro / 10));

      const aerodinamica = 100 - (aletas * 2 + (diametro / 2));
      const rendimiento = Math.max(0, Math.min(100, aerodinamica));

      document.getElementById("resultado").innerHTML = `
        <h3>Resultados del diseño:</h3>
        <p><strong>Altitud estimada:</strong> ${altitud} m</p>
        <p><strong>Eficiencia aerodinámica:</strong> ${rendimiento.toFixed(1)}%</p>
        <p><strong>Volumen del cuerpo:</strong> ${volumen.toFixed(1)} cm³</p>
        <p><strong>Masa de agua:</strong> ${masaAgua.toFixed(2)} kg</p>
      `;
    }
  </script>

</body>
</html>
