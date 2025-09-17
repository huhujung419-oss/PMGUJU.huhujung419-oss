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
      background: #ffffff;
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

    /* 질문 위치 및 크기 조정 */
    .question-area {
      position: absolute;
      top: 60px;
      left: 50%;
      transform: translateX(-50%);
      width: 90%;
      max-width: 380px;
      text-align: center;
      z-index: 10;
    }

    .question-number {
      font-size: 16px;
      color: #777;
      margin-bottom: 8px;
      font-family: 'Pretendard', sans-serif;
    }

    .question-title {
      font-size: 20px;
      font-weight: 700;
      color: #222;
      line-height: 1.3;
      margin: 0;
      font-family: 'Pretendard', sans-serif;
    }

    .question-subtitle {
      font-size: 18px;
      color: #555;
      line-height: 1.4;
      font-family: 'Pretendard', sans-serif;
      margin: 12px 0 0 0;
    }

    /* 다이얼 위치 */
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
      transition: transform 0.3s ease;
    }

    /* Q3 다이얼은 드래그 가능하고 회전됨 */
    .q3-draggable-dial {
      cursor: grab;
      pointer-events: all;
      transition: transform 0.3s ease;
    }

    .q3-draggable-dial:active {
      cursor: grabbing;
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

    /* 터치패드 색상 오버레이 */
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

    /* Q1 온도 디스플레이 - LED 효과 (흰색 글자) */
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

    /* NEXT 버튼 위치 */
    .button-area {
      position: absolute;
      bottom: 50px;
      left: 50%;
      transform: translateX(-50%);
      z-index: 10;
    }

    /* NEXT 버튼 스타일 */
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

    .btn-next.disabled {
      background: #555 !important;
      color: #aaa !important;
      cursor: not-allowed !important;
      box-shadow: none !important;
      transform: none !important;
    }

    /* START 페이지 */
    .start-page {
      background: #ffffff;
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

    /* Q2 날씨 선택 영역 */
    .weather-area {
      position: absolute;
      top: 160px;
      left: 50%;
      transform: translateX(-50%);
      z-index: 10;
      width: 100%;
      max-width: 320px;
    }

    .weather-buttons {
      display: flex;
      justify-content: center;
      gap: 8px;
      margin-bottom: 30px;
      flex-wrap: wrap;
    }

    .weather-btn {
      padding: 10px 18px;
      font-size: 15px;
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
      min-width: 65px;
    }

    .weather-btn:hover {
      color: #5A67D8;
      box-shadow: 0 4px 12px rgba(0, 0, 0, 0.15);
    }

    .weather-btn::after {
      content: '';
      position: absolute;
      top: -4px;
      right: 6px;
      width: 8px;
      height: 8px;
      background: #5A67D8;
      border-radius: 50%;
      box-shadow: 0 1px 3px rgba(90, 103, 216, 0.3);
      display: none;
    }

    .weather-btn.selected::after {
      display: block;
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

    /* Q2 터치패드 - 다이얼과 함께 진동 */
    .q2-touch-pad {
      position: absolute;
      width: 300px;
      height: 300px;
      border-radius: 50%;
      z-index: 3;
      background: url('https://i.imgur.com/FTZhg6Z.png') no-repeat center center;
      background-size: cover;
      pointer-events: none;
    }

    .q2-touch-pad.vibration-0 {
      animation: none;
    }

    .q2-touch-pad.vibration-1 {
      animation: vibrate-pad-1 0.1s infinite;
    }

    .q2-touch-pad.vibration-2 {
      animation: vibrate-pad-2 0.08s infinite;
    }

    .q2-touch-pad.vibration-3 {
      animation: vibrate-pad-3 0.06s infinite;
    }

    @keyframes vibrate-pad-1 {
      0%, 100% { transform: translate(0px, 0px); }
      25% { transform: translate(0.5px, 0.5px); }
      50% { transform: translate(-0.5px, 0px); }
      75% { transform: translate(0px, -0.5px); }
    }

    @keyframes vibrate-pad-2 {
      0%, 100% { transform: translate(0px, 0px); }
      25% { transform: translate(1px, 1px); }
      50% { transform: translate(-1px, 0px); }
      75% { transform: translate(0px, -1px); }
    }

    @keyframes vibrate-pad-3 {
      0%, 100% { transform: translate(0px, 0px); }
      20% { transform: translate(1.5px, 1.5px); }
      40% { transform: translate(-1.5px, 1px); }
      60% { transform: translate(1px, -1.5px); }
      80% { transform: translate(-1px, -1px); }
    }

    /* 진동바 파형 - 얇게 수정하고 흐르는 애니메이션 추가 */
    .waveform-container {
      position: absolute;
      top: -50px;
      left: 50%;
      transform: translateX(-50%);
      z-index: 4;
      width: 160px;
      height: 30px;
    }

    .waveform-svg {
      width: 100%;
      height: 100%;
    }

    .waveform-path {
      stroke: #666;
      stroke-width: 2; /* 3에서 2로 얇게 수정 */
      fill: none;
      transition: all 0.3s ease;
    }

    /* 파형 흐르는 애니메이션 */
    .waveform-path.level-0 {
      stroke: #666;
      opacity: 0.8;
      animation: none;
    }

    .waveform-path.level-1 {
      stroke: #7B83FF;
      opacity: 0.9;
      animation: waveFlow 2s linear infinite;
    }

    .waveform-path.level-2 {
      stroke: #5A67D8;
      opacity: 0.95;
      animation: waveFlow 1.5s linear infinite;
    }

    .waveform-path.level-3 {
      stroke: #3F51B5;
      opacity: 1.0;
      animation: waveFlow 1s linear infinite;
    }

    @keyframes waveFlow {
      0% {
        stroke-dasharray: 0 200;
        stroke-dashoffset: 0;
      }
      50% {
        stroke-dasharray: 100 100;
        stroke-dashoffset: -50;
      }
      100% {
        stroke-dasharray: 0 200;
        stroke-dashoffset: -200;
      }
    }

    /* Q3 이모지 표시 */
    .emoji-display {
      position: absolute;
      top: -45px;
      left: 50%;
      transform: translateX(-50%);
      z-index: 5;
      font-size: 32px;
      transition: all 0.3s ease;
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
      background: #ffffff;
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
      background: #ffffff;
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
      
      .question-title {
        font-size: 18px;
      }

      .question-subtitle {
        font-size: 16px;
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

      .waveform-container {
        width: 120px;
      }

      .emoji-display {
        font-size: 28px;
        top: -40px;
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
        <button id="weather-clear-btn" class="weather-btn">맑음</button>
        <button id="weather-rain-btn" class="weather-btn">비</button>
        <button id="weather-snow-btn" class="weather-btn">눈</button>
        <button id="weather-wind-btn" class="weather-btn">바람</button>
      </div>
    </div>

    <div class="dial-area">
      <div class="waveform-container">
        <svg class="waveform-svg" viewBox="0 0 160 30">
          <path id="waveform-path" class="waveform-path level-0" d="M 10 15 L 150 15" />
        </svg>
      </div>

      <img id="q2-draggable-dial" src="https://i.imgur.com/okVDs9K.png" alt="드래그 가능한 다이얼" class="q2-draggable-dial vibration-0">
      <div id="q2-touch-pad" class="q2-touch-pad vibration-0"></div>
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
      <p class="question-subtitle">다이얼을 좌측으로 돌리면 자연, 우측으로 돌리면 도시 소리가 납니다. 다이얼을 돌려 표현해보세요.</p>
    </div>

    <div class="dial-area">
      <div class="emoji-display" id="q3-emoji">🏞️</div>
      <img src="https://i.imgur.com/OS1T7IS.png" alt="Q3 다이얼 이미지" class="dial-background q3-draggable-dial" id="q3-dial">
      <div id="q3-touch-pad" class="touch-pad level-0" style="background-image: url('https://i.imgur.com/RouU2oD.png');"></div>
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
    let selectedWeather = null;
    let q2DialRotation = 0;
    let q2DialStep = 0;
    let q3EnvironmentStep = 1; // 0: 자연, 1: 중립, 2: 도시
    let q3DialRotation = 0; // Q3 다이얼 회전 각도

    // 온도 단계
    const temperatureLevels = [36.5, 41.5, 46.5, 51.5];

    // 결과 이미지들
    const resultImages = [
      'https://i.imgur.com/uwJHQSt.png',
      'https://i.imgur.com/rYmbPsr.png', 
      'https://i.imgur.com/KI2WR6a.png'
    ];

    // 오디오 요소들
    let natureAudio, cityAudio;

    // 오디오 초기화
    function initAudio() {
      if (!natureAudio) {
        const audioContext = new (window.AudioContext || window.webkitAudioContext)();
        
        const createNatureSound = () => {
          const oscillator = audioContext.createOscillator();
          const gainNode = audioContext.createGain();
          
          oscillator.connect(gainNode);
          gainNode.connect(audioContext.destination);
          
          oscillator.frequency.setValueAtTime(800, audioContext.currentTime);
          oscillator.frequency.exponentialRampToValueAtTime(1200, audioContext.currentTime + 0.1);
          oscillator.frequency.exponentialRampToValueAtTime(600, audioContext.currentTime + 0.3);
          
          gainNode.gain.setValueAtTime(0, audioContext.currentTime);
          gainNode.gain.linearRampToValueAtTime(0.1, audioContext.currentTime + 0.05);
          gainNode.gain.exponentialRampToValueAtTime(0.001, audioContext.currentTime + 0.3);
          
          oscillator.start(audioContext.currentTime);
          oscillator.stop(audioContext.currentTime + 0.3);
        };

        const createCitySound = () => {
          const oscillator = audioContext.createOscillator();
          const gainNode = audioContext.createGain();
          
          oscillator.connect(gainNode);
          gainNode.connect(audioContext.destination);
          
          oscillator.frequency.setValueAtTime(400, audioContext.currentTime);
          oscillator.frequency.setValueAtTime(300, audioContext.currentTime + 0.1);
          
          gainNode.gain.setValueAtTime(0, audioContext.currentTime);
          gainNode.gain.linearRampToValueAtTime(0.2, audioContext.currentTime + 0.05);
          gainNode.gain.linearRampToValueAtTime(0.2, audioContext.currentTime + 0.15);
          gainNode.gain.exponentialRampToValueAtTime(0.001, audioContext.currentTime + 0.4);
          
          oscillator.start(audioContext.currentTime);
          oscillator.stop(audioContext.currentTime + 0.4);
        };

        natureAudio = { play: createNatureSound };
        cityAudio = { play: createCitySound };
      }
    }

    // DOM 요소들
    const nameInput = document.getElementById('name-input');
    const startBtn = document.getElementById('start-btn');
    const touchPad = document.getElementById('touch-pad');
    const temperatureDisplay = document.getElementById('temperature-display');
    const q1NextBtn = document.getElementById('q1-next-btn');

    // Q2 요소들
    const q2DraggableDial = document.getElementById('q2-draggable-dial');
    const q2TouchPad = document.getElementById('q2-touch-pad');
    const waveformPath = document.getElementById('waveform-path');

    // Q3 요소들
    const q3TouchPad = document.getElementById('q3-touch-pad');
    const q3Emoji = document.getElementById('q3-emoji');
    const q3Dial = document.getElementById('q3-dial');

    // 완전 초기화 함수
    function resetAll() {
      answers = {};
      touchLevel = 0;
      selectedWeather = null;
      q2DialRotation = 0;
      q2DialStep = 0;
      q3EnvironmentStep = 1;
      q3DialRotation = 0;
      
      nameInput.value = '';
      startBtn.classList.add('disabled');
      
      document.querySelectorAll('.btn').forEach(btn => {
        btn.classList.remove('selected', 'disabled');
      });
      
      // Q1 초기화
      touchPad.className = 'touch-pad level-0';
      temperatureDisplay.textContent = '36.5°C';
      q1NextBtn.classList.add('disabled');
      
      // Q2 초기화
      document.querySelectorAll('.weather-btn').forEach(btn => {
        btn.classList.remove('selected');
      });
      q2DraggableDial.className = 'q2-draggable-dial vibration-0';
      q2DraggableDial.style.setProperty('--rotation', '0deg');
      q2TouchPad.className = 'q2-touch-pad vibration-0';
      waveformPath.className = 'waveform-path level-0';
      waveformPath.setAttribute('d', 'M 10 15 L 150 15');
      document.getElementById('q2-next-btn').classList.add('disabled');
      
      // Q3 초기화
      q3TouchPad.className = 'touch-pad level-0';
      q3Emoji.textContent = '🏞️';
      q3Dial.style.transform = 'rotate(0deg)'; // 다이얼 회전 초기화
      document.getElementById('q3-next-btn').classList.add('disabled');
      
      // Q4 초기화
      document.getElementById('emotion-dial').value = 25;
      document.getElementById('emotion-temperature-display').textContent = '25°C';
    }

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
    }

    // BACK 버튼 이벤트 리스너들
    document.getElementById('q1-back-btn').addEventListener('click', function() {
      resetAll();
      showPage('start');
    });

    document.getElementById('q2-back-btn').addEventListener('click', function() {
      resetAll();
      showPage('start');
    });

    document.getElementById('q3-back-btn').addEventListener('click', function() {
      resetAll();
      showPage('start');
    });

    document.getElementById('q4-back-btn').addEventListener('click', function() {
      resetAll();
      showPage('start');
    });

    // START 페이지 로직
    nameInput.addEventListener('input', function() {
      const isValid = this.value.trim().length > 0;
      startBtn.classList.toggle('disabled', !isValid);
    });

    startBtn.addEventListener('click', handleStart);

    function handleStart() {
      if (startBtn.classList.contains('disabled')) return;
      
      answers.userName = nameInput.value.trim();
      initAudio();
      showPage('q1');
    }

    // Q1 페이지 로직
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
    });

    q1NextBtn.addEventListener('click', function() {
      if (this.classList.contains('disabled')) return;
      showPage('q2');
    });

    // Q2 페이지 로직
    const weatherButtons = [
      document.getElementById('weather-clear-btn'),
      document.getElementById('weather-rain-btn'),
      document.getElementById('weather-snow-btn'),
      document.getElementById('weather-wind-btn')
    ];
    const q2NextBtn = document.getElementById('q2-next-btn');

    let isQ2Dragging = false;
    let q2LastAngle = 0;

    function getQ2Angle(clientX, clientY) {
      const rect = q2DraggableDial.getBoundingClientRect();
      const centerX = rect.left + rect.width / 2;
      const centerY = rect.top + rect.height / 2;
      return Math.atan2(clientY - centerY, clientX - centerX) * (180 / Math.PI);
    }

    function normalizeQ2AngleDiff(angle) {
      while (angle > 180) angle -= 360;
      while (angle < -180) angle += 360;
      return angle;
    }

    function updateQ2Vibration() {
      q2DraggableDial.className = `q2-draggable-dial vibration-${q2DialStep}`;
      q2TouchPad.className = `q2-touch-pad vibration-${q2DialStep}`;
      waveformPath.className = `waveform-path level-${q2DialStep}`;
      
      // 더 자연스러운 파형들
      const waveforms = [
        'M 10 15 L 150 15',
        'M 10 15 L 40 15 Q 60 12 80 15 L 120 15 Q 140 12 150 15',
        'M 10 15 L 30 15 Q 45 8 60 15 Q 75 22 90 15 Q 105 8 120 15 Q 135 22 150 15',
        'M 10 15 Q 20 8 30 15 Q 40 22 50 15 Q 60 8 70 15 Q 80 22 90 15 Q 100 8 110 15 Q 120 22 130 15 Q 140 8 150 15'
      ];
      
      waveformPath.setAttribute('d', waveforms[q2DialStep]);
      
      const stepAngles = [0, 90, 180, 270];
      const targetAngle = stepAngles[q2DialStep];
      q2DraggableDial.style.setProperty('--rotation', `${targetAngle}deg`);
      
      if (selectedWeather && q2DialStep > 0) {
        answers.weather = {
          type: selectedWeather,
          intensity: q2DialStep
        };
        q2NextBtn.classList.remove('disabled');
      } else {
        q2NextBtn.classList.add('disabled');
      }
    }

    function startQ2Drag(e) {
      if (!selectedWeather) return;
      
      isQ2Dragging = true;
      const clientX = e.touches ? e.touches[0].clientX : e.clientX;
      const clientY = e.touches ? e.touches[0].clientY : e.clientY;
      q2LastAngle = getQ2Angle(clientX, clientY);
      
      q2DraggableDial.classList.add('no-transition');
      e.preventDefault();
    }

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
        updateQ2Vibration();
      } else {
        q2DraggableDial.style.setProperty('--rotation', `${q2DialRotation}deg`);
      }
      
      q2LastAngle = currentAngle;
      e.preventDefault();
    }

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
      updateQ2Vibration();
    }

    q2NextBtn.addEventListener('click', function() {
      if (this.classList.contains('disabled')) return;
      showPage('q3');
    });

    // Q3 페이지 로직 - 다이얼 회전 기능 추가
    let isQ3Dragging = false;
    let q3LastAngle = 0;

    function getQ3Angle(clientX, clientY) {
      const rect = q3Dial.getBoundingClientRect();
      const centerX = rect.left + rect.width / 2;
      const centerY = rect.top + rect.height / 2;
      return Math.atan2(clientY - centerY, clientX - centerX) * (180 / Math.PI);
    }

    function normalizeQ3AngleDiff(angle) {
      while (angle > 180) angle -= 360;
      while (angle < -180) angle += 360;
      return angle;
    }

    function updateQ3Environment(step) {
      q3EnvironmentStep = step;
      
      // 다이얼 회전 각도 설정
      const rotationAngles = [-45, 0, 45]; // 좌측(-45°), 중앙(0°), 우측(45°)
      q3DialRotation = rotationAngles[step];
      q3Dial.style.transform = `rotate(${q3DialRotation}deg)`;
      
      if (step === 0) {
        // 자연 (좌측)
        q3Emoji.textContent = '⛰️';
        if (natureAudio) {
          natureAudio.play();
        }
        answers.environment = 'nature';
        document.getElementById('q3-next-btn').classList.remove('disabled');
      } else if (step === 2) {
        // 도시 (우측)
        q3Emoji.textContent = '🏙️';
        if (cityAudio) {
          cityAudio.play();
        }
        answers.environment = 'city';
        document.getElementById('q3-next-btn').classList.remove('disabled');
      } else {
        // 중립 (중앙)
        q3Emoji.textContent = '🏞️';
        document.getElementById('q3-next-btn').classList.add('disabled');
      }
    }

    // Q3 다이얼 드래그 - 회전 각도 기반
    function startQ3Drag(e) {
      isQ3Dragging = true;
      const clientX = e.touches ? e.touches[0].clientX : e.clientX;
      const clientY = e.touches ? e.touches[0].clientY : e.clientY;
      q3LastAngle = getQ3Angle(clientX, clientY);
      e.preventDefault();
    }

    function moveQ3Drag(e) {
      if (!isQ3Dragging) return;
      
      const clientX = e.touches ? e.touches[0].clientX : e.clientX;
      const clientY = e.touches ? e.touches[0].clientY : e.clientY;
      const currentAngle = getQ3Angle(clientX, clientY);
      
      const angleDiff = normalizeQ3AngleDiff(currentAngle - q3LastAngle);
      
      q3DialRotation += angleDiff;
      q3DialRotation = Math.max(-45, Math.min(45, q3DialRotation)); // -45도에서 45도 사이
      
      // 실시간 다이얼 회전
      q3Dial.style.transform = `rotate(${q3DialRotation}deg)`;
      
      // 단계 결정 (-45~-15: 자연, -15~15: 중립, 15~45: 도시)
      let newStep;
      if (q3DialRotation <= -15) {
        newStep = 0; // 자연
      } else if (q3DialRotation >= 15) {
        newStep = 2; // 도시
      } else {
        newStep = 1; // 중립
      }
      
      if (newStep !== q3EnvironmentStep) {
        updateQ3Environment(newStep);
      }
      
      q3LastAngle = currentAngle;
      e.preventDefault();
    }

    function endQ3Drag() {
      if (!isQ3Dragging) return;
      isQ3Dragging = false;
      
      // 스냅 효과: 가장 가까운 단계로 맞춤
      const snapAngles = [-45, 0, 45];
      let closestIndex = 0;
      let minDistance = Math.abs(q3DialRotation - snapAngles[0]);
      
      for (let i = 1; i < snapAngles.length; i++) {
        const distance = Math.abs(q3DialRotation - snapAngles[i]);
        if (distance < minDistance) {
          minDistance = distance;
          closestIndex = i;
        }
      }
      
      q3DialRotation = snapAngles[closestIndex];
      q3Dial.style.transform = `rotate(${q3DialRotation}deg)`;
      updateQ3Environment(closestIndex);
    }

    // Q3 다이얼 이벤트 리스너
    q3Dial.addEventListener('mousedown', startQ3Drag);
    document.addEventListener('mousemove', moveQ3Drag);
    document.addEventListener('mouseup', endQ3Drag);

    q3Dial.addEventListener('touchstart', startQ3Drag, { passive: false });
    document.addEventListener('touchmove', moveQ3Drag, { passive: false });
    document.addEventListener('touchend', endQ3Drag);

    // 초기 Q3 상태 설정
    updateQ3Environment(1); // 중립 상태로 시작

    document.getElementById('q3-next-btn').addEventListener('click', function() {
      if (this.classList.contains('disabled')) return;
      showPage('q4');
    });

    // Q4 페이지 로직
    const emotionDial = document.getElementById('emotion-dial');
    const emotionTempDisplay = document.getElementById('emotion-temperature-display');
    const q4FinishBtn = document.getElementById('q4-finish-btn');

    emotionDial.addEventListener('input', function() {
      const temp = this.value;
      emotionTempDisplay.textContent = temp + '°C';
      answers.emotion = parseInt(temp);
    });

    q4FinishBtn.addEventListener('click', function() {
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

    // HOME 버튼
    document.getElementById('result-home-btn').addEventListener('click', function() {
      resetAll();
      showPage('start');
    });

    // 터치 지원
    touchPad.addEventListener('touchstart', function(e) {
      e.preventDefault();
      this.click();
    });

    // 초기화
    updateQ2Vibration();
    console.log('향기 추억 제작소가 시작되었습니다!');
  </script>
</body>
</html>
