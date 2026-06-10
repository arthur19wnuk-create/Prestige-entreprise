# Prestige-entreprise
<!DOCTYPE html>
<html lang="fr">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Prestige Entreprise</title>
<link href="https://fonts.googleapis.com/css2?family=Montserrat:wght@400;700;900&family=Inter:wght@300;400;500&display=swap" rel="stylesheet">
<style>
  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

  :root {
    --black: #0a0a0a;
    --dark: #111111;
    --card: #161616;
    --gold: #c9a84c;
    --gold-light: #e6c96e;
    --white: #f5f5f5;
    --muted: #888;
  }

  body {
    font-family: 'Inter', sans-serif;
    background: var(--black);
    color: var(--white);
    overflow-x: hidden;
  }

  header {
    position: relative;
    height: 100vh;
    min-height: 600px;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    text-align: center;
    overflow: hidden;
  }

  .hero-bg {
    position: absolute;
    inset: 0;
    background-image: url('https://images.unsplash.com/photo-1507003211169-0a1dd7228f2d?w=1600&q=80');
    background-size: cover;
    background-position: center;
    filter: brightness(0.25);
  }

  .hero-content { position: relative; z-index: 1; padding: 20px; }

  .eyebrow {
    font-size: 11px;
    letter-spacing: 4px;
    text-transform: uppercase;
    color: var(--gold);
    margin-bottom: 20px;
  }

  h1 {
    font-family: 'Montserrat', sans-serif;
    font-weight: 900;
    font-size: clamp(42px, 8vw, 88px);
    line-height: 1;
    letter-spacing: -2px;
    margin-bottom: 24px;
  }

  .hero-sub {
    font-size: 15px;
    color: #aaa;
    letter-spacing: 1px;
    margin-bottom: 40px;
  }

  .btn-gold {
    display: inline-block;
    background: var(--gold);
    color: #000;
    padding: 14px 32px;
    border-radius: 4px;
    text-decoration: none;
    font-family: 'Montserrat', sans-serif;
    font-weight: 700;
    font-size: 13px;
    letter-spacing: 1.5px;
    text-transform: uppercase;
    transition: background 0.2s, transform 0.2s;
  }
  .btn-gold:hover { background: var(--gold-light); transform: translateY(-2px); }

  section {
    padding: 90px 24px;
    max-width: 1180px;
    margin: auto;
  }

  .section-label {
    font-size: 10px;
    letter-spacing: 4px;
    text-transform: uppercase;
    color: var(--gold);
    margin-bottom: 12px;
  }

  h2 {
    font-family: 'Montserrat', sans-serif;
    font-weight: 900;
    font-size: clamp(28px, 5vw, 48px);
    letter-spacing: -1px;
    margin-bottom: 50px;
  }

  .cards {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
    gap: 20px;
  }

  .card {
    background: var(--card);
    overflow: hidden;
    border-radius: 8px;
  }

  .card-img-wrap {
    height: 260px;
    overflow: hidden;
    background: #1a1a1a;
  }

  .card-img-wrap img {
    width: 100%;
    height: 100%;
    object-fit: cover;
    display: block;
    transition: transform 0.5s ease;
    filter: brightness(0.8) saturate(0.7);
  }

  .card:hover .card-img-wrap img { transform: scale(1.05); }

  .card-body { padding: 28px 24px 32px; }

  .card-body h3 {
    font-family: 'Montserrat', sans-serif;
    font-weight: 700;
    font-size: 18px;
    margin-bottom: 8px;
  }

  .card-body p { font-size: 14px; color: var(--muted); line-height: 1.6; }

  .card-price {
    display: inline-block;
    margin-top: 14px;
    font-family: 'Montserrat', sans-serif;
    font-weight: 900;
    font-size: 22px;
    color: var(--gold);
  }

  .divider {
    border: none;
    border-top: 1px solid #222;
    max-width: 1180px;
    margin: 0 auto;
  }

  .reviews-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
    gap: 20px;
  }

  .review-card {
    background: var(--card);
    border: 1px solid #222;
    border-radius: 12px;
    padding: 28px 24px;
  }

  .stars { color: var(--gold); font-size: 18px; margin-bottom: 14px; letter-spacing: 2px; }

  .review-text {
    font-size: 14px;
    color: #bbb;
    line-height: 1.7;
    margin-bottom: 20px;
    font-style: italic;
  }

  .reviewer { display: flex; align-items: center; gap: 12px; }

  .reviewer-avatar {
    width: 40px;
    height: 40px;
    border-radius: 50%;
    background: #2a2a2a;
    display: flex;
    align-items: center;
    justify-content: center;
    font-family: 'Montserrat', sans-serif;
    font-weight: 700;
    font-size: 15px;
    color: var(--gold);
    flex-shrink: 0;
  }

  .reviewer-name { font-weight: 600; font-size: 14px; }
  .reviewer-service { font-size: 12px; color: var(--muted); margin-top: 2px; }

  .review-form {
    background: var(--card);
    border: 1px solid #222;
    border-radius: 12px;
    padding: 36px;
    max-width: 620px;
    margin: 50px auto 0;
  }

  .review-form h3 {
    font-family: 'Montserrat', sans-serif;
    font-weight: 700;
    font-size: 20px;
    margin-bottom: 24px;
  }

  .star-select {
    display: flex;
    gap: 8px;
    margin-bottom: 20px;
    flex-direction: row-reverse;
    justify-content: flex-end;
  }

  .star-select input { display: none; }

  .star-select label {
    font-size: 32px;
    color: #333;
    cursor: pointer;
    transition: color 0.15s;
  }

  .star-select label:hover,
  .star-select label:hover ~ label,
  .star-select input:checked ~ label { color: var(--gold); }

  .form-group { margin-bottom: 16px; }

  .form-group label {
    display: block;
    font-size: 12px;
    letter-spacing: 1px;
    text-transform: uppercase;
    color: var(--muted);
    margin-bottom: 8px;
  }

  .form-group input,
  .form-group textarea,
  .form-group select {
    width: 100%;
    background: #1a1a1a;
    border: 1px solid #2a2a2a;
    border-radius: 6px;
    color: var(--white);
    font-family: 'Inter', sans-serif;
    font-size: 14px;
    padding: 12px 14px;
    outline: none;
    transition: border-color 0.2s;
  }

  .form-group input:focus,
  .form-group textarea:focus,
  .form-group select:focus { border-color: var(--gold); }

  .form-group select option { background: #1a1a1a; }
  .form-group textarea { height: 100px; resize: vertical; }

  .btn-submit {
    width: 100%;
    background: var(--gold);
    color: #000;
    border: none;
    padding: 14px;
    border-radius: 6px;
    font-family: 'Montserrat', sans-serif;
    font-weight: 700;
    font-size: 13px;
    letter-spacing: 1.5px;
    text-transform: uppercase;
    cursor: pointer;
    margin-top: 8px;
    transition: background 0.2s;
  }

  .btn-submit:hover { background: var(--gold-light); }

  .success-msg {
    display: none;
    text-align: center;
    padding: 20px;
    color: var(--gold);
    font-size: 15px;
  }

  .contact-grid {
    display: grid;
    grid-template-columns: 1fr;
    gap: 60px;
    max-width: 700px;
    margin: auto;
  }

  .contact-item {
    display: flex;
    align-items: center;
    gap: 16px;
    padding: 20px 0;
    border-bottom: 1px solid #1e1e1e;
  }

  .contact-icon {
    width: 44px;
    height: 44px;
    border-radius: 50%;
    background: #1c1c1c;
    border: 1px solid #2a2a2a;
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 18px;
    flex-shrink: 0;
  }

  .contact-text { font-size: 14px; color: var(--muted); }
  .contact-text strong { display: block; color: var(--white); font-size: 16px; margin-bottom: 2px; }

  footer {
    border-top: 1px solid #1a1a1a;
    padding: 32px 24px;
    text-align: center;
    font-size: 12px;
    color: #444;
    letter-spacing: 1px;
  }

  footer span { color: var(--gold); }
</style>
</head>
<body>

<header>
  <div class="hero-bg"></div>
  <div class="hero-content">
    <p class="eyebrow">Services professionnels • Québec</p>
    <h1>Prestige<br>Entreprise</h1>
    <p class="hero-sub">Lavage de voitures &nbsp;·&nbsp; Lavage de poubelles &nbsp;·&nbsp; Tonte de gazon</p>
    <a class="btn-gold" href="#contact">Demander une soumission</a>
  </div>
</header>

<section>
  <p class="section-label">Ce qu'on fait</p>
  <h2>Nos services</h2>
  <div class="cards">

    <div class="card">
      <div class="card-img-wrap">
        <img style="object-position: center 20%;" src="data:image/jpeg;base64,/9j/4AAQSkZJRgABAQAAkACQAAD/4QECRXhpZgAATU0AKgAAAAgABwEOAAIAAAALAAAAYgESAAMAAAABAAEAAAEaAAUAAAABAAAAbgEbAAUAAAABAAAAdgEoAAMAAAABAAIAAAEyAAIAAAAUAAAAfodpAAQAAAABAAAAkgAAAABTY3JlZW5zaG90AAAAAACQAAAAAQAAAJAAAAABMjAyNjowNjoxMCAxNzoyMToxNwAABZADAAIAAAAUAAAA1JKGAAcAAAASAAAA6KABAAMAAAABAAEAAKACAAQAAAABAAADfqADAAQAAAABAAADYQAAAAAyMDI2OjA2OjEwIDE3OjIxOjE3AEFTQ0lJAAAAU2NyZWVuc2hvdP/tAG5QaG90b3Nob3AgMy4wADhCSU0EBAAAAAAANhwBWgADGyVHHAIAAAIAAhwCeAAKU2NyZWVuc2hvdBwCPAAGMTcyMTE3HAI3AAgyMDI2MDYxMDhCSU0EJQAAAAAAEHOaeu+MwNiuUqYonMHvIR3/wAARCANhA34DASIAAhEBAxEB/8QAHwAAAQUBAQEBAQEAAAAAAAAAAAECAwQFBgcICQoL/8QAtRAAAgEDAwIEAwUFBAQAAAF9AQIDAAQRBRIhMUEGE1FhByJxFDKBkaEII0KxwRVS0fAkM2JyggkKFhcYGRolJicoKSo0NTY3ODk6Q0RFRkdISUpTVFVWV1hZWmNkZWZnaGlqc3R1dnd4eXqDhIWGh4iJipKTlJWWl5iZmqKjpKWmp6ipqrKztLW2t7i5usLDxMXGx8jJytLT1NXW19jZ2uHi4+Tl5ufo6erx8vP09fb3+Pn6/8QAHwEAAwEBAQEBAQEBAQAAAAAAAAECAwQFBgcICQoL/8QAtREAAgECBAQDBAcFBAQAAQJ3AAECAxEEBSExBhJBUQdhcRMiMoEIFEKRobHBCSMzUvAVYnLRChYkNOEl8RcYGRomJygpKjU2Nzg5OkNERUZHSElKU1RVVldYWVpjZGVmZ2hpanN0dXZ3eHl6goOEhYaHiImKkpOUlZaXmJmaoqOkpaanqKmqsrO0tba3uLm6wsPExcbHyMnK0tPU1dbX2Nna4uPk5ebn6Onq8vP09fb3+Pn6/9sAQwACAgICAgIDAgIDBQMDAwUGBQUFBQYIBgYGBgYICggICAgICAoKCgoKCgoKDAwMDAwMDg4ODg4PDw8PDw8PDw8P/9sAQwECAwMEBAQHBAQHEAsJCxAQEBAQEBAQEBAQEBAQEBAQEBAQEBAQEBAQEBAQEBAQEBAQEBAQEBAQEBAQEBAQEBAQ/90ABAA4/9oADAMBAAIRAxEAPwDzPVPCfxJupGv9Y8H6X4ytcbvtejyyLMR67QY1z/wGubjn0TTnkm0nU9c8D6lbY/d38a+QCTjG5GLY/A1+v2v/ALDXweumS48FPd+E7mMYQ2j74x3+7Jux+deNeKv2WPjxpqyWmh6xpni3TFUAw6gjJK4HYlQFz+NfmsZ1on7TDM8BiNJOz89D4r0vxn4/isWi1DT9L8b25JLSxDc7L/tBgDmuN1q1/Zy8UsE8b+BJNDvicNLZbkYH1++B19q9N8YfBceGNWn1D4ifDi/0OKONWN3pY8yIPnkhjIwx9RWBbWlvIZJvBHjyP7K0akWWrxqFwxxjMUefxzXowxklubyy+jUXNB3OJtPhJZLDv+D/AMSH02P+Gz1fBU+gBUORWXqUPx98CusnjPwjb+JtNA3fbdHlLsV9SjbefwrptQ8AeIdPhk1LxL4KS9hMxC3eiSEsVJ4bEsgBB7cVzK6nHp+qnT/D/iO50W5U82utIQBjsDEGB/SvUpY9Lc8etl
