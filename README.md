<html lang="en">
<head>
<meta charset="UTF-8">
<title>Wishing Well</title>

<style>
  body {
    margin: 0;
    font-family: "Segoe UI", sans-serif;
    background: radial-gradient(circle at top, #1e2533, #0f1117);
    color: #e2e8f0;
    min-height: 100vh;
    padding: 40px 20px;
  }

  /* Hidden toggles */
  #goOffering,
  #goWish {
    display: none;
  }

  /* Page container */
  .page {
    max-width: 600px;
    margin: 50px auto;
    background: rgba(26, 32, 44, 0.85);
    padding: 30px;
    border-radius: 20px;
    box-shadow: 0 12px 40px rgba(0,0,0,0.6);
    display: none;
  }

  /* Show intro by default */
  #introPage {
    display: block;
  }

  /* Offering page appears when goOffering is checked */
  #goOffering:checked ~ #offeringPage {
    display: block;
  }
  #goOffering:checked ~ #introPage {
    display: none;
  }

  /* Wish page appears when goWish is checked */
  #goWish:checked ~ #wishPage {
    display: block;
  }
  #goWish:checked ~ #offeringPage {
    display: none;
  }

  h2 {
    text-align: center;
    margin-bottom: 10px;
    font-size: 1.8rem;
  }

  p {
    text-align: center;
    margin-bottom: 20px;
    color: #cbd5f5;
  }

  label, button {
    display: block;
    width: 100%;
    text-align: center;
    padding: 14px 0;
    margin-top: 20px;
    border-radius: 999px;
    border: none;
    font-size: 1rem;
    font-weight: 600;
    text-transform: uppercase;
    cursor: pointer;
    background: linear-gradient(135deg, #63b3ed, #9f7aea);
    color: #1a202c;
    text-decoration: none;
  }

  textarea {
    width: 100%;
    min-height: 120px;
    border-radius: 12px;
    border: 1px solid #4a5568;
    padding: 14px;
    background: #2d3748;
    color: #edf2f7;
  }

  .note {
    text-align: center;
    color: #9ae6b4;
    margin-top: 10px;
  }

  .message {
    text-align: center;
    margin-top: 15px;
    color: #9ae6b4;
  }
</style>
</head>

<body>

<!-- Hidden toggles -->
<input type="checkbox" id="goOffering">
<input type="checkbox" id="goWish">

<!-- PAGE 1 -->
<section id="introPage" class="page">
  <h2>Welcome to the Wishing Well</h2>
  <p>This is the wishing well where you can toss a symbolic coin and wish for your greatest desires.</p>
  <label for="goOffering">Wish Now</label>
</section>

<!-- PAGE 2 -->
<section id="offeringPage" class="page">
  <h2>Optional Offering</h2>
  <p>You may toss a symbolic $1 coin into the well. This is optional — the magic listens either way.</p>

  <button>Pay $1</button>
  <p class="note">This offering is symbolic and not enforced.</p>

  <label for="goWish">Skip Payment</label>
</section>

<!-- PAGE 3 -->
<section id="wishPage" class="page">
  <h2>Make a Wish</h2>
  <p>Write your wish below and let it sink into the enchanted water.</p>

  <textarea placeholder="I wish that..."></textarea>

  <button>Toss the Coin</button>

  <p class="message">Your wish drifts softly into the well.</p>
</section>

</body>
</html>
