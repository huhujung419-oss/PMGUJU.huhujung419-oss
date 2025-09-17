# huhujung419-oss.githib.io
<!DOCTYPE html>
<html lang="ko">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Triple Dials with Simple Animation</title>
  <style>
    @import url('https://cdn.jsdelivr.net/npm/@fontsource/pretendard@latest/latin-300.css');
    @import url('https://cdn.jsdelivr.net/npm/@fontsource/pretendard@latest/latin-400.css');
    @import url('https://cdn.jsdelivr.net/npm/@fontsource/pretendard@latest/latin-500.css');

    body {
      height: 100vh; margin: 0; padding: 0;
      display: flex; justify-content: center; align-items: center;
      background: #fff;
      font-family: 'Pretendard', -apple-system, BlinkMacSystemFont, system-ui, Roboto, 'Helvetica Neue', Arial, sans-serif;
      color: #555; user-select: none; overflow: hidden;
    }
    
    /* 메인 화면 */
    #main-screen {
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      width: 100%;
      height: 100%;
    }
    
    #page-container {
      display: flex; justify-content: center; align-items: center; gap: 80px;
    }
    
    /* Finish 버튼 */
    #finish-button {
      position: fixed;
      bottom: 30px;
      left: 50%;
      transform: translateX(-50%);
      padding: 12px 30px;
      background: #ccc;
      color: #888;
      border: none;
      border-radius: 20px;
      font-size: 16px;
      font-weight: 600;
      cursor: not-allowed;
      font-family: 'Pretendard', sans-serif;
      box-shadow: 0 3px 12px rgba(204, 204, 204, 0.3);
      transition: all 0.3s ease;
    }
    
    #finish-button.active {
      background: #333;
      color: white;
      cursor: pointer;
      box-shadow: 0 3px 12px rgba(51, 51, 51, 0.3);
    }
    
    #finish-button.active:hover {
      background: #222;
      transform: translateX(-50%) translateY(-2px);
      box-shadow: 0 5px 16px rgba(51, 51, 51, 0.4);
    }
    
    /* 로딩 화면 */
    #loading-screen {
      display: none;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      width: 100%;
      height: 100%;
      background: #fff;
    }
    
    #loading-text {
      font-size: 16px;
      font-weight: 500;
      color: #666;
      margin-bottom: 40px;
    }
    
    /* 흰 화면 */
    #white-screen {
      display: none;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      width: 100%;
      height: 100%;
      background: #fff;
    }
    
    /* 3D 프린팅스러운 애니메이션 */
    .printer-container {
      width: 200px;
      height: 180px;
      position: relative;
    }
    
    /* 흑백 스타일 아이콘들 - 음영 없는 미니멀 스타일 */
    .floating-icon {
      position: absolute;
      width: 20px;
      height: 20px;
      user-select: none;
      pointer-events: none;
      filter: grayscale(1) contrast(1.2);
      opacity: 0.7;
    }
    
    .planet-icon {
      top: 40px;
      left: 60px;
      animation: float-1 3s ease-in-out infinite;
    }
    
    .rocket-icon {
      top: 80px;
      right: 50px;
      animation: float-2 2.8s ease-in-out infinite 0.5s;
    }
    
    .star-icon {
      top: 120px;
      left: 50px;
      animation: float-3 2.5s ease-in-out infinite 1s;
    }
    
    @keyframes float-1 {
      0%, 100% { transform: translateY(0px) rotate(0deg); }
      50% { transform: translateY(-8px) rotate(5deg); }
    }
    
    @keyframes float-2 {
      0%, 100% { transform: translateY(0px) rotate(0deg); }
      50% { transform: translateY(-10px) rotate(8deg); }
    }
    
    @keyframes float-3 {
      0%, 100% { transform: translateY(0px) rotate(0deg) scale(1); }
      50% { transform: translateY(-6px) rotate(-5deg) scale(1.1); }
    }
    
    /* 노즐: 3D 프린팅처럼 레이어별로 움직임 */
    .printer-nozzle {
      width: 8px;
      height: 12px;
      background: #333;
      position: absolute;
      top: 120px;
      left: 96px;
      border-radius: 0 0 4px 4px;
      animation: nozzle-3d-printing 5s ease-in-out;
    }
    
    .printer-nozzle::before {
      content: '';
      position: absolute;
      top: -6px;
      left: -4px;
      width: 16px;
      height: 6px;
      background: #555;
      border-radius: 8px;
    }
    
    /* 병 형태 - 새로운 색상 */
    .bottle-container {
      position: absolute;
      bottom: 40px;
      left: 85px;
      width: 30px;
      height: 80px;
    }
    
    .bottle-shape {
      position: absolute;
      bottom: 0;
      left: 50%;
      transform: translateX(-50%);
      width: 28px;
      height: 0;
      background: #ACB1FF;
      border-radius: 0 0 14px 14px;
      animation: bottle-build 5s ease-out;
    }
    
    /* 3D 프린팅처럼 레이어별로 노즐 움직임 */
    @keyframes nozzle-3d-printing {
      0% { top: 120px; left: 85px; }
      5% { top: 120px; left: 107px; }
      10% { top: 120px; left: 85px; }
      15% { top: 115px; left: 107px; }
      20% { top: 110px; left: 85px; }
      25% { top: 105px; left: 107px; }
      30% { top: 100px; left: 85px; }
      35% { top: 95px; left: 107px; }
      40% { top: 90px; left: 85px; }
      45% { top: 85px; left: 107px; }
      50% { top: 80px; left: 85px; }
      55% { top: 75px; left: 107px; }
      60% { top: 70px; left: 85px; }
      65% { top: 65px; left: 107px; }
      70% { top: 60px; left: 85px; }
      75% { top: 55px; left: 107px; }
      80% { top: 50px; left: 85px; }
      85% { top: 45px; left: 107px; }
      90% { top: 40px; left: 85px; }
      95% { top: 35px; left: 107px; }
      100% { top: 30px; left: 96px; }
    }
    
    @keyframes bottle-build {
      0%, 15% { height: 0; }
      25% { height: 12px; }
      40% { height: 28px; }
      55% { height: 45px; }
      70% { height: 58px; }
      85% { height: 68px; }
      100% { height: 75px; }
    }
    
    /* 완료 화면 */
    #finish-screen {
      display: none;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      width: 100%;
      height: 100%;
      background: #fff;
      padding: 40px;
      box-sizing: border-box;
    }
    
    #result-image {
      max-width: 40%;
      max-height: 35%;
      object-fit: contain;
      margin-bottom: 20px;
      border-radius: 10px;
    }
    
    /* 완성 메시지 */
    #completion-message {
      font-size: 18px;
      font-weight: 500;
      color: #555;
      margin-bottom: 25px;
      text-align: center;
    }
    
    #home-button {
      padding: 12px 30px;
      background: #666;
      color: white;
      border: none;
      border-radius: 20px;
      font-size: 16px;
      font-weight: 600;
      cursor: pointer;
      font-family: 'Pretendard', sans-serif;
      box-shadow: 0 3px 12px rgba(102, 102, 102, 0.3);
      transition: all 0.3s ease;
    }
    
    #home-button:hover {
      background: #555;
      transform: translateY(-2px);
      box-shadow: 0 5px 16px rgba(102, 102, 102, 0.4);
    }

    .main-content { display: flex; flex-direction: column; align-items: center; position: relative; }
    .status-container {
      width: 320px; height: 30px; margin-bottom: 15px;
      display: flex; align-items: center; justify-content: center; gap: 3px;
    }
    .bar {
      width: 4px; background: #9EA4FF; transition: height 0.2s ease, opacity 0.3s ease;
      border-radius: 2px; height: 3px; opacity: 0.15;
    }
    #thermometer { font-size: 18px; font-weight: 500; }
    .waveform-svg { width: 80px; height: 30px; }
    .waveform-path { stroke: #888; stroke-width: 2; fill: none; transition: d 0.1s linear; }

    .container {
      position: relative; width: 320px; height: 320px; margin: 0 auto; user-select: none;
      transition: transform 0.5s ease-out;
    }
    .outer-ring {
      position: absolute; top: 0; left: 0; width: 100%; height: 100%;
      border-radius: 50%; z-index: 2; cursor: grab; user-select: none; -webkit-user-drag: none;
      object-fit: contain; background: transparent; transition: cursor 0.2s;
      transition: transform 0.1s cubic-bezier(0.4, 0.0, 0.2, 1);
    }
    .outer-ring:active { cursor: grabbing; }
    .outer-ring.no-transition { transition: none; }
    .outer-ring.feedback-pulse { 
      animation: detent-pulse 200ms ease-out;
    }
    
    @keyframes detent-pulse {
      0% { transform: scale(1) rotate(var(--current-rotation)); }
      30% { transform: scale(0.99) rotate(var(--current-rotation)); }
      100% { transform: scale(1) rotate(var(--current-rotation)); }
    }
    
    .inner-pad {
      position: absolute; top: 22px; left: 22px; width: 276px; height: 276px;
      border-radius: 50%; overflow: hidden; z-index: 3; pointer-events: auto; cursor: pointer; box-sizing: border-box;
    }
    .inner-bg { width: 100%; height: 100%; display: block; user-select: none; -webkit-user-drag: none; pointer-events: none; }
    .fill-overlay {
      position: absolute; top: 0; left: 0; width: 100%; height: 100%;
      pointer-events: none; z-index: 5; transition: all 0.5s ease-out; background: var(--fill-gradient);
    }
    .trail-container { position: absolute; left: 0; top: 0; width: 100%; height: 100%; pointer-events: none; z-index: 10; }
    .trail-dot {
      position: absolute; border-radius: 50%; background-color: rgba(158,164,255,0.13); pointer-events: none;
      opacity: 1; animation: dot-fade 1.1s cubic-bezier(0.5,1,0.7,1) forwards;
      filter: blur(15px); transform: translate(-50%, -50%); width: 50px; height: 50px; will-change: filter, opacity;
    }
    @keyframes dot-fade { to { opacity: 0; } }

    .guide-text {
      width: 320px; font-weight: 500; text-align: center; font-size: 14px; color: #555;
      user-select: none; line-height: 1.4; margin: 40px auto 15px auto; visibility: hidden;
    }
    #guide-text-middle { visibility: visible; }
  </style>
</head>
<body>

<!-- 메인 화면 -->
<div id="main-screen">
  <div id="page-container">
    <!-- Left Dial (Vibration with waveform) -->
    <div class="main-content">
      <div id="status-left" class="status-container" aria-hidden="true">
        <svg id="waveform-svg-left" class="waveform-svg"><path id="waveform-path-left" class="waveform-path" d="M 0 15 L 80 15"></path></svg>
      </div>
      <div id="container-left" class="container" role="region" aria-label="Left interactive dial">
        <img id="outer-ring-left" class="outer-ring" src="https://i.imgur.com/cAtYGyh.png" alt="왼쪽 원형 다이얼" />
        <div id="inner-pad-left" class="inner-pad">
          <img class="inner-bg" src="https://i.imgur.com/daKC5T2.png" alt="왼쪽 내부 패드 이미지" />
          <div id="fill-overlay-left" class="fill-overlay"></div>
          <div id="trail-container-left" class="trail-container"></div>
        </div>
      </div>
      <p id="guide-text-left" class="guide-text"></p>
    </div>

    <!-- Middle Dial (Sound) -->
    <div class="main-content">
      <div id="status-middle" class="status-container" aria-hidden="true"></div>
      <div id="container-middle" class="container" role="region" aria-label="Middle interactive dial">
        <img id="outer-ring-middle" class="outer-ring" src="https://i.imgur.com/TbozTaQ.jpeg" alt="가운데 원형 다이얼" />
        <div id="inner-pad-middle" class="inner-pad">
          <img class="inner-bg" src="https://i.imgur.com/CLyC7Oz.png" alt="가운데 내부 패드 이미지" />
          <div id="fill-overlay-middle" class="fill-overlay"></div>
          <div id="trail-container-middle" class="trail-container"></div>
        </div>
      </div>
      <p id="guide-text-middle" class="guide-text">
        겉면의 다이얼을 돌릴 수 있습니다.<br>
        터치 패널에 마우스를 갖다대거나 클릭해보세요.
      </p>
    </div>

    <!-- Right Dial (Temperature) -->
    <div class="main-content">
      <div id="status-right" class="status-container" aria-hidden="true">
        <span id="thermometer"><span id="temperature-value">36.5°C</span></span>
      </div>
      <div id="container-right" class="container" role="region" aria-label="Right interactive dial">
        <img id="outer-ring-right" class="outer-ring" src="https://i.imgur.com/0qwvVIe.png" alt="오른쪽 원형 다이얼" />
        <div id="inner-pad-right" class="inner-pad">
          <img class="inner-bg" src="https://i.imgur.com/wT3AMnE.png" alt="오른쪽 내부 패드 이미지" />
          <div id="fill-overlay-right" class="fill-overlay"></div>
          <div id="trail-container-right" class="trail-container"></div>
        </div>
      </div>
      <p id="guide-text-right" class="guide-text"></p>
    </div>
  </div>
  
  <button id="finish-button">FINISH</button>
</div>

<!-- 로딩 화면 -->
<div id="loading-screen">
  <div class="printer-container">
    <!-- 흑백 미니멀 스타일 아이콘들 -->
    <svg class="floating-icon planet-icon" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
      <circle cx="12" cy="12" r="8"/>
      <ellipse cx="12" cy="12" rx="11" ry="3"/>
    </svg>
    
    <svg class="floating-icon rocket-icon" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
      <path d="M4.5 16.5c-1.5 1.26-2 5-2 5s3.74-.5 5-2c.71-.84.7-2.13-.09-2.91a2.18 2.18 0 0 0-2.91-.09z"/>
      <path d="m12 15-3-3a22 22 0 0 1 2-3.95A12.88 12.88 0 0 1 22 2c0 2.72-.78 7.5-6 11a22.35 22.35 0 0 1-4 2z"/>
      <path d="M9 12H4s.55-3.03 2-4c1.62-1.08 5 0 5 0"/>
      <path d="M12 15v5s3.03-.55 4-2c1.08-1.62 0-5 0-5"/>
    </svg>
    
    <svg class="floating-icon star-icon" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
      <polygon points="12,2 15.09,8.26 22,9.27 17,14.14 18.18,21.02 12,17.77 5.82,21.02 7,14.14 2,9.27 8.91,8.26 12,2"/>
    </svg>
    
    <div class="printer-nozzle"></div>
    <div class="bottle-container">
      <div class="bottle-shape"></div>
    </div>
  </div>
  <div id="loading-text">병 만드는 중...</div>
</div>

<!-- 흰 화면 -->
<div id="white-screen">
  <!-- 빈 흰 화면 -->
</div>

<!-- 완료 화면 -->
<div id="finish-screen">
  <img id="result-image" alt="결과 이미지" />
  <div id="completion-message">향기가 완성 되었습니다</div>
  <button id="home-button">Home</button>
</div>

<audio id="rain-sound" src="https://actions.google.com/sounds/v1/weather/light_rain.ogg" preload="auto" loop></audio>

<script>
  // ------------------------
  // Global variables
  // ------------------------
  const rainSound = document.getElementById('rain-sound');
  rainSound.volume = 0; rainSound.pause();

  let globalDragState = { isDragging: false, dialId: null };
  
  let dialMoved = {
    left: false,
    middle: false,
    right: false
  };

  let dialInstances = {};

  // 3개 이미지
  const resultImages = [
    'https://i.imgur.com/uwJHQSt.png',
    'https://i.imgur.com/rYmbPsr.png', 
    'https://i.imgur.com/KI2WR6a.png'
  ];

  // ------------------------
  // UI Management
  // ------------------------
  function checkFinishCondition() {
    const allMoved = Object.values(dialMoved).every(moved => moved === true);
    const finishButton = document.getElementById('finish-button');
    
    if (allMoved) {
      finishButton.classList.add('active');
      finishButton.disabled = false;
    } else {
      finishButton.classList.remove('active');
      finishButton.disabled = true;
    }
  }

  function showLoadingScreen() {
    const finishButton = document.getElementById('finish-button');
    if (!finishButton.classList.contains('active')) return;
    
    document.getElementById('main-screen').style.display = 'none';
    document.getElementById('loading-screen').style.display = 'flex';
    
    setTimeout(() => {
      showWhiteScreen();
    }, 5000);
  }

  function showWhiteScreen() {
    document.getElementById('loading-screen').style.display = 'none';
    document.getElementById('white-screen').style.display = 'flex';
    
    setTimeout(() => {
      showFinishScreen();
    }, 2000); // 2초 대기
  }

  function showFinishScreen() {
    const randomIndex = Math.floor(Math.random() * resultImages.length);
    const selectedImage = resultImages[randomIndex];
    
    const resultImg = document.getElementById('result-image');
    resultImg.src = selectedImage;
    
    document.getElementById('white-screen').style.display = 'none';
    document.getElementById('finish-screen').style.display = 'flex';
  }

  function showMainScreen() {
    document.getElementById('main-screen').style.display = 'flex';
    document.getElementById('loading-screen').style.display = 'none';
    document.getElementById('white-screen').style.display = 'none';
    document.getElementById('finish-screen').style.display = 'none';
    
    resetAllDials();
  }

  function resetAllDials() {
    dialMoved = {
      left: false,
      middle: false,
      right: false
    };
    
    Object.keys(dialInstances).forEach(dialId => {
      dialInstances[dialId].reset();
    });
    
    rainSound.pause();
    rainSound.currentTime = 0;
    rainSound.volume = 0;
    
    checkFinishCondition();
  }

  document.getElementById('finish-button').addEventListener('click', showLoadingScreen);
  document.getElementById('home-button').addEventListener('click', showMainScreen);

  // ------------------------
  // Dial setup (360도 4단계 + 360도 지점 피드백)
  // ------------------------
  function setupDial(dialId, { fillSteps, fillType, effect }) {
    const container = document.getElementById(`container-${dialId}`);
    const outerRing = document.getElementById(`outer-ring-${dialId}`);
    const innerPad = document.getElementById(`inner-pad-${dialId}`);
    const fillOverlay = document.getElementById(`fill-overlay-${dialId}`);
    const trailContainer = document.getElementById(`trail-container-${dialId}`);

    let isDragging = false;
    let currentFill = 0, fadeTimeout = null;
    let animationFrame = null;
    let currentlyDraggedDial = null;
    
    // 360도를 4단계로 나눔 (90도씩) + 360도 지점도 포함
    let totalRotation = 0;
    let lastMouseAngle = 0;
    let currentStep = 0;  // 기본값 0단계
    let initialStep = 0;

    function getMouseAngle(event) {
      const rect = container.getBoundingClientRect();
      const centerX = rect.left + rect.width / 2;
      const centerY = rect.top + rect.height / 2;
      return Math.atan2(event.clientY - centerY, event.clientX - centerX) * (180 / Math.PI);
    }

    function normalizeAngleDiff(angle) {
      while (angle > 180) angle -= 360;
      while (angle < -180) angle += 360;
      return angle;
    }

    function triggerDetentFeedback(stepAngle) {
      outerRing.classList.remove('feedback-pulse');
      outerRing.style.setProperty('--current-rotation', `${stepAngle}deg`);
      outerRing.offsetHeight;
      outerRing.classList.add('feedback-pulse');
      setTimeout(() => {
        outerRing.classList.remove('feedback-pulse');
      }, 200);
    }

    function updateSoundBars(level) {
      const middleStatus = document.getElementById('status-middle');
      middleStatus.innerHTML = '';
      if (effect === 'sound') {
        for (let i = 0; i < 8; i++) {
          const bar = document.createElement('div');
          bar.className = 'bar';
          bar.style.height = `${3 + i * 2}px`;
          bar.style.opacity = i < level ? '1' : '0.15';
          middleStatus.appendChild(bar);
        }
      }
    }

    function updateTemperatureByStep(stepIdx) {
      let temp;
      if (stepIdx === 0) temp = 36.5;      // 기본값
      else if (stepIdx === 1) temp = 45.0; // 1단계
      else if (stepIdx === 2) temp = 55.0; // 2단계  
      else if (stepIdx === 3) temp = 65.0; // 3단계
      else temp = 36.5;
      
      document.getElementById('temperature-value').textContent = `${temp.toFixed(1)}°C`;
    }

    function updateDialFromStep(triggeredByUser = false) {
      // 360도를 4단계로 나눔: 0도, 90도, 180도, 270도 + 360도 지점도 포함
      const stepAngles = [0, 90, 180, 270];
      let displayAngle = stepAngles[currentStep] || 0;
      
      // 360도 지점 처리 (4단계를 넘어가면 360도로 설정)
      if (currentStep >= 4) {
        displayAngle = 360;
        currentStep = 4; // 360도 지점을 4단계로 설정
      }
      
      outerRing.style.transform = `rotate(${displayAngle}deg)`;
      
      if (triggeredByUser) {
        triggerDetentFeedback(displayAngle);
      }
      
      if (currentStep !== initialStep) {
        dialMoved[dialId] = true;
        checkFinishCondition();
      }

      if (effect === 'sound') {
        // 4단계로 나누기: 0단계=0바, 1단계=2바, 2단계=5바, 3단계=8바
        let level;
        if (currentStep === 0) level = 0;      // 소리 없음
        else if (currentStep === 1) level = 2; // 약한 소리
        else if (currentStep === 2) level = 5; // 중간 소리
        else if (currentStep === 3 || currentStep === 4) level = 8; // 강한 소리
        else level = 0;
        
        rainSound.volume = Math.min(1, Math.max(0, currentStep / 3));
        updateSoundBars(level);
      }
      if (effect === 'temperature') {
        updateTemperatureByStep(currentStep);
      }
    }

    function animateEffect(time) {
      // 왼쪽 다이얼: 4단계 진동
      let amplitude;
      if (currentStep === 0) amplitude = 0;       // 진동 없음
      else if (currentStep === 1) amplitude = 3;  // 약한 진동
      else if (currentStep === 2) amplitude = 7;  // 중간 진동
      else if (currentStep === 3 || currentStep === 4) amplitude = 12; // 강한 진동
      else amplitude = 0;
      
      if (effect === 'vibration') {
        const vibX = Math.sin(time / 20) * amplitude;
        const vibY = Math.sin(time / 15) * amplitude * 0.7;
        container.style.transform = `translate(${vibX}px, ${vibY}px)`;
        
        // 파형도 4단계로 명확히 구분
        const path = document.getElementById('waveform-path-left');
        if (path) {
          const width = 80, height = 30;
          let d = `M 0 ${height/2}`;
          
          if (currentStep === 0) {
            // 0단계: 평직선
            d = `M 0 ${height/2} L ${width} ${height/2}`;
          } else if (currentStep === 1) {
            // 1단계: 작은 파형
            const freq = 3;
            for (let x = 0; x <= width; x++) {
              const yOff = Math.sin(time/180 + (x/width)*Math.PI*freq) * 2;
              d += ` L ${x} ${height/2 + yOff}`;
            }
          } else if (currentStep === 2) {
            // 2단계: 중간 파형
            const freq = 5;
            for (let x = 0; x <= width; x++) {
              const yOff = Math.sin(time/120 + (x/width)*Math.PI*freq) * 5;
              d += ` L ${x} ${height/2 + yOff}`;
            }
          } else if (currentStep === 3 || currentStep === 4) {
            // 3단계: 큰 파형
            const freq = 7;
            for (let x = 0; x <= width; x++) {
              const yOff = Math.sin(time/80 + (x/width)*Math.PI*freq) * 10;
              d += ` L ${x} ${height/2 + yOff}`;
            }
          }
          
          path.setAttribute('d', d);
        }
      }
      animationFrame = requestAnimationFrame(animateEffect);
    }

    function reset() {
      isDragging = false;
      currentFill = 0;
      
      if (animationFrame) {
        cancelAnimationFrame(animationFrame);
        animationFrame = null;
      }
      
      // 모든 다이얼 0단계에서 시작
      totalRotation = 0;
      currentStep = 0;
      initialStep = 0;
      
      outerRing.classList.remove('no-transition', 'feedback-pulse');
      container.style.transform = 'translate(0px, 0px)';
      updateDialFromStep(false);
      updateFill();
      trailContainer.innerHTML = '';
      
      // 파형 초기화
      if (effect === 'vibration') {
        const path = document.getElementById('waveform-path-left');
        if (path) {
          path.setAttribute('d', 'M 0 15 L 80 15');
        }
      }
    }

    outerRing.addEventListener('mousedown', (e) => {
      e.preventDefault();
      isDragging = true; 
      currentlyDraggedDial = dialId;
      globalDragState.isDragging = true;
      globalDragState.dialId = dialId;
      
      lastMouseAngle = getMouseAngle(e);
      outerRing.classList.add('no-transition');

      if (effect === 'sound' && rainSound.paused) rainSound.play();
      if (effect === 'vibration') {
        if (!animationFrame) animationFrame = requestAnimationFrame(animateEffect);
      }
    });

    window.addEventListener('mousemove', (e) => {
      if (!isDragging || currentlyDraggedDial !== dialId) return;

      const currentMouseAngle = getMouseAngle(e);
      const angleDiff = normalizeAngleDiff(currentMouseAngle - lastMouseAngle);
      
      totalRotation += angleDiff;
      lastMouseAngle = currentMouseAngle;
      
      // 360도를 4단계로 나눔 (90도씩) + 360도 지점 포함
      const newStep = Math.round(totalRotation / 90);
      const clampedStep = Math.max(0, Math.min(4, newStep)); // 0~4단계 (360도 포함)
      
      if (clampedStep !== currentStep) {
        currentStep = clampedStep;
        updateDialFromStep(true); // 단계 변경 시 피드백
        
        // 범위 제한
        if (newStep < 0) {
          totalRotation = 0;
        } else if (newStep > 4) {
          totalRotation = 360; // 360도까지
        }
      } else {
        // 스텝 사이의 자유 회전
        const displayAngle = totalRotation;
        outerRing.style.transform = `rotate(${displayAngle}deg)`;
      }
    });

    window.addEventListener('mouseup', () => {
      if (isDragging && currentlyDraggedDial === dialId) {
        isDragging = false; 
        currentlyDraggedDial = null;
        globalDragState.isDragging = false;
        globalDragState.dialId = null;
        
        if (currentStep === 4) {
          totalRotation = 360; // 360도 지점
        } else {
          totalRotation = currentStep * 90;
        }
        outerRing.classList.remove('no-transition');
        updateDialFromStep(true); // 마우스 업에서도 피드백
      }
    });

    function updateFill() {
      let gradient, blendMode = 'overlay', filter = 'blur(15px)', color = 'rgba(100, 120, 255, 0.45)';
      if (currentFill === 0) gradient = 'none';
      else {
        if (fillType === 'donut') {
          const circleSize = (currentFill / fillSteps) * 100;
          gradient = `radial-gradient(circle, ${color} ${circleSize}%, transparent ${circleSize + 1}%)`;
        } else if (fillType === 'circle-out') {
          filter = 'blur(25px)';
          const innerSize = 100 - (currentFill / fillSteps) * 100;
          gradient = `radial-gradient(circle, transparent ${innerSize}%, ${color} ${innerSize + 1}%)`;
        } else {
          const fillPercent = (currentFill / fillSteps) * 100;
          gradient = `linear-gradient(to right, ${color} 0%, ${color} ${fillPercent}%, transparent ${fillPercent}%, transparent 100%)`;
        }
      }
      fillOverlay.style.background = gradient;
      fillOverlay.style.mixBlendMode = blendMode;
      fillOverlay.style.filter = filter;
    }

    innerPad.addEventListener('click', () => {
      currentFill = (currentFill < fillSteps) ? currentFill + 1 : 0;
      updateFill();
      if (fadeTimeout) clearTimeout(fadeTimeout);
      fadeTimeout = setTimeout(() => { currentFill = 0; updateFill(); }, 4000);
    });

    let trailLastTime = 0;
    innerPad.addEventListener('mousemove', (e) => {
      if (globalDragState.isDragging) return;
      
      const rect = innerPad.getBoundingClientRect();
      const x = e.clientX - rect.left, y = e.clientY - rect.top;
      const now = Date.now();
      if (now - trailLastTime > 15) {
        trailLastTime = now;
        const dot = document.createElement('div');
        dot.className = 'trail-dot';
        dot.style.left = `${x}px`; dot.style.top = `${y}px`;
        trailContainer.appendChild(dot);
        setTimeout(() => dot.remove(), 1100);
      }
    });

    updateFill();
    if (effect === 'sound') updateSoundBars(0);
    if (effect === 'temperature') updateTemperatureByStep(0);
    updateDialFromStep(false);
    
    dialInstances[dialId] = { reset };
  }

  // Dials init
  setupDial('left',   { fillSteps: 6, fillType: 'donut',     effect: 'vibration'   });
  setupDial('middle', { fillSteps: 9, fillType: 'linear',    effect: 'sound'       });
  setupDial('right',  { fillSteps: 7, fillType: 'circle-out',effect: 'temperature' });

  checkFinishCondition();

</script>
</body>
</html>
