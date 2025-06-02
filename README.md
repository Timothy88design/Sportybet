<!DOCTYPE html>
<html>
<head>
  <title>BET99</title>
  <style>
    body { font-family: Arial; background: #121212; color: #fff; padding: 20px; }
    .balance { font-size: 20px; margin-bottom: 10px; }
    .btn { padding: 10px 20px; margin: 5px; background: green; color: white; border: none; }
  </style>
</head>
<body>
  <h1>BET99 Sportsbook</h1>
  <div class="balance">Balance: $<span id="balance">100</span></div>

  <h3>Choose your match</h3>
  <div>
    <button class="btn" onclick="placeBet(20)">Man Utd vs Arsenal - Odds 2.5</button><br>
    <button class="btn" onclick="placeBet(10)">Chelsea vs Liverpool - Odds 1.8</button>
  </div>

  <div id="message" style="margin-top: 20px;"></div>
  <button class="btn" style="background:red;" onclick="withdraw()">Withdraw</button>

  <script>
    let balance = 100;
    function placeBet(amount) {
      const win = Math.random() > 0.3; // 70% win rate
      const winnings = amount * (Math.random() * 1.5 + 1.5);
      if (win) {
        balance += winnings;
        document.getElementById('message').innerText = `You won $${winnings.toFixed(2)}!`;
      } else {
        balance -= amount;
        document.getElementById('message').innerText = `You lost $${amount}!`;
      }
      document.getElementById('balance').innerText = balance.toFixed(2);
    }

    function withdraw() {
      document.getElementById('message').innerHTML = `
        🚫 Withdrawals are temporarily disabled.<br>
        🔒 Please deposit at least $25 to enable withdrawals.
      `;
    }
  </script>
</body>
</html>
