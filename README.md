<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Oasis at Poinsettia Ave</title>
  <link href="https://fonts.googleapis.com/css2?family=Montserrat:wght@400;600&display=swap" rel="stylesheet">
  <style>
    body {
      margin: 0;
      font-family: 'Montserrat', sans-serif;
      background: linear-gradient(to bottom right, #f2f6fc, #dbe9f4);
      color: #333;
    }

    header {
      background-color: #006666;
      color: white;
      padding: 20px;
      text-align: center;
      font-size: 1.8em;
      font-weight: 600;
    }

    #welcome {
      text-align: center;
      padding: 40px 20px;
      font-size: 1.5em;
      animation: fadeOut 2s ease-in-out 3s forwards;
    }

    @keyframes fadeOut {
      to {
        opacity: 0;
        visibility: hidden;
        height: 0;
        padding: 0;
        margin: 0;
      }
    }

    .menu {
      display: none;
      flex-direction: column;
      align-items: center;
      gap: 20px;
      padding: 40px 20px;
      animation: fadeIn 1s ease-in-out forwards;
    }

    @keyframes fadeIn {
      from { opacity: 0; transform: translateY(10px); }
      to { opacity: 1; transform: translateY(0); }
    }

    .menu a {
      background-color: white;
      padding: 15px 25px;
      width: 80%;
      text-align: center;
      border-radius: 10px;
      text-decoration: none;
      color: #006666;
      font-weight: 600;
      box-shadow: 0 4px 8px rgba(0,0,0,0.1);
      transition: transform 0.2s ease, background-color 0.3s ease;
    }

    .menu a:hover {
      background-color: #e0f7f7;
      transform: scale(1.05);
    }

    .section {
      display: none;
      padding: 20px;
    }

    .back-btn {
      display: block;
      margin: 20px auto;
      text-align: center;
      background: #006666;
      color: white;
      padding: 10px 20px;
      border-radius: 5px;
      text-decoration: none;
    }
  </style>
</head>
<body>

<header>Oasis at Poinsettia Ave</header>

<div id="welcome">Welcome, Danna!</div>

<div class="menu" id="mainMenu">
  <a href="#" onclick="showSection('rules')">🏡 House Rules</a>
  <a href="#" onclick="showSection('address')">📍 Property Address</a>
  <a href="#" onclick="showSection('attractions')">🌟 Nearby Attractions</a>
  <a href="#" onclick="showSection('restaurants')">🍽️ Nearby Restaurants</a>
</div>

<div id="rules" class="section">
  <h2>House Rules</h2>
  <ul>
    <li>No smoking inside.</li>
    <li>No parties or events.</li>
    <li>Quiet hours: 10 PM - 7 AM.</li>
    <li>Checkout by 11 AM.</li>
  </ul>
  <a href="#" class="back-btn" onclick="goBack()">← Back to Menu</a>
</div>

<div id="address" class="section">
  <h2>Property Address</h2>
  <p>1234 Poinsettia Ave, Sunny City, CA 90210</p>
  <a href="#" class="back-btn" onclick="goBack()">← Back to Menu</a>
</div>

<div id="attractions" class="section">
  <h2>Nearby Attractions</h2>
  <ul>
    <li>Sunny Beach – 5 min drive</li>
    <li>City Park – 10 min walk</li>
    <li>Art Museum – 15 min drive</li>
  </ul>
  <a href="#" class="back-btn" onclick="goBack()">← Back to Menu</a>
</div>

<div id="restaurants" class="section">
  <h2>Nearby Restaurants</h2>
  <ul>
    <li>La Taqueria – 0.5 mi</li>
    <li>The Italian Place – 0.7 mi</li>
    <li>Sushi Garden – 1.2 mi</li>
  </ul>
  <a href="#" class="back-btn" onclick="goBack()">← Back to Menu</a>
</div>

<script>
  // Show menu after welcome animation
  setTimeout(() => {
    document.getElementById('mainMenu').style.display = 'flex';
  }, 3500);

  function showSection(id) {
    document.getElementById('mainMenu').style.display = 'none';
    document.querySelectorAll('.section').forEach(sec => sec.style.display = 'none');
    document.getElementById(id).style.display = 'block';
  }

  function goBack() {
    document.querySelectorAll('.section').forEach(sec => sec.style.display = 'none');
    document.getElementById('mainMenu').style.display = 'flex';
  }
</script>

</body>
</html>
