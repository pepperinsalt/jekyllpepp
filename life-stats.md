---
layout: default
title: Life Stats Dashboard
permalink: /life-stats/
---

<div class="stats-dashboard" style="padding: 40px 20px; display: flex; justify-content: center;">
  <div class="glass-card" style="
    background: rgba(255, 255, 255, 0.05);
    backdrop-filter: blur(15px);
    -webkit-backdrop-filter: blur(15px);
    border: 1px solid rgba(255, 255, 255, 0.1);
    border-radius: 24px;
    padding: 2rem;
    width: 100%;
    max-width: 900px;
    box-shadow: 0 8px 32px 0 rgba(0, 0, 0, 0.3);
  ">
    <h1 style="color: white; margin-bottom: 20px;">The Dyrdek Machine</h1>
    
    <div style="position: relative; height:400px; width:100%">
      <canvas id="myStatsChart"></canvas>
    </div>
  </div>
</div>

<script src="https://cdn.jsdelivr.net/npm/chart.js"></script>

<script>
  // Use Jekyll's Liquid to pull data from your markdown files
  // We sort by date so the graph reads chronologically left to right
  {% assign sorted_stats = site.stats | sort: "date" %}
  
  const dates = [
    {% for stat in sorted_stats %}
      "{{ stat.date | date: '%b %d' }}"{% unless forloop.last %},{% endunless %}
    {% endfor %}
  ];

  const healthData = [{% for stat in sorted_stats %}{{ stat.health | default: 0 }}{% unless forloop.last %},{% endunless %}{% endfor %}];
  const wealthData = [{% for stat in sorted_stats %}{{ stat.wealth | default: 0 }}{% unless forloop.last %},{% endunless %}{% endfor %}];
  const familyData = [{% for stat in sorted_stats %}{{ stat.family | default: 0 }}{% unless forloop.last %},{% endunless %}{% endfor %}];
  const personalData = [{% for stat in sorted_stats %}{{ stat.personal | default: 0 }}{% unless forloop.last %},{% endunless %}{% endfor %}];

  // Initialize Chart
  const ctx = document.getElementById('myStatsChart').getContext('2d');
  
  // Set global font color to white for dark mode/glass look
  Chart.defaults.color = 'rgba(255, 255, 255, 0.8)';
  Chart.defaults.font.family = 'sans-serif';

  new Chart(ctx, {
    type: 'line',
    data: {
      labels: dates,
      datasets: [
        { label: 'Health', data: healthData, borderColor: '#4ade80', backgroundColor: 'rgba(74, 222, 128, 0.1)', tension: 0.4, fill: true },
        { label: 'Wealth', data: wealthData, borderColor: '#facc15', backgroundColor: 'rgba(250, 204, 21, 0.1)', tension: 0.4 },
        { label: 'Family', data: familyData, borderColor: '#60a5fa', backgroundColor: 'rgba(96, 165, 250, 0.1)', tension: 0.4 },
        { label: 'Personal', data: personalData, borderColor: '#c084fc', backgroundColor: 'rgba(192, 132, 252, 0.1)', tension: 0.4 }
      ]
    },
    options: {
      responsive: true,
      maintainAspectRatio: false,
      scales: {
        y: { 
          min: 0, 
          max: 10,
          grid: { color: 'rgba(255, 255, 255, 0.1)' }
        },
        x: {
          grid: { display: false }
        }
      },
      plugins: {
        legend: { position: 'top' }
      }
    }
  });
</script>
