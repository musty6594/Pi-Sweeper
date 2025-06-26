<!DOCTYPE html><html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Pi Sweeper Bot</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background: #f5f5f5;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      height: 100vh;
    }
    .card {
      background: white;
      padding: 20px;
      border-radius: 12px;
      box-shadow: 0 0 10px rgba(0,0,0,0.1);
      text-align: center;
    }
    .status {
      margin-top: 10px;
      font-weight: bold;
      color: green;
    }
  </style>
</head>
<body>
  <div class="card">
    <h2>Pi Sweeper Bot</h2>
    <p>This bot automatically sweeps your available Pi (if ≥ 0.02) to:</p>
    <code>MD5HGPHVL73EBDUD2Z4K2VDRLUBC4FFN7GOBLKPK6OPPXH6TED4TQAAAAGKUCP4TLXSKA</code>
    <p class="status">Status: Running every 1 second...</p>
  </div>  <script>
    const GAS_FEE = 0.01; // fixed Pi gas fee

    function getAvailableBalance() {
      // This should fetch your real wallet balance using Pi SDK or API
      // For demo, simulate a random value
      return parseFloat((Math.random() * 0.05 + 0.01).toFixed(4)); // simulates 0.01–0.06 Pi
    }

    function sweepPi() {
      const balance = getAvailableBalance();
      console.log("Available balance:", balance);

      if (balance >= 0.02) {
        const amountToSweep = (balance - GAS_FEE).toFixed(4);
        console.log(`Sweeping ${amountToSweep} Pi to destination wallet...`);
        // Here you would call Pi Wallet API to send amountToSweep to the wallet address
      } else {
        console.log("Balance too low to sweep.");
      }
    }

    setInterval(sweepPi, 1000); // Every 1 second
  </script></body>
</html>
