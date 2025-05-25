<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Welcome, Danna</title>
  <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;600&display=swap" rel="stylesheet">
  <style>
    :root {
      --primary: #1e90ff;
      --accent: #00c6ff;
      --bg-start: #0f2027;
      --bg-end: #203a43;
      --text-light: #f0f0f0;
      --card-bg: rgba(255, 255, 255, 0.05);
    }

    body {
      margin: 0;
      font-family: 'Inter', sans-serif;
      background: linear-gradient(to bottom right, var(--bg-start), var(--bg-end));
      color: var(--text-light);
      display: flex;
      flex-direction: column;
      align-items: center;
      min-height: 100vh;
      overflow-x: hidden;
    }

    .welcome {
      font-size: 2.5rem;
      margin-top: 30vh;
      text-align: center;
      animation: fadeOut 1s ease-in-out forwards;
      animation-delay: 3s;
    }

    .menu {
      display: none;
      flex-direction: column;
      align-items: center;
      margin-top: 10vh;
      width: 100%;
      max-width: 600px;
      padding: 0 1em;
      animation: fadeIn 1s ease-in-out;
    }

    .menu a {
      background: var(--card-bg);
      color: var(--text-light);
      text-decoration: none;
      padding: 1em;
      width: 100%;
      text-align: center;
      border: 1px solid rgba(255, 255, 255, 0.2);
      border-radius: 12px;
      margin-bottom: 1em;
      font-size: 1.1rem;
      transition: all 0.3s ease;
      backdrop-filter: blur(10px);
    }

    .menu a:hover {
      background: var(--accent);
      color: #000;
      font-weight: 600;
    }

    .tab {
      display: none;
      background: rgba(0, 0, 0, 0.2);
      backdrop-filter: blur(8px);
      margin-top: 2em;
      padding: 2em;
      border-radius: 15px;
      width: 90%;
      max-width: 700px;
      animation: fadeInTab 0.5s ease;
    }

    h2 {
      color: var(--accent);
      margin-bottom: 0.5em;
    }

    ul {
      list-style-type: none;
      padding-left: 0;
    }

    ul li {
      padding: 0.3em 0;
    }

    @keyframes fadeOut {
      to {
        opacity: 0;
        visibility: hidden;
      }
    }

    @keyframes fadeIn {
      from {
        opacity: 0;
        transform: translateY(20px);
      }
      to {
        opacity: 1;
        transform: translateY(0);
      }
    }

    @keyframes fadeInTab {
      from {
        opacity: 0;
        transform: scale(0.98);
      }
      to {
        opacity: 1;
        transform: scale(1);
      }
    }

    a.button-link {
      color: var(--accent);
      text-decoration: underline;
    }
  </style>
</head>
<body>

  <div id="welcome" class="welcome">Welcome, Danna!</div>

  <div id="menu" class="menu">
    <a href="#house-rules">🏡 House Rules</a>
    <a href="#address">📍 Address & Directions</a>
    <a href="#attractions">🌟 Attractions</a>
    <a href="#restaurants">🍽️ Restaurants</a>
    <a href="#wifi">📶 Wi-Fi Info</a>
  </div>

  <div id="house-rules" class="tab">
    <h2>House Rules</h2>
    <p>Please treat the home with respect. No smoking. No parties. Quiet hours after 10PM.</p>
  </div>

  <div id="address" class="tab">
    <h2>House Address & Directions</h2>
    <p>123 Poinsettia Lane, Sunny City, ST 45678</p>
    <p><a class="button-link" href="https://maps.google.com/?q=123 Poinsettia Lane" target="_blank">Open in Maps</a></p>
  </div>

  <div id="attractions" class="tab">
    <h2>Nearby Attractions</h2>
    <ul>
      <li>🌳 Poinsettia Park – 8 min walk</li>
      <li>🏖️ Sunny Beach – 12 min drive</li>
      <li>🛍️ Downtown Market – 10 min walk</li>
    </ul>
  </div>

  <div id="restaurants" class="tab">
    <h2>Recommended Restaurants</h2>
    <ul>
      <li>🍕 Pizzeria Luca – Wood-fired pizza</li>
      <li>🍣 Sora Sushi – Modern Japanese</li>
      <li>🥗 Verde – Healthy eats and smoothies</li>
    </ul>
  </div>

  <div id="wifi" class="tab">
    <h2>Wi-Fi Information</h2>
    <p><strong>Network:</strong> Poinsettia_Guest</p>
    <p><strong>Password:</strong> welcomehome2024</p>
  </div>

  <script>
    // Welcome transition
    setTimeout(() => {
      document.getElementById("welcome").style.display = "none";
      document.getElementById("menu").style.display = "flex";
    }, 3500);

    // Tab transitions
    document.querySelectorAll('a[href^="#"]').forEach(link => {
      link.addEventListener('click', function (e) {
        e.preventDefault();
        document.querySelectorAll('.tab').forEach(tab => tab.style.display = 'none');
        const target = this.getAttribute('href');
        document.querySelector(target).style.display = 'block';
        window.scrollTo({ top: 0, behavior: 'smooth' });
      });
    });
  </script>

</body>
</html>
