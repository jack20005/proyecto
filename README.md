# proyecto
<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Calculadora de Huella de Carbono</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background: #e0f7fa;
      padding: 20px;
    }
    .container {
      max-width: 500px;
      margin: auto;
      background: white;
      padding: 25px;
      border-radius: 10px;
      box-shadow: 0 0 10px rgba(0,0,0,0.1);
    }
    h2 {
      text-align: center;
      color: #00695c;
    }
    label {
      font-weight: bold;
    }
    select, input, button {
      width: 100%;
      padding: 10px;
      margin: 10px 0 20px;
      border-radius: 5px;
      border: 1px solid #ccc;
    }
    button {
      background-color: #00796b;
      color: white;
      cursor: pointer;
    }
    .resultado {
      padding: 15px;
      text-align: center;
      font-weight: bold;
      border-radius: 8px;
      background: #dcedc8;
    }
  </style>
</head>
<body>
  <div class="container">
    <h2>🌿 Calculadora de Huella de Carbono</h2>

    <label for="transporte">¿Usas auto todos los días?</label>
    <select id="transporte">
      <option value="0">No, camino o uso bici</option>
      <option value="1">A veces</option>
      <option value="2">Sí, todos los días</option>
    </select>

    <label for="energia">¿Cómo es tu consumo de electricidad?</label>
    <select id="energia">
      <option value="0">Bajo</option>
      <option value="1">Moderado</option>
      <option value="2">Alto (luces todo el día, electrodomésticos)</option>
    </select>

    <label for="alimentacion">¿Con qué frecuencia comes carne?</label>
    <select id="alimentacion">
      <option value="0">Nunca</option>
      <option value="1">Algunas veces por semana</option>
      <option value="2">Casi todos los días</option>
    </select>

    <button onclick="calcularHuella()">Calcular</button>

    <div class="resultado" id="resultado"></div>
  </div>

  <script>
    function calcularHuella() {
      const transporte = parseInt(document.getElementById("transporte").value);
      const energia = parseInt(document.getElementById("energia").value);
      const alimentacion = parseInt(document.getElementById("alimentacion").value);

      const total = transporte + energia + alimentacion;

      let mensaje = "";
      if (total <= 2) {
        mensaje = "🌱 ¡Muy bien! Tu huella de carbono es baja.";
      } else if (total <= 4) {
        mensaje = "🙂 Tu huella de carbono es moderada. ¡Puedes mejorar!";
      } else {
        mensaje = "⚠️ Tu huella de carbono es alta. ¡Revisa tus hábitos!";
      }

      document.getElementById("resultado").textContent = mensaje;
    }
  </script>
</body>
</html>
