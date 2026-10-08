<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>Wishing Well</title>

<style>
  /* Magical background */
  body {
    margin: 0;
    font-family: "Segoe UI", sans-serif;
    background: radial-gradient(circle at top, #1e2533, #0f1117);
    color: #e2e8f0;
    min-height: 100vh;
    padding: 40px 20px;
    overflow-x: hidden;
  }

  /* Soft stars */
  body::before {
    content: "";
    position: fixed;
    inset: 0;
    background-image: radial-gradient(#ffffff22 1px, transparent 1px);
    background-size: 4px 4px;
    opacity: 0.25;
    pointer-events: none;
  }

  /* Header */
  .header {
    text-align: center;
    margin-bottom: 40px;
  }

  .header h1 {
    font-size: 3rem;
    letter-spacing: 0.1em;
    background: linear-gradient(135deg, #63b3ed, #9f7aea);
    -webkit-background-clip: text;
    color: transparent;
    text-shadow: 0 0 20px #63b3ed55;
  }

  /* Section container */
  section {
    max-width: 600px;
    margin: 50px auto;
    background: rgba(26, 32, 44, 0.85);
    padding: 30px;
    border-radius: 20px;
    box-shadow: 0 12px 40px rgba(0,0,0,0.6);
    backdrop-filter: blur(6px);
    animation: fadeIn 0.8s ease;
  }

  @keyframes fadeIn {
    from { opacity: 0; transform: translateY(20px); }
    to   { opacity: 1; transform: translateY(0); }
  }

  h2 {
    text-align: center;
    margin-bottom: 10px;
    font-size: 1.8rem;
    letter-spacing: 0.05em;
  }

  p {
    text-align: center;
    max-width: 550px;
    margin: 0 auto 20px;
    color: #cbd5f5;
    font-size: 1rem;
  }

  /* Buttons */
  a, button {
    display: block;
    width: 100%;
    text-align: center;
    padding: 14px 0;
    margin-top: 20px;
    border-radius: 999px;
    border: none;
    font-size: 1rem;
    font-weight: 600;
    letter-spacing: 0.05em;
    text-transform: uppercase;
    cursor: pointer;
    background: linear-gradient(135deg, #63b3ed, #9f7aea);
    color: #1a202c;
    text-decoration: none;
    box-shadow: 0 8px 18px rgba(99, 179, 237, 0.5);
    transition: transform 0.1s ease, box-shadow 0.1s ease;
  }

  a:hover, button:hover {
    transform: translateY(-2px);
    box-shadow: 0 12px 26px rgba(99, 179, 237, 0.7);
  }

  a:active, button:active {
    transform: translateY(1px);
    box-shadow: 0 4px 10px rgba(99, 179, 237, 0.5);
  }

  /* Textarea */
  textarea {
    width: 100%;
    min-height: 120px;
    border-radius: 12px;
    border: 1px solid #4a5568;
    padding: 14px;
    font-size: 1rem;
    background: #2d3748;
    color: #edf2f7;
    resize: vertical;
    outline: none;
  }

  textarea:focus {
    border-color: #63b3ed;
    box-shadow: 0 0 0 1px #63b3ed;
  }

  .note {
    font-size: 0.85rem;
    color: #9ae6b4;
    margin-top: 10px;
    text-align: center;
  }

  .message {
    margin-top: 15px;
    text-align: center;
    color: #9ae6b4;
    font-size: 0.95rem;
  }
</style>
</head>

<body>

<div class="header">
  <h1>WISH</h1>
</div>

<!-- INTRO -->
<section id="intro">
  <h2>Welcome to the Wishing Well</h2>
  <p>This is the wishing well where you can toss a symbolic coin and wish for your greatest desires.</p>
  <a href="#payment">Wish Now</a>
</section>

<!-- PAYMENT -->
<section id="payment">
  <h2>Optional Offering</h2>
  <p>You may toss a symbolic $1 coin into the well. This is optional — the magic listens either way.</p>

  <button>Pay $1</button>
  <p class="note">This offering is symbolic and not enforced.</p>

  <a href="#wish">Skip Payment</a>
</section>

<!-- WISH -->
<section id="wish">
  <h2>Make a Wish</h2>
  <p>Write your wish below and let it sink into the enchanted water.</p>

  <textarea placeholder="I wish that..."></textarea>

  <button>Toss the Coin</button>

  <p class="message">Your wish drifts softly into the well.</p>
</section>

</body>
</html>
