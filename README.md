<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Login Page</title>
<style>
    /* CSS Reset */
    * {
        margin: 0;
        padding: 0;
        box-sizing: border-box;
    }

    body {
        font-family: Arial, sans-serif;
        background-color: #f0f0f0;
    }

    .login-container {
        max-width: 360px;
        margin: 80px auto;
        background: #fff;
        padding: 40px;
        border-radius: 8px;
        box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
    }

    .login-container h2 {
        text-align: center;
        margin-bottom: 30px;
    }

    .form-group {
        margin-bottom: 20px;
    }

    .form-group label {
        display: block;
        font-weight: bold;
        margin-bottom: 5px;
    }

    .form-group input {
        width: 100%;
        padding: 10px;
        border: 1px solid #ccc;
        border-radius: 4px;
        font-size: 16px;
    }

    .form-group button {
        width: 100%;
        padding: 10px;
        border: none;
        border-radius: 4px;
        font-size: 16px;
        background-color: #4CAF50;
        color: white;
        cursor: pointer;
        transition: background-color 0.3s;
    }

    .form-group button:hover {
        background-color: #45a049;
    }

    .alert {
        padding: 15px;
        margin-bottom: 20px;
        border: 1px solid transparent;
        border-radius: 4px;
        color: #721c24;
        background-color: #f8d7da;
        border-color: #f5c6cb;
    }

    .alert-success {
        color: #155724;
        background-color: #d4edda;
        border-color: #c3e6cb;
    }
</style>
</head>
<body>
<div class="login-container">
    <h2>Login</h2>
    <form id="loginForm">
        <div class="form-group">
            <label for="username">Username</label>
            <input type="text" id="username" name="username" required>
        </div>
        <div class="form-group">
            <label for="password">Password</label>
            <input type="password" id="password" name="password" required>
        </div>
        <div class="form-group">
            <button type="submit">Login</button>
        </div>
    </form>
    <div id="alertMessage" class="alert" style="display: none;">
        Invalid username or password.
    </div>
</div>

<script>
    // Simulating login validation
    document.getElementById("loginForm").addEventListener("submit", function(event) {
        event.preventDefault();
        var username = document.getElementById("username").value;
        var password = document.getElementById("password").value;

        // Example validation (replace with your actual login logic)
        if (username === "admin" && password === "password") {
            showSuccessAlert();
        } else {
            showErrorAlert();
        }
    });

    function showSuccessAlert() {
        document.getElementById("alertMessage").classList.remove("alert-danger");
        document.getElementById("alertMessage").classList.add("alert-success");
        document.getElementById("alertMessage").style.display = "block";
        document.getElementById("alertMessage").textContent = "Login successful. Redirecting...";
        setTimeout(function() {
            window.location.href = "dashboard.html"; // Redirect to dashboard page
        }, 2000);
    }

    function showErrorAlert() {
        document.getElementById("alertMessage").classList.remove("alert-success");
        document.getElementById("alertMessage").classList.add("alert-danger");
        document.getElementById("alertMessage").style.display = "block";
        document.getElementById("alertMessage").textContent = "Invalid username or password.";
    }
</script>
</body>
</html>
