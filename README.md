<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Skill Bar</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background-color: #1e1e2f;
      color: white;
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
      margin: 0;
    }

    .skill-container {
      display: flex;
      gap: 20px;
    }

    .circle {
      position: relative;
      width: 120px;
      height: 120px;
      background: #333;
      border-radius: 50%;
      display: flex;
      justify-content: center;
      align-items: center;
    }

    .circle::before {
      content: '';
      position: absolute;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      background: conic-gradient(
        green calc(var(--progress) * 1%), 
        red calc(var(--progress) * 1%), 
        gray 0
      );
      border-radius: 50%;
      z-index: 1;
    }

    .circle-text {
      position: relative;
      z-index: 2;
      color: white;
      font-size: 16px;
      font-weight: bold;
    }
  </style>
</head>
<body>
  <div class="skill-container">
    <div class="circle" style="--progress: 75;">
      <div class="circle-text">75%</div>
    </div>
    <div class="circle" style="--progress: 40;">
      <div class="circle-text">40%</div>
    </div>
  </div>

  <script>
    // JavaScript bilan animatsiya
    const circles = document.querySelectorAll('.circle');
    circles.forEach((circle) => {
      let progress = 0;
      const targetProgress = parseInt(circle.style.getPropertyValue('--progress'));
      const interval = setInterval(() => {
        if (progress >= targetProgress) {
          clearInterval(interval);
        } else {
          progress++;
          circle.style.setProperty('--progress', progress);
          circle.querySelector('.circle-text').innerText = `${progress}%`;
        }
      }, 20);
    });
  </script>
</body>
</html>
