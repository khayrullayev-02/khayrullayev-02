<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Animated Skill Bars</title>
  <style>
    /* Asosiy sozlashlar */
    body {
      font-family: 'Arial', sans-serif;
      background: linear-gradient(135deg, #1e1e2f, #252537);
      color: white;
      display: flex;
      justify-content: center;
      align-items: center;
      flex-direction: column;
      min-height: 100vh;
      margin: 0;
    }

    h1 {
      margin-bottom: 20px;
      font-size: 2rem;
    }

    .skills-container {
      display: flex;
      flex-wrap: wrap;
      justify-content: center;
      gap: 30px;
    }

    .skill {
      position: relative;
      width: 150px;
      height: 150px;
    }

    .skill .outer-circle {
      width: 100%;
      height: 100%;
      border-radius: 50%;
      background: conic-gradient(
        #ff6b6b calc(var(--progress) * 1%),
        #ddd calc(var(--progress) * 1%)
      );
      display: flex;
      justify-content: center;
      align-items: center;
      animation: rotate 4s linear infinite;
    }

    @keyframes rotate {
      0% {
        transform: rotate(0deg);
      }
      100% {
        transform: rotate(360deg);
      }
    }

    .skill .inner-circle {
      width: 90%;
      height: 90%;
      background: #252537;
      border-radius: 50%;
      display: flex;
      justify-content: center;
      align-items: center;
      flex-direction: column;
      z-index: 2;
    }

    .skill .inner-circle span {
      font-size: 1.5rem;
      font-weight: bold;
    }

    .skill .inner-circle p {
      font-size: 0.8rem;
      margin-top: 5px;
    }
  </style>
</head>
<body>
  <h1>🔄 Mening Skill Barlarim</h1>
  <div class="skills-container">
    <!-- Skill 1 -->
    <div class="skill" style="--progress: 80;">
      <div class="outer-circle">
        <div class="inner-circle">
          <span>80%</span>
          <p>HTML</p>
        </div>
      </div>
    </div>

    <!-- Skill 2 -->
    <div class="skill" style="--progress: 70;">
      <div class="outer-circle">
        <div class="inner-circle">
          <span>70%</span>
          <p>CSS</p>
        </div>
      </div>
    </div>

    <!-- Skill 3 -->
    <div class="skill" style="--progress: 60;">
      <div class="outer-circle">
        <div class="inner-circle">
          <span>60%</span>
          <p>JavaScript</p>
        </div>
      </div>
    </div>
  </div>
</body>
</html>
