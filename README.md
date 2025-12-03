<!DOCTYPE html>
<html lang="it">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Fiocchi & Artigianato</title>
  <link href="https://fonts.googleapis.com/css2?family=Great+Vibes&family=Roboto:wght@400;700&display=swap" rel="stylesheet">
  <style>
    body {
      font-family: 'Roboto', sans-serif;
      margin: 0;
      padding: 0;
      background-color: #fff8f0;
      color: #333;
      overflow-x: hidden;
      scroll-behavior: smooth;
      position: relative;
    }

    /* Neve */
    .snowflake {
      position: fixed;
      top: -10px;
      color: white;
      font-size: 1em;
      user-select: none;
      pointer-events: none;
      z-index: 9999;
      animation-name: fall;
      animation-timing-function: linear;
      animation-iteration-count: infinite;
    }

    @keyframes fall {
      0% { transform: translateY(0) rotate(0deg); }
      100% { transform: translateY(110vh) rotate(360deg); }
    }

    header {
      background: linear-gradient(90deg, #c94f4f, #ff7f50);
      color: white;
      padding: 30px 20px;
      text-align: center;
      position: sticky;
      top: 0;
      z-index: 1000;
    }
    header h1 {
      font-family: 'Great Vibes', cursive;
      font-size: 3em;
      margin: 0;
    }
    nav {
      margin-top: 10px;
      display: flex;
      justify-content: center;
      gap: 25px;
      flex-wrap: wrap;
    }
    nav a {
      color: white;
      text-decoration: none;
      font-weight: bold;
      transition: transform 0.2s;
    }
    nav a:hover {
      transform: scale(1.1);
    }
    section {
      padding: 60px 20px;
      text-align: center;
    }
    section h2 {
      font-size: 2.5em;
      margin-bottom: 20px;
      color: #c94f4f;
    }
    .products {
      display: flex;
      flex-wrap: wrap;
      justify-content: center;
      gap: 25px;
    }
    .product-card {
      background-color: #fff;
      border-radius: 15px;
      width: 280px;
      padding: 15px;
      box-shadow: 0 6px 15px rgba(0,0,0,0.1);
      transition: transform 0.3s, box-shadow 0.3s;
      opacity: 0;
      transform: translateY(30px);
      animation: fadeInUp 0.8s forwards;
    }
    .product-card:hover {
      transform: translateY(-10px);
      box-shadow: 0 10px 25px rgba(0,0,0,0.2);
    }
    .product-card img {
      width: 100%;
      border-radius: 15px;
    }
    footer {
      background-color: #c94f4f;
      color: white;
      text-align: center;
      padding: 25px 20px;
    }
    form {
      max-width: 500px;
      margin: 0 auto;
    }
    input, textarea, button {
      padding: 12px;
      margin: 8px 0;
      width: 100%;
      border-radius: 8px;
      border: 1px solid #ccc;
      font-size: 1em;
    }
    button {
      background-color: #ff7f50;
      color: white;
      border: none;
      cursor: pointer;
      transition: background 0.3s;
    }
    button:hover {
      background-color: #c94f4f;
    }
    /* Animazione entrata prodotti */
    .product-card:nth-child(1){ animation-delay: 0.1s; }
    .product-card:nth-child(2){ animation-delay: 0.3s; }
    .product-card:nth-child(3){ animation-delay: 0.5s; }

    @keyframes fadeInUp {
      to {
        opacity: 1;
        transform: translateY(0);
      }
    }

    @media(max-width: 768px){
      .products {
        flex-direction: column;
        align-items: center;
      }
    }
  </style>
</head>
<body>

  <header>
    <h1>Fiocchi & Artigianato</h1>
    <nav>
      <a href="#home">Home</a>
      <a href="#prodotti">Prodotti</a>
      <a href="#chi-siamo">Chi Siamo</a>
      <a href="#contatti">Contatti</a>
    </nav>
  </header>

  <section id="home">
    <h2>Benvenuti nel nostro mondo artigianale</h2>
    <p>Scoprite fiocchi, articoli natalizi, fiocchi nascita e centrotavola realizzati a mano con passione e amore.</p>
  </section>

  <section id="prodotti">
    <h2>I nostri prodotti</h2>
    <div class="products">
      <div class="product-card">
        <img src="https://via.placeholder.com/280x200?text=Fiocco+Nascita" alt="Fiocco Nascita">
        <h3>Fiocco Nascita</h3>
      </div>
      <div class="product-card">
        <img src="https://via.placeholder.com/280x200?text=Articoli+Natalizi" alt="Articoli Natalizi">
        <h3>Articoli Natalizi</h3>
      </div>
      <div class="product-card">
        <img src="https://via.placeholder.com/280x200?text=Centrotavola" alt="Centrotavola">
        <h3>Centrotavola</h3>
      </div>
    </div>
  </section>

  <section id="chi-siamo">
    <h2>Chi Siamo</h2>
    <p>Siamo un laboratorio artigianale specializzato nella creazione di fiocchi, decorazioni natalizie e centrotavola unici. Ogni pezzo è realizzato a mano con cura e passione, per rendere speciali i vostri momenti più belli.</p>
  </section>

  <section id="contatti">
    <h2>Contattaci</h2>
    <form>
      <input type="text" placeholder="Nome" required>
      <input type="email" placeholder="Email" required>
      <textarea placeholder="Messaggio" rows="4" required></textarea>
      <button type="submit">Invia</button>
    </form>
  </section>

  <footer>
    <p>&copy; 2025 Fiocchi & Artigianato. Tutti i diritti riservati.</p>
  </footer>

  <!-- Neve -->
  <script>
    const numberOfSnowflakes = 50;
    for(let i=0; i<numberOfSnowflakes; i++){
      const snowflake = document.createElement('div');
      snowflake.classList.add('snowflake');
      snowflake.style.left = Math.random() * 100 + 'vw';
      snowflake.style.fontSize = (Math.random() * 10 + 10) + 'px';
      snowflake.style.animationDuration = (Math.random() * 5 + 5) + 's';
      snowflake.style.opacity = Math.random();
      snowflake.innerHTML = '❄';
      document.body.appendChild(snowflake);
    }
  </script>
</body>
</html>
