<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>C&CR Industrial S.A.S. - Portal de Usuario</title>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Orbitron:wght@400;700&display=swap');

        body {
            font-family: 'Orbitron', sans-serif;
            margin: 0;
            height: 100vh;
            display: flex;
            justify-content: center;
            align-items: center;
            background: #ffffff;
            overflow: hidden;
            color: #333;
        }

        .background {
            position: absolute;
            width: 100%;
            height: 100%;
            background: linear-gradient(135deg, #ff0000, #ffffff);
            clip-path: circle(90% at right 70%);
            animation: moveBackground 6s infinite alternate;
        }

        @keyframes moveBackground {
            to {
                clip-path: circle(90% at left 70%);
            }
        }

        .container {
            position: relative;
            background: rgba(255, 255, 255, 0.9);
            padding: 180px; /* Aumenta el padding */
            border-radius: 15px;
            box-shadow: 0 0 30px rgba(0, 0, 0, 0.1);
            text-align: center;
            max-width: 1500px; /* Aumenta el ancho máximo */
            width: 100%;
            z-index: 1;
        }

        .logo {
            max-width: 750px; /* Aumenta el tamaño máximo del logo */
            margin-bottom: 90px; /* Aumenta el margen inferior */
        }

        input {
            width: 100%;
            padding: 48px; /* Aumenta el padding */
            margin-bottom: 60px; /* Aumenta el margen inferior */
            border: 1px solid #ddd;
            border-radius: 5px;
            box-sizing: border-box;
            background-color: #f0f0f0;
            color: #333;
            font-size: 54px; /* Aumenta el tamaño de la fuente */
        }

        button {
            width: 100%;
            padding: 48px; /* Aumenta el padding */
            background-color: #ff0000;
            color: white;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            font-size: 54px; /* Aumenta el tamaño de la fuente */
            margin-bottom: 45px; /* Aumenta el margen inferior */
            transition: background-color 0.3s, transform 0.3s;
        }

        button:hover {
            background-color: #cc0000;
            transform: scale(1.05);
        }

        #error-message {
            color: red;
            margin-bottom: 45px; /* Aumenta el margen inferior */
            font-size: 54px; /* Aumenta el tamaño de la fuente */
        }

        #success-message {
            color: green;
            margin-bottom: 45px; /* Aumenta el margen inferior */
            font-size: 54px; /* Aumenta el tamaño de la fuente */
        }

        #logoutButton {
            background-color: #007bff;
        }

        #logoutButton:hover {
            background-color: #0056b3;
        }

        h2 {
            margin-bottom: 90px; /* Aumenta el margen inferior */
            font-size: 72px; /* Aumenta el tamaño de la fuente */
        }

        .clock-container {
            position: absolute;
            top: 90px; /* Aumenta la posición desde la parte superior */
            right: 90px; /* Aumenta la posición desde la derecha */
            color: #ff0000;
            text-align: right;
            font-size: 66px; /* Aumenta el tamaño de la fuente */
            z-index: 2;
        }

        .clock-container span {
            display: block;
        }

    </style>
</head>
<body>
    <div class="background"></div>
    <div class="clock-container">
        <span id="date"></span>
        <span id="time"></span>
    </div>
    <div class="container">
        <img src="https://www.ccrindustrial.com.co/wp-content/uploads/elementor/thumbs/logo-ccr-ouhzwt6nhfjaels3q1k11op0gb6ek6vspxad2oewwc.png" alt="C&CR Industrial S.A.S. Logo" class="logo">
        
        <div id="loginForm">
            <h2>Iniciar Sesión</h2>
            <div id="message"></div>
            <form id="login-form">
                <input type="text" id="username" placeholder="Usuario" required>
                <input type="password" id="password" placeholder="Contraseña" required>
                <button type="submit">Iniciar Sesión</button>
            </form>
        </div>
        
        <div id="logoutSection" style="display: none;">
            <h2>Sesión Iniciada</h2>
            <p>Has iniciado sesión correctamente.</p>
            <button id="logoutButton" onclick="logout()">Cerrar Sesión</button>
        </div>
    </div>

    <script>
        document.getElementById('login-form').addEventListener('submit', function(e) {
            e.preventDefault();
            const username = document.getElementById('username').value;
            const password = document.getElementById('password').value;
            
            if (username === 'ADMIN2024' && password === 'Colombia2024*') {
                // Credenciales correctas
                sessionStorage.setItem('loggedIn', 'true');
                document.getElementById('loginForm').style.display = 'none';
                document.getElementById('logoutSection').style.display = 'block';
                document.getElementById('message').textContent = '';
                window.location.href = 'https://sites.google.com/view/descarga-certificados/administrador';
            } else {
                // Credenciales incorrectas, mostrar error
                document.getElementById('message').textContent = 'Usuario o contraseña incorrectos';
                document.getElementById('message').style.color = 'red';
            }
        });

        function logout() {
            sessionStorage.removeItem('loggedIn');
            document.getElementById('loginForm').style.display = 'block';
            document.getElementById('logoutSection').style.display = 'none';
            document.getElementById('message').textContent = 'Sesión cerrada correctamente.';
            document.getElementById('message').style.color = 'green';
            document.getElementById('username').value = '';
            document.getElementById('password').value = '';
        }

        // Verificar si el usuario está logueado al cargar la página
        window.onload = function() {
            if (sessionStorage.getItem('loggedIn') === 'true') {
                window.location.href = 'https://sites.google.com/view/descarga-certificados/administrador';
            }
            updateTime();
            setInterval(updateTime, 1000);
        }

        function updateTime() {
            const now = new Date();
            const time = now.toLocaleTimeString('es-ES', { hour: '2-digit', minute: '2-digit', second: '2-digit' });
            document.getElementById('time').textContent = time;
        }
    </script>
</body>
</html>




