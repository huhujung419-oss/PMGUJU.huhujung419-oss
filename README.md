<!DOCTYPE html>
<html lang="ko">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0, user-scalable=no">
  <meta name="apple-mobile-web-app-capable" content="yes">
  <title>향기 추억 제작소</title>
  <style>
    @import url('https://fonts.googleapis.com/css2?family=Pretendard:wght@300;400;500;600;700;800&display=swap');
    
    * {
      -webkit-tap-highlight-color: transparent;
      -webkit-touch-callout: none;
      -webkit-user-select: none;
      -moz-user-select: none;
      -ms-user-select: none;
      user-select: none;
      box-sizing: border-box;
    }

    body {
      margin: 0;
      padding: 0;
      font-family: 'Pretendard', -apple-system, BlinkMacSystemFont, system-ui, sans-serif;
      background: #fff;
      color: #333;
      overflow-x: hidden;
    }

    .page {
      min-height: 100vh;
      position: relative;
      overflow: hidden;
    }

    .page.hidden {
      display: none;
    }

    .fade-in {
      animation: fadeIn 0.8s ease-out;
    }

    @keyframes fadeIn {
      from { opacity: 0; transform: translateY(20px); }
      to { opacity: 1; transform: translateY(0); }
    }

    /* BACK 버튼 - 좌측 상단 고정 */
    .btn-back {
      position: fixed !important;
      top: 20px !important;
      left: 20px !important;
      background: white !important;
      color: #666 !important;
      font-size: 12px !important;
      padding: 6px 12px !important;
      font-weight: 600 !important;
      box-shadow: 0 2px 8px rgba(0,0,0,0.2) !important;
      border-radius: 15px !important;
      z-index: 9999 !important;
      border: none !important;
      cursor: pointer !important;
      text-transform: uppercase !important;
      transition: all 0.3s ease !important;
    }

    .btn-back:hover {
      color: #444 !important;
      box-shadow: 0 3px 10px rgba(0,0,0,0.25) !important;
    }

    /* 통일된 질문 위치 - 페이지 상단 고정 */
    .question-area {
      position: absolute;
      top: 60px;
      left: 50%;
      transform: translateX(-50%);
      width: 90%;
      max-width: 400px;
      text-align: center;
      z-index: 10;
    }

    .question-number {
      font-size: 14px;
      color: #999;
      margin-bottom: 10px;
      font-family: 'Pretendard', sans-serif;
    }

    .question-title {
      font-size: 16px;
      font-weight: 700;
      color: #333;
      line-height: 1.4;
      margin: 0;
      font-family: 'Pretendard', sans-serif;
    }

    .question-subtitle {
      font-size: 14px;
      color: #666;
      line-height: 1.4;
      font-family: 'Pretendard', sans-serif;
      margin: 10px 0 0 0;
    }

    /* 통일된 다이얼 위치 - 페이지 중앙 고정 */
    .dial-area {
      position: absolute;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -50%);
      width: 350px;
      height: 350px;
      display: flex;
      align-items: center;
      justify-content: center;
      z-index: 10;
    }

    /* 다이얼 배경 이미지 */
    .dial-background {
      position: absolute;
      width: 350px;
      height: 350px;
      z-index: 1;
      pointer-events: none;
      user-select: none;
      -webkit-user-drag: none;
    }

    /* 터치패드 */
    .touch-pad {
      position: absolute;
      width: 300px;
      height: 300px;
      border-radius: 50%;
      cursor: pointer;
      display: flex;
      align-items: center;
      justify-content: center;
      z-index: 2;
      background: url('https://i.imgur.com/FTZhg6Z.png') no-repeat center center;
      background-size: cover;
      overflow: hidden;
    }

    /* 터치패드 색상 오버레이 - 중앙에서 채워짐 */
    .touch-pad::before {
      content: '';
      position: absolute;
      width: 100%;
      height: 100%;
      border-radius: 50%;
      background: radial-gradient(circle, transparent 0%, transparent 100%);
      transition: all 0.4s ease;
      z-index: 1;
    }

    .touch-pad.level-0::before {
      background: radial-gradient(circle, transparent 0%, transparent 100%);
    }

    .touch-pad.level-1::before {
      background: radial-gradient(circle, rgba(153, 163, 255, 0.3) 0%, rgba(153, 163, 255, 0.1) 30%, transparent 50%);
    }

    .touch-pad.level-2::before {
      background: radial-gradient(circle, rgba(153, 163, 255, 0.5) 0%, rgba(153, 163, 255, 0.2) 60%, transparent 75%);
    }

    .touch-pad.level-3::before {
      background: radial-gradient(circle, rgba(153, 163, 255, 0.7) 0%, rgba(153, 163, 255, 0.3) 80%, transparent 90%);
    }

    /* Q1 온도 디스플레이 - LED 효과 (하얗고 뿌옇게) */
    .temperature-display {
      font-size: 20px;
      font-weight: 800;
      color: white;
      text-shadow: 0 0 12px rgba(255, 255, 255, 0.8), 0 0 20px rgba(255, 255, 255, 0.6), 0 0 30px rgba(255, 255, 255, 0.4);
      font-family: 'Pretendard', sans-serif;
      z-index: 3;
      position: relative;
      letter-spacing: 0.5px;
    }

    /* 터치 리플 효과 */
    .touch-ripple {
      position: absolute;
      border-radius: 50%;
      background: rgba(255, 255, 255, 0.4);
      transform: scale(0);
      animation: ripple 0.6s linear;
      pointer-events: none;
      z-index: 4;
    }

    @keyframes ripple {
      to {
        transform: scale(3);
        opacity: 0;
      }
    }

    /* 통일된 NEXT 버튼 위치 - 페이지 하단 고정 */
    .button-area {
      position: absolute;
      bottom: 80px;
      left: 50%;
      transform: translateX(-50%);
      z-index: 10;
    }

    /* NEXT 버튼 - 검은색 배경, 흰색 글씨, 크기 축소, PRETENDARD BOLD */
    .btn-next {
      background: #000 !important;
      color: #fff !important;
      font-weight: 700 !important;
      font-family: 'Pretendard', sans-serif !important;
      font-size: 14px !important;
      padding: 8px 20px !important;
      border-radius: 18px !important;
      width: auto !important;
      min-width: 80px !important;
      max-width: 100px !important;
      box-shadow: 0 3px 10px rgba(0,0,0,0.3) !important;
      text-transform: uppercase !important;
      cursor: pointer !important;
      transition: all 0.3s ease !important;
      border: none !important;
      letter-spacing: 0.5px !important;
    }

    .btn-next:hover:not(.disabled) {
      background: #222 !important;
      transform: translateY(-1px) !important;
      box-shadow: 0 4px 12px rgba(0,0,0,0.4) !important;
    }

    .btn-next:active {
      transform: translateY(0px) !important;
    }

    .btn-next.disabled {
      background: #555 !important;
      color: #aaa !important;
      cursor: not-allowed !important;
      box-shadow: none !important;
      transform: none !important;
    }

    /* START 페이지 */
    .start-page {
      background: linear-gradient(135deg, #f8f9ff 0%, #fff 50%, #f0f2ff 100%);
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      padding: 40px 20px;
    }

    .start-header {
      text-align: center;
      margin-bottom: 60px;
    }

    .start-title {
      font-size: 28px;
      font-weight: 500;
      color: #333;
      line-height: 1.4;
      margin: 0 0 20px 0;
      letter-spacing: -0.5px;
    }

    .start-subtitle {
      font-size: 16px;
      font-weight: 400;
      color: #666;
      line-height: 1.5;
      margin: 0;
    }

    .input-section {
      margin-bottom: 80px;
    }

    .input-container {
      position: relative;
      width: 300px;
    }

    .name-input {
      width: 100%;
      padding: 15px 5px;
      font-size: 18px;
      font-weight: 400;
      color: #333;
      background: transparent;
      border: none;
      outline: none;
      text-align: center;
      font-family: 'Pretendard', sans-serif;
    }

    .name-input::placeholder {
      color: #aaa;
      font-weight: 300;
    }

    .input-line {
      position: absolute;
      bottom: 0;
      left: 0;
      width: 100%;
      height: 2px;
      background: #ddd;
      transition: all 0.3s ease;
    }

    .input-container:focus-within .input-line {
      background: #9EA4FF;
      transform: scaleY(1.5);
    }

    .btn {
      font-family: 'Pretendard', sans-serif;
      font-weight: 600;
      border: none;
      border-radius: 25px;
      cursor: pointer;
      transition: all 0.3s ease;
      text-transform: uppercase;
      letter-spacing: 0.5px;
      touch-action: manipulation;
      outline: none;
      padding: 16px 40px;
      font-size: 18px;
      background: #333;
      color: white;
      box-shadow: 0 4px 15px rgba(51, 51, 51, 0.2);
    }

    .btn:hover:not(.disabled) {
      background: #222;
      transform: translateY(-2px);
      box-shadow: 0 6px 20px rgba(51, 51, 51, 0.3);
    }

    .btn.disabled {
      background: #ccc !important;
      color: #888 !important;
      cursor: not-allowed !important;
      transform: none !important;
      box-shadow: none !important;
    }

    .btn-secondary {
      background: #9EA4FF;
      box-shadow: 0 4px 15px rgba(158, 164, 255, 0.2);
    }

    .btn-secondary:hover:not(.disabled) {
      background: #8A91FF;
      box-shadow: 0 6px 20px rgba(158, 164, 255, 0.3);
    }

    /* 페이지별 배경 */
    .q1-page {
      background: linear-gradient(135deg, #fff8f0 0%, #fff 50%, #f0f8ff 100%);
    }

    .q2-page {
      background: linear-gradient(135deg, #f0fff4 0%, #fff 50%, #f8fff8 100%);
    }

    .q3-page {
      background: linear-gradient(135deg, #f0f8ff 0%, #fff 50%, #e6f3ff 100%);
    }

    .q4-page {
      background: linear-gradient(135deg, #fff0f5 0%, #fff 50%, #fdf0f8 100%);
    }

    /* Q2 날씨 선택 영역 */
    .weather-area {
      position: absolute;
      top: 140px;
      left: 50%;
      transform: translateX(-50%);
      z-index: 10;
    }

    .weather-buttons {
      display: flex;
      justify-content: center;
      gap: 15px;
      margin-bottom: 30px;
      flex-wrap: wrap;
    }

    .weather-btn {
      padding: 12px 24px;
      font-size: 16px;
      border: none;
      border-radius: 25px;
      background: #fff;
      color: #666;
      cursor: pointer;
      transition: all 0.3s ease;
      font-family: 'Pretendard', sans-serif;
      font-weight: 500;
      position: relative;
      box-shadow: 0 2px 8px rgba(0, 0, 0, 0.1);
    }

    .weather-btn:hover {
      color: #5A67D8;
      box-shadow: 0 4px 12px rgba(0, 0, 0, 0.15);
    }

    .weather-btn.selected::after {
      content: '';
      position: absolute;
      top: -4px;
      right: 6px;
      width: 8px;
      height: 8px;
      background: #5A67D8;
      border-radius: 50%;
      box-shadow: 0 1px 3px rgba(90, 103, 216, 0.3);
    }

    /* Q2 다이얼 진동 효과 */
    .q2-draggable-dial {
      position: absolute;
      width: 350px;
      height: 350px;
      cursor: grab;
      user-select: none;
      -webkit-user-drag: none;
      transition: transform 0.2s cubic-bezier(0.4, 0.0, 0.2, 1);
      transform-origin: center center;
      z-index: 2;
    }

    .q2-draggable-dial:active {
      cursor: grabbing;
    }

    .q2-draggable-dial.no-transition {
      transition: none;
    }

    .q2-draggable-dial.vibration-0 {
      animation: none;
    }

    .q2-draggable-dial.vibration-1 {
      animation: vibrate-1 0.1s infinite;
    }

    .q2-draggable-dial.vibration-2 {
      animation: vibrate-2 0.08s infinite;
    }

    .q2-draggable-dial.vibration-3 {
      animation: vibrate-3 0.06s infinite;
    }

    @keyframes vibrate-1 {
      0%, 100% { transform: rotate(var(--rotation, 0deg)) translate(0px, 0px); }
      25% { transform: rotate(var(--rotation, 0deg)) translate(0.5px, 0.5px); }
      50% { transform: rotate(var(--rotation, 0deg)) translate(-0.5px, 0px); }
      75% { transform: rotate(var(--rotation, 0deg)) translate(0px, -0.5px); }
    }

    @keyframes vibrate-2 {
      0%, 100% { transform: rotate(var(--rotation, 0deg)) translate(0px, 0px); }
      25% { transform: rotate(var(--rotation, 0deg)) translate(1px, 1px); }
      50% { transform: rotate(var(--rotation, 0deg)) translate(-1px, 0px); }
      75% { transform: rotate(var(--rotation, 0deg)) translate(0px, -1px); }
    }

    @keyframes vibrate-3 {
      0%, 100% { transform: rotate(var(--rotation, 0deg)) translate(0px, 0px); }
      20% { transform: rotate(var(--rotation, 0deg)) translate(1.5px, 1.5px); }
      40% { transform: rotate(var(--rotation, 0deg)) translate(-1.5px, 1px); }
      60% { transform: rotate(var(--rotation, 0deg)) translate(1px, -1.5px); }
      80% { transform: rotate(var(--rotation, 0deg)) translate(-1px, -1px); }
    }

    /* Q2 터치패드 배경 */
    .q2-touch-pad {
      position: absolute;
      width: 300px;
      height: 300px;
      border-radius: 50%;
      z-index: 1;
      background: url('https://i.imgur.com/FTZhg6Z.png') no-repeat center center;
      background-size: cover;
      pointer-events: none;
    }

    /* 파형 진동 바 */
    .waveform-container {
      position: absolute;
      top: -50px;
      left: 50%;
      transform: translateX(-50%);
      z-index: 3;
      width: 200px;
      height: 30px;
    }

    .waveform-svg {
      width: 100%;
      height: 100%;
    }

    .waveform-path {
      stroke: #9EA4FF;
      stroke-width: 2;
      fill: none;
      transition: stroke 0.3s ease;
    }

    .waveform-path.level-0 {
      stroke: #ddd;
      opacity: 0.3;
    }

    .waveform-path.level-1 {
      stroke: #9EA4FF;
      opacity: 0.6;
    }

    .waveform-path.level-2 {
      stroke: #7B83FF;
      opacity: 0.8;
    }

    .waveform-path.level-3 {
      stroke: #5A67D8;
      opacity: 1.0;
    }

    /* Q3, Q4 추가 선택 영역 */
    .selection-area {
      position: absolute;
      bottom: 200px;
      left: 50%;
      transform: translateX(-50%);
      display: flex;
      gap: 30px;
      z-index: 10;
    }

    /* Q4 감정 다이얼 */
    .emotion-dial-area {
      position: absolute;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -50%);
      text-align: center;
      z-index: 10;
    }

    .emotion-display {
      font-size: 32px;
      font-weight: 600;
      color: #d2691e;
      margin-bottom: 20px;
      text-shadow: 0 2px 4px rgba(0,0,0,0.1);
      font-family: 'Pretendard', sans-serif;
    }

    .dial-control {
      width: 250px;
      height: 100px;
      margin: 0 auto;
      position: relative;
      display: flex;
      align-items: center;
      justify-content: center;
    }

    .dial-input {
      width: 200px;
      height: 8px;
      background: #ddd;
      border-radius: 5px;
      outline: none;
      cursor: pointer;
      -webkit-appearance: none;
      appearance: none;
    }

    .dial-input::-webkit-slider-thumb {
      width: 25px;
      height: 25px;
      background: #9EA4FF;
      border-radius: 50%;
      cursor: pointer;
      -webkit-appearance: none;
      appearance: none;
      box-shadow: 0 2px 6px rgba(158, 164, 255, 0.3);
    }

    .dial-input::-moz-range-thumb {
      width: 25px;
      height: 25px;
      background: #9EA4FF;
      border-radius: 50%;
      cursor: pointer;
      border: none;
      box-shadow: 0 2px 6px rgba(158, 164, 255, 0.3);
    }

    /* 로딩 페이지 */
    .loading-page {
      background: linear-gradient(135deg, #f8f9ff 0%, #fff 50%, #f0f2ff 100%);
      display: flex;
      align-items: center;
      justify-content: center;
    }

    .loading-text {
      font-size: 24px;
      font-weight: 500;
      color: #666;
      text-align: center;
      animation: pulse 2s ease-in-out infinite;
      font-family: 'Pretendard', sans-serif;
    }

    @keyframes pulse {
      0%, 100% { opacity: 0.6; }
      50% { opacity: 1; }
    }

    /* 결과 페이지 */
    .result-page {
      background: linear-gradient(135deg, #fff8f0 0%, #fff 50%, #f0f8ff 100%);
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      padding: 40px 20px;
    }

    .result-message {
      font-size: 24px;
      font-weight: 500;
      color: #333;
      text-align: center;
      margin-bottom: 40px;
      font-family: 'Pretendard', sans-serif;
    }

    .result-image-container {
      margin-bottom: 40px;
    }

    .result-image {
      max-width: 200px;
      max-height: 200px;
      border-radius: 15px;
      box-shadow: 0 8px 25px rgba(0,0,0,0.1);
    }

    /* 모바일 반응형 */
    @media (max-width: 768px) {
      .start-title {
        font-size: 24px;
      }
      
      .start-subtitle {
        font-size: 14px;
      }
      
      .input-container {
        width: 280px;
      }
      
      .name-input {
        font-size: 16px;
      }

      .question-title {
        font-size: 15px;
      }

      .dial-area {
        width: 300px;
        height: 300px;
      }

      .dial-background, .q2-draggable-dial {
        width: 300px;
        height: 300px;
      }

      .touch-pad, .q2-touch-pad {
        width: 260px;
        height: 260px;
      }

      .temperature-display {
        font-size: 18px;
      }

      .weather-buttons {
        gap: 10px;
      }

      .weather-btn {
        padding: 10px 20px;
        font-size: 14px;
      }

      .btn {
        padding: 14px 35px;
        font-size: 16px;
      }

      .waveform-container {
        width: 150px;
        height: 25px;
        top: -40px;
      }

      .selection-area {
        flex-direction: column;
        gap: 15px;
        bottom: 180px;
      }
    }

    @media (max-width: 480px) {
      .start-title {
        font-size: 22px;
      }
      
      .input-container {
        width: 260px;
      }

      .dial-area {
        width: 260px;
        height: 260px;
      }

      .dial-background, .q2-draggable-dial {
        width: 260px;
        height: 260px;
      }

      .touch-pad, .q2-touch-pad {
        width: 220px;
        height: 220px;
      }

      .temperature-display {
        font-size: 16px;
      }

      .dial-control {
        width: 200px;
      }

      .dial-input {
        width: 150px;
      }

      .waveform-container {
        width: 120px;
        height: 20px;
        top: -35px;
      }
    }
  </style>
</head>
<body>
  <!-- START 페이지 -->
  <div id="start-page" class="page start-page fade-in">
    <div class="start-header">
      <h1 class="start-title">
        당신만의 지구 추억의<br>
        향과 향수병을 제작해보세요.
      </h1>
      <p class="start-subtitle">
        아래 칸에 펜으로 이름을 작성하신 뒤<br>
        start 버튼을 눌러주세요.
      </p>
    </div>

    <div class="input-section">
      <div class="input-container">
        <input
          type="text"
          id="name-input"
          placeholder="이름을 입력해주세요"
          class="name-input"
          maxlength="20"
        >
        <div class="input-line"></div>
      </div>
    </div>

    <div>
      <button id="start-btn" class="btn disabled">START</button>
    </div>
  </div>

  <!-- Q1 페이지 (온도 질문) -->
  <div id="q1-page" class="page q1-page hidden">
    <button id="q1-back-btn" class="btn-back">BACK</button>
    
    <div class="question-area">
      <div class="question-number">*총 네개의 질문으로 구성되어있습니다.</div>
      <h2 class="question-title">Q1. 그 때의 주변의 온도는 어땠나요?</h2>
      <p class="question-subtitle">가운데 패드를 터치하여 온도를 떠올려보세요.</p>
    </div>

    <div class="dial-area">
      <img src="https://i.imgur.com/okVDs9K.png" alt="다이얼 이미지" class="dial-background">
      <div id="touch-pad" class="touch-pad level-0">
        <div id="temperature-display" class="temperature-display">36.5°C</div>
      </div>
    </div>

    <div class="button-area">
      <button id="q1-next-btn" class="btn-next disabled">NEXT</button>
    </div>
  </div>

  <!-- Q2 페이지 (날씨 질문) -->
  <div id="q2-page" class="page q2-page hidden">
    <button id="q2-back-btn" class="btn-back">BACK</button>
    
    <div class="question-area">
      <h2 class="question-title">Q2. 그 날의 날씨는 어땠나요? 날씨를 클릭하고 다이얼을 돌려 날씨의 강도를 표현해주세요.</h2>
    </div>

    <div class="weather-area">
      <div class="weather-buttons">
        <button id="weather-clear-btn" class="weather-btn selected">맑음</button>
        <button id="weather-rain-btn" class="weather-btn">비</button>
        <button id="weather-snow-btn" class="weather-btn">눈</button>
        <button id="weather-wind-btn" class="weather-btn">바람</button>
      </div>
    </div>

    <div class="dial-area">
      <div class="waveform-container">
        <svg class="waveform-svg" viewBox="0 0 200 30">
          <path id="waveform-path" class="waveform-path level-0" d="M 10 15 L 30 15 Q 35 10 40 15 T 50 15 L 60 15 Q 70 8 80 15 T 100 15 L 110 15 Q 120 12 130 15 T 150 15 L 170 15 Q 175 18 180 15 T 190 15" />
        </svg>
      </div>

      <div class="q2-touch-pad"></div>
      <img id="q2-draggable-dial" src="https://i.imgur.com/okVDs9K.png" alt="드래그 가능한 다이얼" class="q2-draggable-dial vibration-0">
    </div>

    <div class="button-area">
      <button id="q2-next-btn" class="btn-next disabled">NEXT</button>
    </div>
  </div>

  <!-- Q3 페이지 (환경 질문) -->
  <div id="q3-page" class="page q3-page hidden">
    <button id="q3-back-btn" class="btn-back">BACK</button>
    
    <div class="question-area">
      <div class="question-number">*총 네개의 질문으로 구성되어있습니다.</div>
      <h2 class="question-title">Q3. 그 때의 주변 환경은 자연과 도시중 어느곳에 가까웠나요?</h2>
    </div>

    <div class="dial-area">
      <img src="https://i.imgur.com/okVDs9K.png" alt="다이얼 이미지" class="dial-background">
      <div id="q3-touch-pad" class="touch-pad level-0"></div>
    </div>

    <div class="selection-area">
      <button id="env-nature-btn" class="btn btn-secondary">자연</button>
      <button id="env-city-btn" class="btn btn-secondary">도시</button>
    </div>

    <div class="button-area">
      <button id="q3-next-btn" class="btn-next disabled">NEXT</button>
    </div>
  </div>

  <!-- Q4 페이지 (마음 상태) -->
  <div id="q4-page" class="page q4-page hidden">
    <button id="q4-back-btn" class="btn-back">BACK</button>
    
    <div class="question-area">
      <div class="question-number">*총 네개의 질문으로 구성되어있습니다.</div>
      <h2 class="question-title">Q4. 그 때 내 마음은 어땠나요?</h2>
      <p class="question-subtitle">다이얼을 돌려 온도로 마음의 상태를 표현해보세요.</p>
    </div>

    <div class="emotion-dial-area">
      <div id="emotion-temperature-display" class="emotion-display">25°C</div>
      <div class="dial-control">
        <input id="emotion-dial" class="dial-input" type="range" min="15" max="35" value="25">
      </div>
    </div>

    <div class="button-area">
      <button id="q4-finish-btn" class="btn-next">FINISH</button>
    </div>
  </div>

  <!-- 로딩 페이지 -->
  <div id="loading-page" class="page loading-page hidden">
    <div class="loading-text">향기 만드는 중...</div>
  </div>

  <!-- 결과 페이지 -->
  <div id="result-page" class="page result-page hidden">
    <div class="result-message" id="result-message">님의 추억의 향기가 완성 되었습니다.</div>
    
    <div class="result-image-container">
      <img id="result-image" class="result-image" src="https://i.imgur.com/uwJHQSt.png" alt="완성된 향기 이미지">
    </div>

    <div>
      <button id="result-home-btn" class="btn btn-secondary">HOME</button>
    </div>
  </div>

  <script>
    // 전역 상태
    let currentPage = 'start';
    let answers = {};
    let touchLevel = 0;
    let selectedWeather = 'clear';
    let q2DialRotation = 0;
    let q2DialStep = 0;

    // 온도 단계 (36.5°C부터 5도씩 증가)
    const temperatureLevels = [36.5, 41.5, 46.5, 51.5];

    // 결과 이미지들
    const resultImages = [
      'https://i.imgur.com/uwJHQSt.png',
      'https://i.imgur.com/rYmbPsr.png', 
      'https://i.imgur.com/KI2WR6a.png'
    ];

    // DOM 요소들
    const nameInput = document.getElementById('name-input');
    const startBtn = document.getElementById('start-btn');
    const touchPad = document.getElementById('touch-pad');
    const temperatureDisplay = document.getElementById('temperature-display');
    const q1NextBtn = document.getElementById('q1-next-btn');

    // Q2 요소들
    const q2DraggableDial = document.getElementById('q2-draggable-dial');
    const waveformPath = document.getElementById('waveform-path');

    // Q3 요소들
    const q3TouchPad = document.getElementById('q3-touch-pad');

    // 페이지 전환 함수
    function showPage(pageId) {
      document.querySelectorAll('.page').forEach(page => {
        page.classList.add('hidden');
      });
      
      const targetPage = document.getElementById(pageId + '-page');
      if (targetPage) {
        targetPage.classList.remove('hidden');
        targetPage.classList.add('fade-in');
      }
      
      currentPage = pageId;
      console.log('현재 페이지:', pageId);
    }

    // ========== BACK 버튼 이벤트 리스너들 ==========
    document.getElementById('q1-back-btn').addEventListener('click', function() {
      showPage('start');
    });

    document.getElementById('q2-back-btn').addEventListener('click', function() {
      showPage('q1');
    });

    document.getElementById('q3-back-btn').addEventListener('click', function() {
      showPage('q2');
    });

    document.getElementById('q4-back-btn').addEventListener('click', function() {
      showPage('q3');
    });

    // START 페이지 로직
    nameInput.addEventListener('input', function() {
      const isValid = this.value.trim().length > 0;
      startBtn.classList.toggle('disabled', !isValid);
    });

    nameInput.addEventListener('keypress', function(e) {
      if (e.key === 'Enter' && !startBtn.classList.contains('disabled')) {
        handleStart();
      }
    });

    startBtn.addEventListener('click', handleStart);

    function handleStart() {
      if (startBtn.classList.contains('disabled')) return;
      
      answers.userName = nameInput.value.trim();
      console.log('사용자 이름:', answers.userName);
      showPage('q1');
    }

    // Q1 페이지 로직 (온도 터치패드) - 순환 구조
    touchPad.addEventListener('click', function(e) {
      if (touchLevel === 3) {
        touchLevel = 0;
      } else {
        touchLevel++;
      }
      
      touchPad.className = `touch-pad level-${touchLevel}`;
      
      const currentTemp = temperatureLevels[touchLevel];
      temperatureDisplay.textContent = currentTemp + '°C';
      answers.temperature = currentTemp;
      
      // 리플 효과
      const rect = this.getBoundingClientRect();
      const ripple = document.createElement('span');
      const size = 120;
      const x = e.clientX - rect.left - size / 2;
      const y = e.clientY - rect.top - size / 2;
      
      ripple.classList.add('touch-ripple');
      ripple.style.width = ripple.style.height = size + 'px';
      ripple.style.left = x + 'px';
      ripple.style.top = y + 'px';
      
      this.appendChild(ripple);
      
      setTimeout(() => {
        ripple.remove();
      }, 600);

      if (touchLevel > 0) {
        q1NextBtn.classList.remove('disabled');
      } else {
        q1NextBtn.classList.add('disabled');
      }
      
      console.log('현재 터치 레벨:', touchLevel, '온도:', currentTemp + '°C');
    });

    q1NextBtn.addEventListener('click', function() {
      if (this.classList.contains('disabled')) return;
      
      console.log('선택된 온도:', answers.temperature);
      showPage('q2');
    });

    // Q2 페이지 로직 (날씨 선택 + 다이얼)
    const weatherButtons = [
      document.getElementById('weather-clear-btn'),
      document.getElementById('weather-rain-btn'),
      document.getElementById('weather-snow-btn'),
      document.getElementById('weather-wind-btn')
    ];
    const q2NextBtn = document.getElementById('q2-next-btn');

    let isQ2Dragging = false;
    let q2LastAngle = 0;

    // 각도 계산 함수
    function getQ2Angle(clientX, clientY) {
      const rect = q2DraggableDial.getBoundingClientRect();
      const centerX = rect.left + rect.width / 2;
      const centerY = rect.top + rect.height / 2;
      return Math.atan2(clientY - centerY, clientX - centerX) * (180 / Math.PI);
    }

    // 각도 차이 정규화
    function normalizeQ2AngleDiff(angle) {
      while (angle > 180) angle -= 360;
      while (angle < -180) angle += 360;
      return angle;
    }

    // Q2 다이얼 피드백 애니메이션
    function triggerQ2DialFeedback(stepAngle) {
      q2DraggableDial.classList.remove('feedback');
      q2DraggableDial.style.setProperty('--current-rotation', `${stepAngle}deg`);
      q2DraggableDial.offsetHeight;
      q2DraggableDial.classList.add('feedback');
      setTimeout(() => {
        q2DraggableDial.classList.remove('feedback');
      }, 200);
    }

    // Q2 진동 및 파형 업데이트
    function updateQ2Vibration() {
      // 진동 클래스 업데이트 (다이얼 흔들림)
      q2DraggableDial.className = `q2-draggable-dial vibration-${q2DialStep}`;
      
      // 파형 상태 업데이트 (흔들림 없음)
      waveformPath.className = `waveform-path level-${q2DialStep}`;
      
      // 회전 각도 설정
      const stepAngles = [0, 90, 180, 270];
      const targetAngle = stepAngles[q2DialStep];
      q2DraggableDial.style.setProperty('--rotation', `${targetAngle}deg`);
      
      if (q2DialStep > 0) {
        answers.weather = {
          type: selectedWeather,
          intensity: q2DialStep
        };
        q2NextBtn.classList.remove('disabled');
      } else {
        q2NextBtn.classList.add('disabled');
      }
    }

    // Q2 드래그 시작
    function startQ2Drag(e) {
      isQ2Dragging = true;
      const clientX = e.touches ? e.touches[0].clientX : e.clientX;
      const clientY = e.touches ? e.touches[0].clientY : e.clientY;
      q2LastAngle = getQ2Angle(clientX, clientY);
      
      q2DraggableDial.classList.add('no-transition');
      e.preventDefault();
    }

    // Q2 드래그 중
    function moveQ2Drag(e) {
      if (!isQ2Dragging) return;
      
      const clientX = e.touches ? e.touches[0].clientX : e.clientX;
      const clientY = e.touches ? e.touches[0].clientY : e.clientY;
      const currentAngle = getQ2Angle(clientX, clientY);
      
      const angleDiff = normalizeQ2AngleDiff(currentAngle - q2LastAngle);
      
      q2DialRotation += angleDiff;
      q2DialRotation = Math.max(0, Math.min(270, q2DialRotation));
      
      const newStep = Math.round(q2DialRotation / 90);
      
      if (newStep !== q2DialStep && newStep >= 0 && newStep <= 3) {
        q2DialStep = newStep;
        triggerQ2DialFeedback(q2DialStep * 90);
        updateQ2Vibration();
      } else {
        const currentRotation = q2DialRotation;
        q2DraggableDial.style.setProperty('--rotation', `${currentRotation}deg`);
      }
      
      q2LastAngle = currentAngle;
      e.preventDefault();
    }

    // Q2 드래그 종료
    function endQ2Drag() {
      if (!isQ2Dragging) return;
      
      isQ2Dragging = false;
      q2DialRotation = q2DialStep * 90;
      
      q2DraggableDial.classList.remove('no-transition');
      updateQ2Vibration();
    }

    // Q2 다이얼 이벤트 리스너
    q2DraggableDial.addEventListener('mousedown', startQ2Drag);
    document.addEventListener('mousemove', moveQ2Drag);
    document.addEventListener('mouseup', endQ2Drag);

    q2DraggableDial.addEventListener('touchstart', startQ2Drag, { passive: false });
    document.addEventListener('touchmove', moveQ2Drag, { passive: false });
    document.addEventListener('touchend', endQ2Drag);

    // Q2 날씨 선택 버튼
    weatherButtons.forEach((btn, index) => {
      btn.addEventListener('click', function() {
        const weatherTypes = ['clear', 'rain', 'snow', 'wind'];
        selectQ2Weather(weatherTypes[index], this);
      });
    });

    function selectQ2Weather(weather, button) {
      weatherButtons.forEach(btn => btn.classList.remove('selected'));
      button.classList.add('selected');
      
      selectedWeather = weather;
      console.log('선택된 날씨:', weather);
      
      updateQ2Vibration();
    }

    q2NextBtn.addEventListener('click', function() {
      if (this.classList.contains('disabled')) return;
      console.log('날씨 정보:', answers.weather);
      showPage('q3');
    });

    // Q3 페이지 로직 (환경 선택)
    const envNatureBtn = document.getElementById('env-nature-btn');
    const envCityBtn = document.getElementById('env-city-btn');
    const q3NextBtn = document.getElementById('q3-next-btn');

    envNatureBtn.addEventListener('click', function() {
      selectEnvironment('nature', this);
    });

    envCityBtn.addEventListener('click', function() {
      selectEnvironment('city', this);
    });

    function selectEnvironment(env, button) {
      envNatureBtn.classList.remove('selected');
      envCityBtn.classList.remove('selected');
      button.classList.add('selected');
      
      q3TouchPad.className = 'touch-pad level-2';
      
      answers.environment = env;
      q3NextBtn.classList.remove('disabled');
      console.log('선택된 환경:', env);
    }

    q3NextBtn.addEventListener('click', function() {
      if (this.classList.contains('disabled')) return;
      showPage('q4');
    });

    // Q4 페이지 로직 (마음 상태)
    const emotionDial = document.getElementById('emotion-dial');
    const emotionTempDisplay = document.getElementById('emotion-temperature-display');
    const q4FinishBtn = document.getElementById('q4-finish-btn');

    emotionDial.addEventListener('input', function() {
      const temp = this.value;
      emotionTempDisplay.textContent = temp + '°C';
      answers.emotion = parseInt(temp);
      console.log('마음 온도:', temp);
    });

    q4FinishBtn.addEventListener('click', function() {
      console.log('모든 답변 완료:', answers);
      showLoading();
    });

    // 로딩 및 결과 표시
    function showLoading() {
      showPage('loading');
      
      setTimeout(() => {
        showResult();
      }, 3000);
    }

    function showResult() {
      const randomIndex = Math.floor(Math.random() * resultImages.length);
      const selectedImage = resultImages[randomIndex];
      
      document.getElementById('result-image').src = selectedImage;
      document.getElementById('result-message').textContent = 
        `${answers.userName}님의 추억의 향기가 완성 되었습니다.`;
      
      showPage('result');
    }

    // HOME 버튼 (처음으로)
    document.getElementById('result-home-btn').addEventListener('click', function() {
      answers = {};
      touchLevel = 0;
      selectedWeather = 'clear';
      q2DialRotation = 0;
      q2DialStep = 0;
      
      nameInput.value = '';
      startBtn.classList.add('disabled');
      
      document.querySelectorAll('.btn').forEach(btn => {
        btn.classList.remove('selected', 'disabled');
      });
      
      touchPad.className = 'touch-pad level-0';
      temperatureDisplay.textContent = '36.5°C';
      
      document.getElementById('weather-clear-btn').classList.add('selected');
      q2DraggableDial.className = 'q2-draggable-dial vibration-0';
      q2DraggableDial.style.setProperty('--rotation', '0deg');
      waveformPath.className = 'waveform-path level-0';
      
      q3TouchPad.className = 'touch-pad level-0';
      
      emotionDial.value = 25;
      emotionTempDisplay.textContent = '25°C';
      
      q1NextBtn.classList.add('disabled');
      q2NextBtn.classList.add('disabled');
      q3NextBtn.classList.add('disabled');
      
      showPage('start');
    });

    // 터치 지원
    touchPad.addEventListener('touchstart', function(e) {
      e.preventDefault();
      this.click();
    });

    // 초기화
    selectedWeather = 'clear';
    updateQ2Vibration();
    console.log('향기 추억 제작소가 시작되었습니다!');
  </script>
</body>
</html>
