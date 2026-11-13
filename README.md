<!DOCTYPE html>
<html lang="fr">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Maquette de connexion</title>

<style>
* {
  box-sizing: border-box;
}

body {
  margin: 0;
  color: white;
  font-family: Arial, sans-serif;
  background-color: #111216;
  background-image:
    linear-gradient(rgba(0,0,0,.45), rgba(0,0,0,.58)),
    url("arriere-plan.jpg");
  background-size: cover;
  background-position: center top;
  background-repeat: no-repeat;
  background-attachment: fixed;
}

header {
  background: #191a20;
  padding: 20px;
}

nav {
  display: flex;
  justify-content: flex-end;
  align-items: center;
  gap: 16px;
  flex-wrap: wrap;
}

nav a, .menu a {
  color: white;
  text-decoration: none;
}

nav a {
  font-size: 17px;
}

.primary {
  background: #345cf4;
  padding: 14px 20px;
  border-radius: 13px;
}

.menu {
  display: flex;
  justify-content: space-around;
  gap: 12px;
  width: 100%;
  padding-top: 22px;
}

main {
  padding: 40px 18px;
}

.login {
  max-width: 620px;
  margin: auto;
  background: #25262e;
  padding: 30px 24px 55px;
  border-radius: 8px;
}

h1 {
  text-align: center;
  font-size: 32px;
  margin: 4px 0 40px;
}

input {
  display: block;
  width: 100%;
  height: 75px;
  margin-bottom: 30px;
  border-radius: 22px;
  background: #343640;
  border: 1px solid #484a56;
  padding: 20px 35px;
  font-size: 20px;
  color: white;
}

button {
  cursor: pointer;
}

.login-btn {
  width: 100%;
  min-height: 65px;
  border-radius: 15px;
  font-size: 19px;
  background: transparent;
  color: white;
  border: 1px solid white;
}

.forgot {
  text-align: center;
  margin: 75px 0;
  font-size: 20px;
}

.login a {
  color: inherit;
}

hr {
  border: 0;
  border-top: 1px solid #41424b;
  margin-bottom: 55px;
}

.secondary {
  width: 100%;
  min-height: 65px;
  border-radius: 15px;
  font-size: 19px;
  background: #3a3b46;
  color: white;
  border: none;
  margin-bottom: 20px;
}

.signup {
  text-align: center;
  margin-top: 65px;
  font-size: 19px;
  line-height: 1.5;
}

.notice {
  max-width: 620px;
  margin: 14px auto 0;
  padding: 12px;
  color: #ddd;
  text-align: center;
  font-size: 14px;
  line-height: 1.5;
}

footer {
  background: #0b0c0f;
  padding: 55px 30px 25px;
}

.footer-links {
  display: flex;
  flex-wrap: wrap;
  justify-content: space-between;
  gap: 30px;
}

.footer-links a {
  color: #ddd;
  text-decoration: none;
  font-size: 18px;
}

.footer-bottom {
  border-top: 1px solid #444;
  margin-top: 100px;
  padding-top: 30px;
  display: flex;
  justify-content: space-between;
  align-items: center;
  flex-wrap: wrap;
  gap: 20px;
  color: #ccc;
  font-size: 13px;
}

.language {
  width: auto;
  padding: 15px 25px;
  background: transparent;
  border: 1px solid #777;
  border-radius: 12px;
  color: white;
  font-size: 16px;
}

.floating-help {
  position: fixed;
  right: 18px;
  bottom: 18px;
  width: 65px;
  height: 65px;
  border-radius: 50%;
  background: #345cf4;
  color: white;
  border: none;
  font-size: 30px;
  z-index: 10;
}

@media(max-width: 480px) {
  .login {
    padding: 25px 18px 45px;
  }

  .menu {
    font-size: 14px;
  }

  .footer-links {
    gap: 25px;
  }

  .footer-bottom {
    margin-top: 65px;
  }
}
</style>
</head>

<body>

<header>
  <nav>
    <a class="primary" href="#creer">Créer un compte</a>
    <a href="#connexion">Connexion</a>
    <a href="#recherche">⌕</a>
  </nav>

  <div class="menu">
    <a href="#decouvrir">Découvrir</a>
    <a href="#catalogue">Catalogue</a>
    <a href="#creer">Créer</a>
    <a href="#credits">Crédits</a>
  </div>
</header>

<main>
  <section class="login" id="connexion">

    <h1>Connexion</h1>

    <form id="demoForm">
      <input type="text"
        placeholder="Identifiant / E-mail"
        autocomplete="off">

      <input type="password"
        placeholder="Mot de passe"
        autocomplete="off">

      <button class="login-btn" type="submit">
        Connexion
      </button>
    </form>

    <p class="forgot">
      <a href="#aide">Mot de passe ou identifiant oublié ?</a>
    </p>

    <hr>

    <button class="secondary" type="button">
      Recevoir un code par e-mail
    </button>

    <button class="secondary" type="button">
      Connexion rapide
    </button>

    <button class="secondary" type="button">
      Autres options de connexion
    </button>

    <p class="signup">
      Vous n'avez pas de compte ?
      <a href="#creer">Créer un compte</a>
    </p>

  </section>

  <p class="notice">
    Maquette de démonstration non officielle.
    Ne saisis pas de vrai mot de passe sur cette page.
  </p>
</main>

<footer>

  <div class="footer-links">
    <a href="#apropos">À propos</a>
    <a href="#emplois">Emplois</a>
    <a href="#presse">Presse</a>
    <a href="#parents">Parents</a>
    <a href="#cadeaux">Cartes-cadeaux</a>
    <a href="#aide">Aide</a>
    <a href="#conditions">Conditions</a>
    <a href="#accessibilite">Accessibilité</a>
    <a href="#confidentialite">Confidentialité</a>
    <a href="#preferences">Préférences de confidentialité</a>
    <a href="#sitemap">Plan du site</a>
    <a href="#cookies">Options des cookies</a>
  </div>

  <div class="footer-bottom">
    <button class="language">Français　⌄</button>
    <span>© 2026 Exemple — Maquette de démonstration</span>
  </div>

</footer>

<button class="floating-help" aria-label="Aide">?</button>

<script>
document.getElementById("demoForm")
.addEventListener("submit", function(event) {
  event.preventDefault();
  alert("Maquette de démonstration uniquement.");
});
</script>

</body>
</html>
