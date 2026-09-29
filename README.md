<!DOCTYPE html>
<html>
<head>
  <title>4 Day Countdown</title>

  <style>
    body {
      background: #0a0a0a;
      color: white;
      font-family: Arial, sans-serif;
      text-align: center;
      padding-top: 100px;
    }

    #countdown {
      font-size: 60px;
      font-weight: bold;
    }
  </style>
</head>

<body>

  <h1>Countdown</h1>
  <div id="countdown">Loading...</div>

  <script>
    // 4 days from when the page is opened
    const endTime = Date.now() + (4 * 24 * 60 * 60 * 1000);

    function updateCountdown() {
      const remaining = endTime - Date.now();

      if (remaining <= 0) {
        document.getElementById("countdown").textContent = "TIME'S UP!";
        return;
      }

      const days = Math.floor(remaining / (1000 * 60 * 60 * 24));
      const hours = Math.floor((remaining / (1000 * 60 * 60)) % 24);
      const minutes = Math.floor((remaining / (1000 * 60)) % 60);
      const seconds = Math.floor((remaining / 1000) % 60);

      document.getElementById("countdown").textContent =
        `${days}d ${hours}h ${minutes}m ${seconds}s`;
    }

    updateCountdown();
    setInterval(updateCountdown, 1000);
  </script>

</body>
</html>
