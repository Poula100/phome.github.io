<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <title>Wishing Well</title>
  <style>
    body {
      margin: 0;
      font-family: system-ui, sans-serif;
      background: radial-gradient(circle at top, #2b6cb0 0, #1a202c 45%, #000 100%);
      color: #f7fafc;
      display: flex;
      flex-direction: column;
      align-items: center;
      min-height: 100vh;
    }

    header {
      text-align: center;
      padding: 40px 20px 10px;
    }

    header h1 {
      margin: 0;
      font-size: 2.5rem;
      letter-spacing: 0.08em;
      text-transform: uppercase;
    }

    header p {
      margin-top: 10px;
      max-width: 500px;
      font-size: 0.95rem;
      color: #cbd5f5;
    }

    .well-container {
      margin-top: 20px;
      display: flex;
      flex-direction: column;
      align-items: center;
    }

    /* Simple “well” illustration */
    .well {
      position: relative;
      width: 260px;
      height: 260px;
      margin-bottom: 25px;
    }

    .well-base {
      position: absolute;
      bottom: 0;
      left: 50%;
      transform: translateX(-50%);
      width: 220px;
      height: 90px;
      background: #4a5568;
      border-radius: 0 0 120px 120px;
      box-shadow: 0 0 20px rgba(0, 0, 0, 0.6);
      overflow: hidden;
    }

    .well-stones {
      position: absolute;
      inset: 0;
      background-image: radial-gradient(circle, #a0aec0 10%, transparent 11%);
      background-size: 22px 22px;
      opacity: 0.4;
    }

    .water {
      position: absolute;
      bottom: 0;
      left: 50%;
      transform: translateX(-50%);
      width: 180px;
      height: 40px;
      background: radial-gradient(circle at 30% 0, #63b3ed, #2b6cb0);
      border-radius: 50%;
      box-shadow: 0 0 12px rgba(99, 179, 237, 0.7);
      animation: ripple 4s infinite ease-in-out;
    }

    @keyframes ripple {
      0%   { transform: translateX(-50%) scaleX(1); opacity: 1; }
      50%  { transform: translateX(-50%) scaleX(1.05); opacity: 0.9; }
      100% { transform: translateX(-50%) scaleX(1); opacity: 1; }
    }

    .roof {
      position: absolute;
      top: 40px;
      left: 50%;
      transform: translateX(-50%);
      width: 240px;
      height: 40px;
      background: linear-gradient(135deg, #742a2a, #9b2c2c);
      border-radius: 6px 6px 0 0;
      box-shadow: 0 6px 12px rgba(0, 0, 0, 0.5);
    }

    .posts {
      position: absolute;
      top: 80px;
      left: 50%;
      transform: translateX(-50%);
      width: 200px;
      display: flex;
      justify-content: space-between;
    }

    .post {
      width: 16px;
      height: 90px;
      background: linear-gradient(to bottom, #cbd5e0, #718096);
      border-radius: 8px;
    }

    .bucket-rope {
      position: absolute;
      top: 80px;
      left: 50%;
      transform: translateX(-50%);
      width: 2px;
      height: 70px;
      background: #e2e8f0;
    }

    .bucket {
      position: absolute;
      top: 140px;
      left: 50%;
      transform: translateX(-50%);
      width: 40px;
      height: 35px;
      background: linear-gradient(to bottom, #ecc94b, #b7791f);
      border-radius: 0 0 10px 10px;
      box-shadow: 0 4px 8px rgba(0, 0, 0, 0.4);
    }

    .wish-panel {
      background: rgba(26, 32, 44, 0.9);
      border-radius: 16px;
      padding: 20px 24px;
      max-width: 420px;
      box-shadow: 0 12px 30px rgba(0, 0, 0, 0.7);
      backdrop-filter: blur(6px);
    }

    .wish-panel h2 {
      margin: 0 0 10px;
      font-size: 1.3rem;
    }

    .wish-panel p {
      margin: 0 0 16px;
      font-size: 0.9rem;
      color: #e2e8f0;
    }

    .wish-panel textarea {
      width: 100%;
      min-height: 80px;
      border-radius: 10px;
      border: 1px solid #4a5568;
      padding: 10px;
      font-family: inherit;
      font-size: 0.95rem;
      resize: vertical;
      background: #1a202c;
      color: #edf2f7;
      outline: none;
    }

    .wish-panel textarea:focus {
      border-color: #63b3ed;
      box-shadow: 0 0 0 1px #63b3ed;
    }

    .wish-panel button {
      margin-top: 12px;
      width: 100%;
      padding: 10px 0;
      border-radius: 999px;
      border: none;
      font-size: 0.95rem;
      font-weight: 600;
      letter-spacing: 0.05em;
      text-transform: uppercase;
      cursor: pointer;
      background: linear-gradient(135deg, #63b3ed, #9f7aea);
      color: #1a202c;
      box-shadow: 0 8px 18px rgba(99, 179, 237, 0.5);
      transition: transform 0.1s ease, box-shadow 0.1s ease;
    }

    .wish-panel button:hover {
      transform: translateY(-1px);
      box-shadow: 0 10px 22px rgba(99, 179, 237, 0.7);
    }

    .wish-panel button:active {
      transform: translateY(1px);
      box-shadow: 0 4px 10px rgba(99, 179, 237, 0.5);
    }

    .message {
      margin-top: 10px;
      font-size: 0.9rem;
      color: #9ae6b4;
      min-height: 1.2em;
    }

    footer {
      margin-top: auto;
      padding: 20px;
      font-size: 0.75rem;
      color: #718096;
      text-align: center;
    }
  </style>
</head>
<body>
  <header>
    <h1>The Wishing Well</h1>
    <p>
      Toss a wish into the quiet water. You won’t see it again—but maybe you’ll feel it
      echo back as courage.
    </p>
  </header>

  <main class="well-container">
    <div class="well" aria-hidden="true">
      <div class="roof"></div>
      <div class="posts">
        <div class="post"></div>
        <div class="post"></div>
      </div>
      <div class="bucket-rope"></div>
      <div class="bucket"></div>
      <div class="well-base">
        <div class="well-stones"></div>
        <div class="water"></div>
      </div>
    </div>

    <section class="wish-panel">
      <h2>Make a wish</h2>
      <p>
        Type your wish below, then release it into the well. It won’t be stored—this is just
        between you and the water.
      </p>

      <textarea id="wishInput" placeholder="I wish that..."></textarea>
      <button id="wishButton">Toss the coin</button>
      <div id="wishMessage" class="message"></div>
    </section>
  </main>

  <footer>
    This wishing well lives only in your browser. Refresh to start fresh.
  </footer>

  <script>
    const wishInput = document.getElementById('wishInput');
    const wishButton = document.getElementById('wishButton');
    const wishMessage = document.getElementById('wishMessage');

    wishButton.addEventListener('click', () => {
      const text = wishInput.value.trim();

      if (!text) {
        wishMessage.textContent = 'You forgot the wish. Try again.';
        wishMessage.style.color = '#feb2b2';
        return;
      }

      // “Release” the wish: clear the text and show a gentle message.
      wishInput.value = '';
      wishMessage.style.color = '#9ae6b4';
      const phrases = [
        'Your wish sinks softly into the water.',
        'The coin disappears, but the intention stays.',
        'The well keeps your secret and your hope.',
        'You let go—and something new might begin.'
      ];
      const phrase = phrases[Math.floor(Math.random() * phrases.length)];
      wishMessage.textContent = phrase;
    });
  </script>
</body>
</html>
<nav>
  <button id="tabIntro" class="active">Welcome</button>
  <button id="tabPayment">Payment</button>
  <button id="tabWish">Wish</button>
</nav>

<!-- INTRO TAB -->
<div id="introTab" class="tab active">
  <h2>Welcome to the Wishing Well</h2>
  <p>This is the wishing well where you can throw a coin in and wish for your greatest desires.</p>
  <button class="wish" id="introWishButton">Wish Now</button>
</div>

<!-- PAYMENT TAB -->
<div id="paymentTab" class="tab">
  <h2>Optional Offering</h2>
  <p>You may toss a symbolic $1 coin into the well. This is optional — the magic listens either way.</p>
  <button class="pay" id="payButton">Pay $1</button>
  <div id="paymentMessage" class="message"></div>
  <button class="wish" id="skipPaymentButton">Skip Payment</button>
</div>

<!-- WISH TAB -->
<div id="wishTab" class="tab">
  <h2>Make a Wish</h2>
  <p>Write your wish below and let it sink into the enchanted water.</p>
  <textarea id="wishInput" placeholder="I wish that..."></textarea>
  <button class="wish" id="wishButton">Toss the Coin</button>
  <div id="wishMessage" class="message"></div>
</div>

<script>
  let paid = false;

  // Tab elements
  const tabIntro = document.getElementById("tabIntro");
  const tabPayment = document.getElementById("tabPayment");
  const tabWish = document.getElementById("tabWish");

  const introTab = document.getElementById("introTab");
  const paymentTab = document.getElementById("paymentTab");
  const wishTab = document.getElementById("wishTab");

  function switchToIntro() {
    tabIntro.classList.add("active");
    tabPayment.classList.remove("active");
    tabWish.classList.remove("active");
    introTab.classList.add("active");
    paymentTab.classList.remove("active");
    wishTab.classList.remove("active");
  }

  function switchToPayment() {
    tabPayment.classList.add("active");
    tabIntro.classList.remove("active");
    tabWish.classList.remove("active");
    paymentTab.classList.add("active");
    introTab.classList.remove("active");
    wishTab.classList.remove("active");
  }

  function switchToWish() {
    tabWish.classList.add("active");
    tabIntro.classList.remove("active");
    tabPayment.classList.remove("active");
    wishTab.classList.add("active");
    introTab.classList.remove("active");
    paymentTab.classList.remove("active");
  }

  tabIntro.onclick = switchToIntro;
  tabPayment.onclick = switchToPayment;
  tabWish.onclick = switchToWish;

  // Intro button → goes to payment
  document.getElementById("introWishButton").onclick = switchToPayment;

  // Payment button
  const payButton = document.getElementById("payButton");
  const paymentMessage = document.getElementById("paymentMessage");

  payButton.onclick = () => {
    paid = true;
    paymentMessage.textContent = "Your offering has been accepted.";
    switchToWish();
  };

  // Skip payment
  document.getElementById("skipPaymentButton").onclick = switchToWish;

  // Wish logic (no payment enforcement)
  const wishButton = document.getElementById("wishButton");
  const wishInput = document.getElementById("wishInput");
  const wishMessage = document.getElementById("wishMessage");

  wishButton.onclick = () => {
    const text = wishInput.value.trim();
    if (!text) {
      wishMessage.textContent = "You forgot the wish.";
      wishMessage.style.color = "#feb2b2";
      return;
    }

    wishInput.value = "";
    wishMessage.style.color = "#9ae6b4";

    const phrases = [
      paid
        ? "Your paid wish sinks into the enchanted water."
        : "Your wish drifts softly into the well without a coin.",
      "Magic stirs as your wish disappears below.",
      "The well keeps your desire safe.",
      "A quiet ripple answers your hope."
    ];

    wishMessage.textContent = phrases[Math.floor(Math.random() * phrases.length)];
  };
</script>
