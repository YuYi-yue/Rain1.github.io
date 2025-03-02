<!DOCTYPE html>
<html lang="zh-CN">

<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>新冠疫情与区域经济发展的可视化关联分析</title>
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/Chart.js/3.9.1/chart.min.css">
  <style>
    body {
      font-family: Arial, sans-serif;
    }

  </style>
</head>

<body>
  <h1>新冠疫情与区域经济发展的可视化关联分析</h1>

  <!-- 区域经济增长趋势图表 -->
  <h2>区域经济增长趋势（疫情前后对比）</h2>
  <canvas id="economicGrowthChart"></canvas>

  <!-- 疫情确诊人数与经济指标相关性图表 -->
  <h2>疫情确诊人数与区域GDP相关性</h2>
  <canvas id="correlationChart"></canvas>

  <script src="https://cdnjs.cloudflare.com/ajax/libs/Chart.js/3.9.1/chart.min.js"></script>
  <script>
    // 模拟区域经济增长数据
    const economicGrowthData = {
      labels: ['2019', '2020', '2021', '2022', '2023'],
      datasets: [{
        label: '地区A经济增长率',
        data: [3.5, -1.2, 2.1, 3.0, 3.8],
        borderColor: 'blue',
        fill: false
      },
      {
        label: '地区B经济增长率',
        data: [2.8, -2.5, 1.8, 2.6, 3.5],
        borderColor:'red',
        fill: false
      }]
    };

    const economicGrowthCtx = document.getElementById('economicGrowthChart').getContext('2d');
    new Chart(economicGrowthCtx, {
      type: 'line',
      data: economicGrowthData,
      options: {
        scales: {
          y: {
            beginAtZero: true
          }
        }
      }
    });

    // 模拟疫情确诊人数与区域GDP相关性数据
    const correlationData = {
      labels: ['地区1', '地区2', '地区3', '地区4', '地区5'],
      datasets: [{
        label: '确诊人数',
        data: [1000, 2500, 800, 1800, 3000],
        borderColor: 'green',
        fill: false
      },
      {
        label: 'GDP增长率',
        data: [-0.5, -1.2, 0.2, -0.8, -1.5],
        borderColor: 'orange',
        fill: false
      }]
    };

    const correlationCtx = document.getElementById('correlationChart').getContext('2d');
    new Chart(correlationCtx, {
      type: 'bar',
      data: correlationData,
      options: {
        scales: {
          y: {
            beginAtZero: true
          }
        }
      }
    });
  </script>
</body>

</html>
