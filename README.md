<!DOCTYPE html>
<html lang="fr">
<head>
  <!-- Google tag (gtag.js) -->
<script async src="https://www.googletagmanager.com/gtag/js?id=G-D17R52MVJF"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag('js', new Date());

  gtag('config', 'G-D17R52MVJF');
</script>

  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Portfolio de Mor Sakho</title>
  <style>
    body {
      margin: 0;
      font-family: 'Segoe UI', sans-serif;
      background: #111;
      color: #fff;
    }
    header {
      text-align: center;
      padding: 50px 20px 20px 20px;
    }
    header h1 { color: #FFD700; margin: 0; }
    header p { font-size: 1.2rem; color: #ccc; }

    /* Slider */
    .slider {
      position: relative;
      max-width: 1000px;
      margin: 30px auto;
      overflow: hidden;
      border-radius: 15px;
      box-shadow: 0 0 20px rgba(0,0,0,0.5);
      background: #222;
    }
    .slides {
      display: flex;
      width: 300%;
      transition: transform 0.5s ease-in-out;
    }
    .slide {
      width: 100%;
      flex-shrink: 0;
      padding: 40px;
      box-sizing: border-box;
      text-align: center;
    }
    .slide h2 { color: #FFD700; margin-bottom: 15px; }
    .slide p { font-size: 1.1rem; color: #fff; }

    .nav-buttons {
      position: absolute;
      width: 100%;
      top: 50%;
      display: flex;
      justify-content: space-between;
      transform: translateY(-50%);
    }
    .nav-buttons button {
      background: rgba(0,0,0,0.5);
      border: none;
      color: #FFD700;
      font-size: 2rem;
      padding: 10px 20px;
      cursor: pointer;
      border-radius: 10px;
    }
    .dots { text-align: center; margin-top: 15px; }
    .dot {
      height: 15px; width: 15px;
      margin: 0 5px;
      background-color: #bbb;
      border-radius: 50%;
      display: inline-block;
      cursor: pointer;
    }
    .dot.active { background-color: #FFD700; }

    /* Projet */
    .project-item {
      max-width: 1000px;
      margin: 50px auto;
      background: #222;
      border-radius: 15px;
      overflow: hidden;
      box-shadow: 0 0 15px rgba(0,0,0,0.5);
      display: flex;
      flex-wrap: wrap;
    }
    .project-item img {
      width: 100%;
      max-width: 400px;
      object-fit: cover;
    }
    .project-info {
      padding: 20px;
      flex: 1;
    }
    .project-info h3 { color: #FFD700; margin-top: 0; }
    .project-info p { color: #ccc; }

    /* Contact */
    .contact {
      max-width: 600px;
      margin: 50px auto;
      text-align: center;
    }
    .contact h2 { color: #FFD700; }
    .contact p { color: #ccc; margin: 10px 0; }
    .contact a {
      color: #FFD700;
      text-decoration: none;
      font-weight: bold;
    }
    .contact a:hover { text-decoration: underline; }

    /* Responsive */
    @media(max-width:768px){
      .slides { flex-direction: column; }
      .project-item { flex-direction: column; }
      .project-item img { max-width: 100%; }
    }
  </style>
</head>
<body>

  <header>
    <h1>Mor Sakho</h1>
    <p>Développeur Web & Designer UI/UX | Création de sites vitrines et e-commerce</p>
  </header>

  <!-- Slider -->
  <div class="slider">
    <div class="slides">
      <div class="slide">
        <h2>À propos de moi</h2>
        <p>Développeur web passionné, spécialisé dans la création de sites e-commerce et vitrines modernes, avec un design responsive et une expérience utilisateur optimale.</p>
      </div>
      <div class="slide">
        <h2>Compétences</h2>
        <p>HTML5, CSS3, JavaScript (Vanilla), UI/UX Design, Intégration paiement Wave & Orange Money, WhatsApp API</p>
      </div>
      <div class="slide">
        <h2>Mon projet principal</h2>
        <p>Boutique en ligne SN-Élégance 221 : gestion du panier, paiement en ligne Wave/Orange Money et commande WhatsApp intégrés. Design moderne et responsive.</p>
      </div>
    </div>
    <div class="nav-buttons">
      <button id="prev">&#10094;</button>
      <button id="next">&#10095;</button>
    </div>
  </div>
  <div class="dots">
    <span class="dot active"></span>
    <span class="dot"></span>
    <span class="dot"></span>
  </div>

  <!-- Projet détaillé -->
  <section class="project-item">
    <img src="https://sakhomor.github.io/SN-Elegance/assets/img/home.png" alt="SN-Elegance 221 - Page d'accueil">
    <div class="project-info">
      <h3>SN-Élégance 221</h3>
      <p>Boutique en ligne moderne et responsive pour tissus Getzner. Gestion du panier, paiement Wave/Orange Money et commande WhatsApp intégrés. Design élégant et expérience utilisateur optimale.</p>
      <p>Site : <a href="https://sakhomor.github.io/SN-Elegance/" target="_blank">https://sakhomor.github.io/SN-Elegance/</a></p>
    </div>
  </section>

  <!-- Contact -->
  <section class="contact">
    <h2>Contact</h2>
    <p>Email : <a href="mailto:mamesakho34@gmail.com">mamesakho34@gmail.com</a></p>
    <p>Fiverr : <a href="https://www.fiverr.com/sakhomor" target="_blank">https://www.fiverr.com/sakhomor</a></p>
    <p>WhatsApp : <a href="https://wa.me/228784324745" target="_blank">+22 784324745</a></p>
  </section>

  <script>
    const slides = document.querySelector('.slides');
    const slide = document.querySelectorAll('.slide');
    const prev = document.getElementById('prev');
    const next = document.getElementById('next');
    const dots = document.querySelectorAll('.dot');
    let index = 0;

    function showSlide(i) {
      if(i >= slide.length) index = 0;
      if(i < 0) index = slide.length -1;
      slides.style.transform = 'translateX(' + (-index * 100) + '%)';
      dots.forEach(dot => dot.classList.remove('active'));
      dots[index].classList.add('active');
    }

    next.addEventListener('click', () => { index++; showSlide(index); });
    prev.addEventListener('click', () => { index--; showSlide(index); });
    dots.forEach((dot, i) => { dot.addEventListener('click', () => { index = i; showSlide(index); }); });

    setInterval(() => { index++; showSlide(index); }, 8000);
  </script>

</body>
</html>

