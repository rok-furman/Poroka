<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Moja Poroka</title>
    <style>
        body {
            font-family: 'Arial', sans-serif;
            text-align: center;
            background-color: #f8f8f8;
            color: #333;
            padding: 20px;
        }
        #countdown {
            font-size: 24px;
            margin-bottom: 20px;
        }
        #start-camera {
            display: inline-block;
            padding: 10px;
            background-color: #405de6; /* Instagram modra */
            color: white;
            border: none;
            border-radius: 5px;
            font-size: 16px;
            cursor: pointer;
        }
    </style>
</head>
<body>
    <h1>Dobrodošli na Naši Poročni Spletni Strani</h1>
    <p id="countdown">Čas do začetka poroke: <span id="countdown-timer"></span></p>
    <button id="start-camera" onclick="startCamera()">Začni Snemanje</button>

    <script>
        // Dodaj kodo za odštevalnik in dostop do kamere tukaj

        // Primer odštevalnika
        const weddingDate = new Date("2024-08-16T15:00:00").getTime();

        function updateCountdown() {
            const now = new Date().getTime();
            const distance = weddingDate - now;

            const days = Math.floor(distance / (1000 * 60 * 60 * 24));
            const hours = Math.floor((distance % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
            const minutes = Math.floor((distance % (1000 * 60 * 60)) / (1000 * 60));
            const seconds = Math.floor((distance % (1000 * 60)) / 1000);

            document.getElementById("countdown-timer").innerHTML = `${days}d ${hours}h ${minutes}m ${seconds}s`;
        }

        // Posodobi odštevalnik vsako sekundo
        setInterval(updateCountdown, 1000);

        // Funkcija za začetek snemanja kamere
        function startCamera() {
            // Dodaj kodo za dostop do kamere tukaj
            alert("Dostop do kamere je zdaj omogočen!");
        }
    </script>
</body>
</html>
