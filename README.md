<!DOCTYPE html>
<html>
<head>
  <title>Login</title>
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

