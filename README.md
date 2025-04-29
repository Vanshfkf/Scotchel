# Scotchel
In this you could see time and temperature of every state of India
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <title>Scotchel - World Clock</title>
  <style>
    body {
      background: #f2f2f2;
      font-family: 'Arial', sans-serif;
      text-align: center;
      padding: 30px;
    }
    h1 {
      font-size: 3rem;
      color: #333;
    }
    .clock-container {
      display: flex;
      flex-wrap: wrap;
      justify-content: center;
      gap: 20px;
      margin-top: 40px;
    }
    .clock {
      background: white;
      padding: 20px;
      border-radius: 10px;
      box-shadow: 0 4px 8px rgba(0,0,0,0.1);
      width: 200px;
    }
    .country {
      font-size: 1.5rem;
      margin-bottom: 10px;
    }
    .time {
      font-size: 1.2rem;
      color: #555;
    }
  </style>
</head>
<body>

  <h1>Scotchel - World Clock</h1>
  
  <div class="clock-container" id="clocks">
    <!-- Times will be inserted here -->
  </div>

  <script>
    const countries = [
      { name: "New York (USA)", timeZone: "America/New_York" },
      { name: "London (UK)", timeZone: "Europe/London" },
      { name: "Paris (France)", timeZone: "Europe/Paris" },
      { name: "Moscow (Russia)", timeZone: "Europe/Moscow" },
      { name: "Dubai (UAE)", timeZone: "Asia/Dubai" },
      { name: "Mumbai (India)", timeZone: "Asia/Kolkata" },
      { name: "Beijing (China)", timeZone: "Asia/Shanghai" },
      { name: "Tokyo (Japan)", timeZone: "Asia/Tokyo" },
      { name: "Sydney (Australia)", timeZone: "Australia/Sydney" }
    ];

    function updateClocks() {
      const clocksDiv = document.getElementById('clocks');
      clocksDiv.innerHTML = '';

      countries.forEach(country => {
        const now = new Date().toLocaleTimeString('en-US', { timeZone: country.timeZone, hour: '2-digit', minute: '2-digit', second: '2-digit' });

        const clockDiv = document.createElement('div');
        clockDiv.className = 'clock';
        clockDiv.innerHTML = `
          <div class="country">${country.name}</div>
          <div class="time">${now}</div>
        `;
        clocksDiv.appendChild(clockDiv);
      });
    }

    setInterval(updateClocks, 1000);
    updateClocks(); // Initial call
  </script>

</body>
</html>
