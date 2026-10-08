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
