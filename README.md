<!DOCTYPE html>
<html>
<head>
  <title>Login</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background-color: #f4f4f4;
      text-align: center;
    }

    h2 {
      color: #333;
    }

    form {
      margin: 0 auto;
      width: 300px;
      background-color: #fff;
      padding: 20px;
      border-radius: 10px;
      box-shadow: 0px 0px 10px rgba(0, 0, 0, 0.1);
    }

    label {
      display: block;
      margin-bottom: 5px;
      text-align: left;
    }

    input[type="text"],
    input[type="password"] {
      width: calc(100% - 12px);
      padding: 8px;
      margin-bottom: 15px;
      border: 1px solid #ccc;
      border-radius: 5px;
    }

    input[type="button"] {
      background-color: #007bff;
      color: #fff;
      border: none;
      padding: 10px 20px;
      border-radius: 5px;
      cursor: pointer;
    }

    input[type="button"]:hover {
      background-color: #0056b3;
    }

  </style>
</head>
<body>
  <h2>Login</h2>
  <form id="loginForm">
    <label for="username">Usuario:</label>
    <input type="text" id="username" name="username" required><br><br>
    <label for="password">Contraseña:</label>
    <input type="password" id="password" name="password" required><br><br>
    <input type="button" value="Iniciar sesión" onclick="validateForm()">
  </form>

  <script>
    function validateForm() {
      var username = document.getElementById('username').value;
      var password = document.getElementById('password').value;

      // Reemplaza estos valores con tus propios datos de usuario y contraseña
      var correctUsername = 'camilo';
      var correctPassword = 'camilo';

      if (username === correctUsername && password === correctPassword) {
        window.location.href = 'https://sites.google.com/view/descarga-certificados/eliminar-cursos?authuser=0';  // Reemplaza con la URL de la página de destino
      } else {
        alert('Usuario o contraseña incorrectos');
      }
    }
  </script>
</body>
</html>
