<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <title>Welcome Danna</title>
  <style>
    body {
      font-family: 'Segoe UI', sans-serif;
      margin: 0;
      padding: 0;
      background: #fefefe;
      color: #333;
      text-align: center;
    }

    .welcome {
      font-size: 2em;
      margin-top: 40vh;
      animation: fadeOut 2s forwards;
      animation-delay: 3s;
    }

    .menu {
      display: none;
      flex-direction: column;
      align-items: center;
      gap: 1em;
      margin-top: 20vh;
    }

    .menu a {
      display: block;
      width: 80%;
      max-width: 300px;
      background: #003366;
      color: white;
      padding: 1em;
      text-decoration: none;
      border-radius: 8px;
      font-size: 1.1em;
    }

    .tab {
      padding: 2em;
      display: none;
    }

    @keyframes fadeOut {
      to {
        opacity: 0;
        visibility: hidden;
      }
    }
  </style>
</head>
<body>

  <div id="welcome" class="welcome">Welcome, Danna!</div>

  <div id="menu" class="menu">
    <a href="#house-rules">🏡 House Rules</a>
    <a href="#address">📍 House Address & Directions</a>
    <a href="#attractions">🌟 Nearby Attractions</a>
    <a href="#restaurants">🍽️ Restaurants</a>
    <a href="#wifi">📶 Wi-Fi Info</a>
  </div>

  <div id="house-rules" class="tab">
    <h2>House Rules</h2>
    <p>No smoking, no pets, and please be respectful of neighbors.</p>
  </div>

  <div id="address" class="tab">
    <h2>House Address & Directions</h2>
    <p>123 Main St, Your City, ST 12345</p>
    <p><a href="https://maps.google.com/?q=123 Main St" target="_blank">Get Directions</a></p>
  </div>

  <div id="attractions" class="tab">
    <h2>Nearby Attractions</h2>
    <ul>
      <li>City Museum – 5 min drive</li>
      <li>Central Park – 10 min walk</li>
    </ul>
  </div>

  <div id="restaurants" class="tab">
    <h2>Nearby Restaurants</h2>
    <ul>
      <li>La Casa – Mexican Grill</li>
      <li>Joe’s Pizza – Best in town!</li>
    </ul>
  </div>

  <div id="wifi" class="tab">
    <h2>Wi-Fi Info</h2>
    <p>Network: WelcomeHome</p>
    <p>Password: enjoyyourstay123</p>
  </div>

  <script>
    // After 3.5 seconds, hide welcome and show menu
    setTimeout(() => {
      document.getElementById("welcome").style.display = "none";
      document.getElementById("menu").style.display = "flex";
    }, 3500);

    // Show tab content when linked
    document.querySelectorAll('a[href^="#"]').forEach(link => {
      link.addEventListener('click', function (e) {
        e.preventDefault();
        document.querySelectorAll('.tab').forEach(tab => tab.style.display = 'none');
        const target = this.getAttribute('href');
        document.querySelector(target).style.display = 'block';
        window.scrollTo(0, 0);
      });
    });
  </script>

</body>
</html>
