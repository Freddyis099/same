      <!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">

    <title>STYNOR | Registration</title>

    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            min-height: 100vh;
            font-family: Arial, Helvetica, sans-serif;
            background: linear-gradient(135deg, #0f172a, #1d4ed8);
            display: flex;
            align-items: center;
            justify-content: center;
            padding: 20px;
        }

        .card {
            width: 100%;
            max-width: 420px;
            padding: 35px;
            background: #ffffff;
            border-radius: 20px;
            box-shadow: 0 20px 60px rgba(0, 0, 0, 0.35);
        }

        .logo {
            text-align: center;
            font-size: 32px;
            font-weight: 800;
            letter-spacing: 4px;
            color: #1d4ed8;
            margin-bottom: 8px;
        }

        .subtitle {
            text-align: center;
            color: #64748b;
            margin-bottom: 30px;
            font-size: 15px;
        }

        .input-box {
            margin-bottom: 18px;
        }

        label {
            display: block;
            margin-bottom: 7px;
            color: #334155;
            font-size: 14px;
            font-weight: 600;
        }

        input {
            width: 100%;
            height: 48px;
            padding: 0 14px;
            border: 1px solid #cbd5e1;
            border-radius: 10px;
            outline: none;
            font-size: 15px;
            color: #0f172a;
            background: #f8fafc;
            transition: 0.2s;
        }

        input:focus {
            border-color: #2563eb;
            background: #ffffff;
            box-shadow: 0 0 0 3px rgba(37, 99, 235, 0.12);
        }

        button {
            width: 100%;
            height: 50px;
            margin-top: 5px;
            border: none;
            border-radius: 10px;
            background: #2563eb;
            color: white;
            font-size: 16px;
            font-weight: 700;
            cursor: pointer;
            transition: 0.2s;
        }

        button:hover {
            background: #1d4ed8;
            transform: translateY(-1px);
        }

        #message {
            min-height: 22px;
            margin-top: 18px;
            text-align: center;
            font-size: 14px;
        }

        .footer {
            text-align: center;
            margin-top: 25px;
            color: #94a3b8;
            font-size: 12px;
        }
    </style>
</head>

<body>

    <div class="card">

        <div class="logo">STYNOR</div>

        <div class="subtitle">
            Create your account
        </div>

        <form id="registrationForm">

            <div class="input-box">
                <label for="username">Username</label>

                <input
                    type="text"
                    id="username"
                    placeholder="Enter your username"
                    required
                    minlength="3"
                >
            </div>

            <div class="input-box">
                <label for="email">Email</label>

                <input
                    type="email"
                    id="email"
                    placeholder="example@email.com"
                    required
                >
            </div>

            <div class="input-box">
                <label for="password">Password</label>

                <input
                    type="password"
                    id="password"
                    placeholder="Create a password"
                    required
                    minlength="6"
                >
            </div>

            <div class="input-box">
                <label for="confirmPassword">Confirm password</label>

                <input
                    type="password"
                    id="confirmPassword"
                    placeholder="Repeat your password"
                    required
                >
            </div>

            <button type="submit">
                Create Account
            </button>

            <div id="message"></div>

        </form>

        <div class="footer">
            STYNOR • Demo Registration
        </div>

    </div>

    <script>
        const form = document.getElementById("registrationForm");
        const message = document.getElementById("message");

        form.addEventListener("submit", function(event) {

            event.preventDefault();

            const password =
                document.getElementById("password").value;

            const confirmPassword =
                document.getElementById("confirmPassword").value;

            if (password !== confirmPassword) {
                message.textContent = "Passwords do not match.";
                message.style.color = "#dc2626";
                return;
            }

            message.textContent =
                "Registration successful!";

            message.style.color = "#16a34a";

            form.reset();
        });
    </script>

</body>
</html>
