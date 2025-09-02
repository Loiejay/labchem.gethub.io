<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>School Laboratory</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      margin: 0;
      padding: 0;
      background-color: #f5f7fa;
    }
    header {
      background-color: #003366;
      color: white;
      padding: 1rem;
      text-align: center;
    }
    nav {
      background-color: #00509e;
      padding: 0.5rem;
      text-align: center;
    }
    nav a {
      color: white;
      margin: 0 15px;
      text-decoration: none;
      font-weight: bold;
    }
    nav a:hover {
      text-decoration: underline;
    }
    .container {
      padding: 20px;
      max-width: 1000px;
      margin: auto;
    }
    table {
      width: 100%;
      border-collapse: collapse;
      margin-top: 20px;
    }
    table, th, td {
      border: 1px solid #ccc;
    }
    th, td {
      padding: 10px;
      text-align: center;
    }
    th {
      background-color: #003366;
      color: white;
    }
    footer {
      background-color: #003366;
      color: white;
      text-align: center;
      padding: 1rem;
      margin-top: 20px;
    }
    #searchBar {
      padding: 10px;
      width: 100%;
      max-width: 400px;
      margin: 10px 0;
      border: 1px solid #ccc;
      border-radius: 5px;
    }
    #time {
      margin-top: 10px;
      font-size: 14px;
      color: #ffdd57;
    }
  </style>
  <script>
    function searchTable() {
      let input = document.getElementById("searchBar").value.toLowerCase();
      let rows = document.querySelectorAll("#chemicalTable tr");
      rows.forEach((row, index) => {
        if (index === 0) return; // skip header
        let text = row.innerText.toLowerCase();
        row.style.display = text.includes(input) ? "" : "none";
      });
    }

    function updateTime() {
      let options = { timeZone: "Asia/Manila", hour: "2-digit", minute: "2-digit", second: "2-digit" };
      let now = new Date().toLocaleTimeString("en-PH", options);
      document.getElementById("time").textContent = "Philippine Time: " + now;
    }

    setInterval(updateTime, 1000);
    window.onload = updateTime;
  </script>
</head>
<body>
  <header>
    <h1>School Laboratory</h1>
    <p>Welcome to the official laboratory chemical inventory and location portal</p>
  </header>

  <nav>
    <a href="#home">Home</a>
    <a href="#chemicals">Chemical List</a>
    <a href="#location">Location</a>
  </nav>

  <div class="container" id="home">
    <h2>About the Laboratory</h2>
    <p>This laboratory provides facilities and chemical resources for science students. Below you can find our current list of chemicals and their storage locations.</p>
  </div>

  <div class="container" id="chemicals">
    <h2>Chemical Inventory</h2>
    <input type="text" id="searchBar" onkeyup="searchTable()" placeholder="Search for a chemical...">
    <table id="chemicalTable">
      <tr>
        <th>Chemical Name</th>
        <th>Quantity</th>
        <th>Hazard Level</th>
      </tr>
      <tr>
        <td>Sodium Chloride (NaCl)</td>
        <td>5 kg</td>
        <td>Low</td>
      </tr>
      <tr>
        <td>Sulfuric Acid (H2SO4)</td>
        <td>2 L</td>
        <td>High</td>
      </tr>
      <tr>
        <td>Ethanol (C2H5OH)</td>
        <td>3 L</td>
        <td>Medium</td>
      </tr>
      <tr>
        <td>Copper Sulfate (CuSO4)</td>
        <td>1 kg</td>
        <td>Medium</td>
      </tr>
    </table>
  </div>

  <div class="container" id="location">
    <h2>Laboratory Locations</h2>
    <p><strong>Main Chemistry Lab:</strong> Room 201, Science Building</p>
    <p><strong>Chemical Storage Room:</strong> Room 202, Science Building</p>
    <p><strong>Biology Lab:</strong> Room 203, Science Building</p>
  </div>

  <footer>
    <p>&copy; 2025 School Laboratory | All Rights Reserved</p>
    <div id="time"></div>
  </footer>
</body>
</html>
