# OFFSET WAY
“Integrated Performance Dashboard – Offset Packaging”
<!DOCTYPE html>
<html lang="id">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Dashboard KPI Offset Packaging</title>

  <script src="https://cdn.jsdelivr.net/npm/chart.js"></script>

  <style>
    body {
      margin: 0;
      padding: 24px;
      font-family: Arial, sans-serif;
      background: #f4f7fb;
      color: #1f2937;
    }

    h1 {
      margin-bottom: 4px;
    }

    .subtitle {
      color: #64748b;
      margin-bottom: 24px;
    }

    .kpi-container {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(180px, 1fr));
      gap: 16px;
      margin-bottom: 24px;
    }

    .card {
      background: white;
      padding: 20px;
      border-radius: 14px;
      box-shadow: 0 4px 12px rgba(0,0,0,0.06);
    }

    .kpi-name {
      color: #64748b;
      font-size: 14px;
    }

    .kpi-value {
      margin-top: 8px;
      font-size: 30px;
      font-weight: bold;
      color: #0f766e;
    }

    .chart-container {
      background: white;
      padding: 20px;
      border-radius: 14px;
      box-shadow: 0 4px 12px rgba(0,0,0,0.06);
    }
  </style>
</head>

<body>
  <h1>Dashboard KPI Offset Packaging</h1>
  <div class="subtitle">Performance produksi Oktober 2026</div>

  <div class="kpi-container">
    <div class="card">
      <div class="kpi-name">OEE</div>
      <div class="kpi-value">78.5%</div>
    </div>

    <div class="card">
      <div class="kpi-name">Reject Rate</div>
      <div class="kpi-value">2.10%</div>
    </div>

    <div class="card">
      <div class="kpi-name">FPY</div>
      <div class="kpi-value">96.8%</div>
    </div>

    <div class="card">
      <div class="kpi-name">Plan Achievement</div>
      <div class="kpi-value">94.2%</div>
    </div>
  </div>

  <div class="chart-container">
    <canvas id="oeeChart"></canvas>
  </div>

  <script>
    const ctx = document.getElementById("oeeChart");

    new Chart(ctx, {
      type: "line",
      data: {
        labels: ["Jan", "Feb", "Mar", "Apr", "Mei", "Jun"],
        datasets: [{
          label: "OEE Aktual (%)",
          data: [68, 71, 73, 75, 77, 78.5],
          borderColor: "#0f766e",
          backgroundColor: "rgba(15,118,110,0.15)",
          fill: true,
          tension: 0.3
        }, {
          label: "Target OEE (%)",
          data: [85, 85, 85, 85, 85, 85],
          borderColor: "#ef4444",
          borderDash: [6, 6],
          tension: 0
        }]
      },
      options: {
        responsive: true,
        plugins: {
          title: {
            display: true,
            text: "Tren OEE Bulanan"
          }
        },
        scales: {
          y: {
            min: 0,
            max: 100
          }
        }
      }
    });
  </script>
</body>
</html>
