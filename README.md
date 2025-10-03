
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Traffic Accidents Data Visualization</title>
  <script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
  <style>
    body {
      font-family: Arial, sans-serif;
      margin: 20px;
      background: #f4f7fa;
      color: #333;
    }
    h1 {
      text-align: center;
      margin-bottom: 30px;
    }
    .chart-container {
      width: 90%;
      margin: 20px auto;
      background: #fff;
      padding: 20px;
      border-radius: 12px;
      box-shadow: 0 4px 12px rgba(0,0,0,0.1);
    }
    canvas {
      max-height: 400px;
    }
  </style>
</head>
<body>

  <h1>🚦 Traffic Accidents Data Visualization</h1>

  <!-- Chart 1: Accidents per Year -->
  <div class="chart-container">
    <h3>Accidents Per Year</h3>
    <canvas id="accidentsYear"></canvas>
  </div>

  <!-- Chart 2: Accident Types -->
  <div class="chart-container">
    <h3>Types of Accidents</h3>
    <canvas id="accidentTypes"></canvas>
  </div>

  <!-- Chart 3: Accidents by Time of Day -->
  <div class="chart-container">
    <h3>Accidents by Time of Day</h3>
    <canvas id="accidentsTime"></canvas>
  </div>

  <script>
    // Chart 1 - Accidents per Year
    new Chart(document.getElementById("accidentsYear"), {
      type: "line",
      data: {
        labels: ["2018", "2019", "2020", "2021", "2022", "2023"],
        datasets: [{
          label: "Number of Accidents",
          data: [1200, 1500, 900, 1700, 2000, 1800],
          borderColor: "rgba(75,192,192,1)",
          backgroundColor: "rgba(75,192,192,0.2)",
          borderWidth: 2,
          tension: 0.3,
          fill: true
        }]
      },
      options: {
        responsive: true,
        plugins: { legend: { position: "top" } }
      }
    });

    // Chart 2 - Accident Types
    new Chart(document.getElementById("accidentTypes"), {
      type: "pie",
      data: {
        labels: ["Car Collision", "Bike Accident", "Truck Accident", "Pedestrian", "Others"],
        datasets: [{
          data: [45, 25, 15, 10, 5],
          backgroundColor: [
            "#FF6384",
            "#36A2EB",
            "#FFCE56",
            "#4BC0C0",
            "#9966FF"
          ]
        }]
      },
      options: {
        responsive: true,
        plugins: { legend: { position: "right" } }
      }
    });

    // Chart 3 - Accidents by Time of Day
    new Chart(document.getElementById("accidentsTime"), {
      type: "bar",
      data: {
        labels: ["Morning", "Afternoon", "Evening", "Night"],
        datasets: [{
          label: "Accidents",
          data: [500, 800, 1200, 600],
          backgroundColor: "rgba(54,162,235,0.7)",
          borderColor: "rgba(54,162,235,1)",
          borderWidth: 1
        }]
      },
      options: {
        responsive: true,
        scales: { y: { beginAtZero: true } }
      }
    });
  </script>
</body>
</html>
