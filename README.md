from zipfile import ZipFile
import os

# Criar a estrutura do projeto da landing page
html_content = """<!DOCTYPE html>
<html lang="pt-br">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Doguinho Feliz - Doe Amor</title>
  <link href="https://fonts.googleapis.com/css2?family=Fredoka+One&display=swap" rel="stylesheet">
  <style>
    body {
      margin: 0;
      font-family: 'Fredoka One', cursive;
      background: #fff8f0;
      color: #333;
      text-align: center;
    }
    header {
      background-color: #ffb347;
      padding: 2rem 1rem;
    }
    header h1 {
      font-size: 2.5rem;
      color: white;
    }
    .hero-img {
      width: 250px;
      margin-top: 20px;
    }
    .content {
      padding: 2rem;
    }
    .content h2 {
      color: #ff7f50;
      font-size: 2rem;
    }
    .content p {
      font-size: 1.1rem;
      max-width: 600px;
      margin: 1rem auto;
      line-height: 1.6;
    }
    .btn {
      background-color: #ff7f50;
      color: white;
      padding: 1rem 2rem;
      font-size: 1.2rem;
      text-decoration: none;
      border-radius: 30px;
      display: inline-block;
      margin-top: 1.5rem;
      box-shadow: 0 4px 10px rgba(0,0,0,0.1);
      transition: background 0.3s ease;
    }
    .btn:hover {
      background-color: #e8673f;
    }
    .dog-gallery {
      display: flex;
      justify-content: center;
      flex-wrap: wrap;
      gap: 1rem;
      margin-top: 2rem;
    }
    .dog-gallery img {
      width: 150px;
      border-radius: 10px;
    }
    footer {
      background-color: #ffb347;
      color: white;
      padding: 1rem;
      margin-top: 2rem;
    }
    .meta-container {
      background: #fff3e0;
      padding: 1.5rem;
      border-radius: 20px;
      max-width: 500px;
      margin: 2rem auto;
      box-shadow: 0 2px 10px rgba(0,0,0,0.05);
    }
    .meta-container h3 {
      margin: 0 0 0.5rem 0;
      color: #e76f51;
    }
    .progress-bar {
      background-color: #ffd4b0;
      border-radius: 30px;
      overflow: hidden;
      height: 25px;
      width: 100%;
    }
    .progress-bar-fill {
      background-color: #ff7f50;
      width: 10%;
      height: 100%;
      transition: width 0.5s ease-in-out;
    }
    .meta-valores {
      margin-top: 0.5rem;
      font-size: 1rem;
      color: #555;
    }
  </style>
</head>
<body>

  <header>
    <h1>Doguinho Feliz 🐶💛</h1>
    <img src="https://cdn-icons-png.flaticon.com/512/616/616408.png" alt="Cachorro Fofo" class="hero-img">
  </header>

  <section class="content">
    <h2>Ajude um Doguinho Hoje!</h2>
    <p>
      Somos um lar temporário que cuida de cãezinhos resgatados. Com a sua ajuda, podemos garantir ração, vacinas, castração e muito amor.
    </p>
    <p>
      Qualquer valor faz diferença! Doe o quanto quiser e faça parte da transformação de vidas de peludinhos 🐾
    </p>

    <div class="meta-container">
      <h3>Meta de Doações: R$10.000 💰</h3>
      <div class="progress-bar">
        <div class="progress-bar-fill"></div>
      </div>
      <div class="meta-valores">R$1.000 arrecadado (10%)</div>
    </div>

    <a href="https://link.mercadopago.com.br/saudedez" class="btn" target="_blank">🐕 Quero Ajudar!</a>

    <div class="dog-gallery">
      <img src="https://cdn-icons-png.flaticon.com/512/616/616408.png" alt="Cachorro Cartoon 1">
      <img src="https://cdn-icons-png.flaticon.com/512/616/616408.png" alt="Cachorro Cartoon 2">
      <img src="https://cdn-icons-png.flaticon.com/512/616/616408.png" alt="Cachorro Cartoon 3">
    </div>
  </section>

  <footer>
    © 2025 Doguinho Feliz – Amor que late alto! 🐾
  </footer>

</body>
</html>
"""

# Salvar o HTML num arquivo temporário
html_file_path = "/mnt/data/index.html"
with open(html_file_path, "w", encoding="utf-8") as f:
    f.write(html_content)

# Criar o arquivo zip
zip_path = "/mnt/data/doguinho-feliz.zip"
with ZipFile(zip_path, "w") as zipf:
    zipf.write(html_file_path, arcname="index.html")

zip_path
