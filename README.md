# WIND-PREMIUM
Información de jugador
<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<title>Buscador de Jugadores</title>
<style>
    body {
        font-family: Arial, sans-serif;
        background: #0d1117;
        color: #fff;
        display: flex;
        flex-direction: column;
        align-items: center;
        padding: 20px;
    }
    h1 {
        color: #00ff88;
    }
    input {
        padding: 10px;
        font-size: 16px;
        width: 300px;
        border-radius: 5px;
        border: none;
        outline: none;
        margin-bottom: 20px;
    }
    .resultado {
        background: #161b22;
        padding: 15px;
        border-radius: 8px;
        width: 350px;
        display: none;
    }
    .titulo {
        font-weight: bold;
        color: #00ff88;
    }
    .linea {
        border-top: 1px solid #444;
        margin: 10px 0;
    }
</style>
</head>
<body>

<h1>🔍 Buscador de Jugadores</h1>
<input type="text" id="busqueda" placeholder="Escribe jugador, usuario o apodo...">
<div class="resultado" id="resultado"></div>

<script>
const jugadores = [
    {
        numero: 2,
        discord: "binobeb",
        usuario: "binobeb",
        apodo: "BINOBE",
        juegos: "Ninja Legends, Muscle Legends, Legends of Speed"
    },
    {
        numero: 3,
        discord: "<@1251558795641884677>",
        usuario: "emeeme44 (soy un gato)",
        apodo: "Javi 🤙🏻🤙🏻",
        juegos: "Muscle Legends, Ninja Legends, Legends of Speed"
    },
    {
        numero: 4,
        discord: "<@934490365652791326>",
        usuario: "larrycatula20002",
        apodo: "Larrycatula 20002",
        juegos: "Ninja Legends"
    }
];

document.getElementById("busqueda").addEventListener("input", function() {
    const valor = this.value.toLowerCase();
    const resultado = document.getElementById("resultado");
    const jugador = jugadores.find(j =>
        `jugador ${j.numero}`.toLowerCase() === valor ||
        j.discord.toLowerCase().includes(valor) ||
        j.usuario.toLowerCase().includes(valor) ||
        j.apodo.toLowerCase().includes(valor)
    );

    if (jugador) {
        resultado.style.display = "block";
        resultado.innerHTML = `
            <div class="titulo">🎮 Jugador ${jugador.numero} Registrado</div>
            <div class="linea"></div>
            💬 <b>Discord:</b> ${jugador.discord}<br>
            🕹 <b>Usuario ROBLOX:</b> ${jugador.usuario}<br>
            🏷 <b>Apodo ROBLOX:</b> ${jugador.apodo}<br>
            🎯 <b>Juegos:</b> ${jugador.juegos}
        `;
    } else {
        resultado.style.display = "none";
    }
});
</script>

</body>
</html>
