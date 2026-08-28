<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>STYNOR — Create Account</title>

    <style>
        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
            font-family: Arial, sans-serif;
        }

        body {
            min-height: 100vh;
            display: flex;
            justify-content: center;
            align-items: center;
            background: linear-gradient(135deg, #0f172a, #1e3a8a);
            padding: 20px;
        }

        .container {
            width: 100%;
            max-width: 420px;
            background: rgba(255, 255, 255, 0.08);
            backdrop-filter: blur(15px);
            border: 1px solid rgba(255, 255, 255, 0.15);
            border-radius: 20px;
            padding: 35px;
            color: white;
            box-shadow: 0 20px 50px rgba(0, 0, 0, 0.3);
        }

        .logo {
            text-align: center;
            font-size: 32px;
            font-weight: bold;
            letter-spacing: 3px;
            margin-bottom: 8px;
        }

        .subtitle {
            text-align: center;
            color: #cbd5e1;
            margin-bottom: 30px;
        }

        .input-group {
            margin-bottom: 18px;
        }

        label {
            display: block;
            margin-bottom: 7px;
            font-size: 14px;
            color: #e2e8f0;
        }

        input {
            width: 100%;
            padding: 14px;
            border: 1px solid rgba(255,255,255,0.2);
            border-radius: 10px;
            background: rgba(255,255,255,0.1);
            color: white;
            outline: none;
            font-size: 15px;
        }

        input::placeholder {
            color: #94a3b8;
        }

        input:focus {
            border-color: #60a5fa;
        }

        button {
            width: 100%;
            padding: 14px;
            border: none;
            border-radius: 10px;
            background: #2563eb;
            color: white;
            font-size: 16px;
            font-weight: bold;
            cursor: pointer;
            margin-top: 8px;
            transition: 0.2s;
        }

        button:hover {
            background: #1d4ed8;
            transform: translateY(-1px);
        }

        #message {
            text-align: center;
            margin-top: 18px;
            min-height: 20px;
            font-size: 14px;
        }

        .login {
            text-align: center;
            margin-top: 22px;
            color: #cbd5e1;
            font-size: 14px;
        }
    </style>
</head>

<body>

    <div class="container">

        <div class="logo">STYNOR</div>
        <div class="subtitle">Create your account</div>

        <form id="registerForm">

            <div class="input-group">
                <label for="username">Username</label>
                <input
                    type="text"
                    id="username"
                    placeholder="Enter username"
                    required
                    minlength="3"
                >
            </div>

            <div class="input-group">
                <label for="email">Email</label>
                <input
                    type="email"
                    id="email"
                    placeholder="example@email.com"
                    required
                >
            </div>

            <div class="input-group">
                <label for="password">Password</label>
                <input
                    type="password"
                    id="password"
                    placeholder="Create a password"
                    required
                    minlength="6"
                >
            </div>

            <div class="input-group">
                <label for="confirmPassword">Confirm password</label>
                <input
                    type="password"
                    id="confirmPassword"
                    placeholder="Repeat your password"
                    required
                >
            </div>

            <button type="submit">Create account</button>

            <div id="message"></div>

        </form>

        <div class="login">
            Already have an account? Sign in
        </div>

    </div>

    <script>
        const form = document.getElementById("registerForm");
        const message = document.getElementById("message");

        form.addEventListener("submit", function(event) {
            event.preventDefault();

            const username = document.getElementById("username").value.trim();
            const email = document.getElementById("email").value.trim();
            const password = document.getElementById("password").value;
            const confirmPassword =
                document.getElementById("confirmPassword").value;

            if (password !== confirmPassword) {
                message.textContent = "Passwords do not match.";
                return;
            }

            if (password.length < 6) {
                message.textContent =
                    "Password must contain at least 6 characters.";
                return;
            }

            message.textContent =
                "Registration successful! (Demo only)";

            form.reset();
        });
    </script>

</body>
</html>
