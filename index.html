<!DOCTYPE html>
<html lang="ko">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0, user-scalable=no" />
  <meta name="apple-mobile-web-app-capable" content="yes" />
  <title>향기 추억 제작소</title>
  <style>
    @import url('https://fonts.googleapis.com/css2?family=Pretendard:wght@300;400;500;600;700;800&display=swap');

    * { -webkit-tap-highlight-color: transparent; user-select: none; box-sizing: border-box; }
    body { margin: 0; padding: 0; font-family: 'Pretendard', -apple-system, BlinkMacSystemFont, system_ui, sans-serif; background: #fff; color: #333; overflow-x: hidden; }

    .page { min-height: 100vh; position: relative; overflow: hidden; background: #fff; }
    .page.hidden { display: none; }
    .fade-in { animation: fadeIn .6s ease-out; }
    @keyframes fadeIn { from { opacity: 0; transform: translateY(8px); } to { opacity: 1; transform: translateY(0); } }

    .btn-back { position: fixed; top: 20px; left: 20px; z-index: 9999; background: #fff; color: #666; font-size: 12px; padding: 6px 12px; font-weight: 600; box-shadow: 0 2px 8px rgba(0,0,0,.2); border-radius: 15px; border: 0; cursor: pointer; text-transform: uppercase; }

    .q-badge { position: absolute; top: 14px; right: 14px; z-index: 1000; font-size: 11px; color: #888; background: rgba(255,255,255,.9); padding: 4px 8px; border-radius: 10px; box-shadow: 0 1px 4px rgba(0,0,0,.08); pointer-events: none; }

    .question-area { position: absolute; top: 60px; left: 50%; transform: translateX(-50%); width: 90%; max-width: 380px; text-align: center; z-index: 10; }
    .question-title  { font-size: 20px; font-weight: 700; color: #222; line-height: 1.3; margin: 0; }
    .question-subtitle { font-size: 13px; color: #666; line-height: 1.35; margin: 10px 0 0 0; }

    .dial-area { position: absolute; top: 50%; left: 50%; transform: translate(-50%, -50%); width: 350px; height: 350px; display: flex; align-items: center; justify-content: center; z-index: 10; }
    .dial-background { position: absolute; width: 350px; height: 350px; z-index: 1; pointer-events: none; transition: transform .2s ease; }

    .button-area { position: absolute; bottom: 50px; left: 50%; transform: translateX(-50%); z-index: 10; }
    .btn-next { background: #000; color: #fff; font-weight: 700; font-size: 14px; padding: 8px 20px; border-radius: 18px; border: 0; cursor: pointer; text-transform: uppercase; min-width: 80px; box-shadow: 0 3px 10px rgba(0,0,0,.3); }
    .btn-next.disabled { background: #555; color: #aaa; cursor: not-allowed; box-shadow: none; }

    .start-page { display: flex; min-height: 100vh; align-items: center; justify-content: center; }
    .start-container { width: 100%; max-width: 460px; text-align: center; transform: translateY(24px); }
    .start-title { font-size: 28px; font-weight: 700; margin: 0 0 24px; line-height: 1.35; color: #333; }

    .input-wrap { margin: 28px 0 48px; }
    .input-inner { position: relative; width: 300px; margin: 0 auto; }
    .name-input { width: 100%; padding: 15px 5px; font-size: 18px; text-align: center; border: 0; outline: 0; background: transparent; }
    .input-line { position: absolute; left: 0; right: 0; bottom: 0; height: 2px; background: #ddd; }

    /* INFO — 선택 시 푸른빛 */
    .info-page .info-center { position: absolute; top: 44%; left: 50%; transform: translate(-50%, -50%); width: 90%; max-width: 420px; text-align: center; }
    .month-grid { display: grid; grid-template-columns: repeat(6, 1fr); gap: 8px; justify-items: center; margin: 8px 0 40px; }
    .month-btn { width: 52px; height: 36px; border-radius: 10px; border: 0; cursor: pointer; font-weight: 600; font-size: 14px; background: #fff; color: #555; box-shadow: 0 2px 8px rgba(0,0,0,.08); transition: background .2s ease, color .2s ease, box-shadow .2s ease; }
    .month-btn.selected { background: rgba(111,121,255,.16); color: #3F51B5; box-shadow: 0 2px 10px rgba(90,103,216,.22); }

    .city-input-wrap { position: relative; width: 320px; max-width: 90%; margin: 18px auto 0; }
    .city-input { width: 100%; padding: 12px 10px; font-size: 16px; border: 0; outline: 0; text-align: center; background: transparent; }
    .city-line { position: absolute; left: 0; right: 0; bottom: 0; height: 2px; background: #ddd; }

    /* Q1 균일 링 퍼짐 */
    .touch-pad { position: absolute; width: 300px; height: 300px; border-radius: 50%; display: flex; align-items: center; justify-content: center; z-index: 2; background: url('https://i.imgur.com/FTZhg6Z.png') center/cover no-repeat; overflow: hidden; }
    .touch-pad .ring { position: absolute; inset: 0; border-radius: 50%; pointer-events: none; opacity: 0; }
    .touch-pad .ring.blue  { background: radial-gradient(circle, rgba(110,145,255,.20) 0%, rgba(110,145,255,.08) 60%, rgba(110,145,255,0) 75%); }
    .touch-pad .ring.orange{ background: radial-gradient(circle, rgba(255,160,75,.22) 0%, rgba(255,160,75,.10) 60%, rgba(255,160,75,0) 75%); }
    @keyframes ringSpread { 0% { transform: scale(.2); opacity: 0; filter: blur(8px);} 10%{opacity:.5;} 60%{opacity:.85;} 100%{ transform: scale(1.0); opacity:.95; filter:blur(10px);} }
    .state-label { position: absolute; top: -46px; left: 50%; transform: translateX(-50%); font-size: 14px; font-weight: 700; color: #222; letter-spacing: .5px; text-transform: uppercase; background: rgba(255,255,255,.75); padding: 4px 10px; border-radius: 12px; box-shadow: 0 2px 8px rgba(0,0,0,.08); pointer-events: none; }

    /* Q2 */
    .weather-area { position: absolute; top: 150px; left: 50%; transform: translateX(-50%); z-index: 10; width: 100%; max-width: 320px; }
    .weather-buttons { display: flex; justify-content: center; gap: 8px; margin-bottom: 30px; flex-wrap: wrap; }
    .weather-btn { padding: 10px 18px; font-size: 15px; border: 0; border-radius: 25px; background: #fff; color: #666; cursor: pointer; box-shadow: 0 2px 8px rgba(0,0,0,.1); min-width: 65px; position: relative; transition: background .2s ease, color .2s ease, box-shadow .2s ease; }
    .weather-btn::after { content: ''; position: absolute; top: -4px; right: 6px; width: 8px; height: 8px; background: #5A67D8; border-radius: 50%; display: none; }
    .weather-btn.selected { background: rgba(111,121,255,.14); color: #3F51B5; box-shadow: 0 2px 10px rgba(90,103,216,.20); }
    .weather-btn.selected::after { display: block; }

    .q2-draggable-dial { position: absolute; width: 350px; height: 350px; transform-origin: center; z-index: 2; transform: rotate(var(--rotation, 0deg)); transition: transform .18s ease; will-change: transform; }
    .q2-touch-pad { position: absolute; width: 300px; height: 300px; border-radius: 50%; z-index: 3; background: url('https://i.imgur.com/FTZhg6Z.png') center/cover no-repeat; pointer-events: none; }

    .waveform-container { position: absolute; top: -50px; left: 50%; transform: translateX(-50%); z-index: 4; width: 160px; height: 30px; }
    .waveform-svg { width: 100%; height: 100%; }
    .waveform-path { stroke: #666; stroke-width: 2; fill: none; }
    @keyframes waveFlow { 0%{stroke-dasharray:40 200;stroke-dashoffset:0;}50%{stroke-dasharray:100 140;stroke-dashoffset:-60;}100%{stroke-dasharray:40 200;stroke-dashoffset:-200;} }
    .wave-anim-1 { animation: waveFlow 1.8s linear infinite; stroke: #6F79FF; }
    .wave-anim-2 { animation: waveFlow 1.4s linear infinite; stroke: #5A67D8; }
    .wave-anim-3 { animation: waveFlow 1.1s linear infinite; stroke: #3F51B5; }

    .step-tick { animation: dialTick 120ms cubic-bezier(.2, .8, .2, 1); }
    @keyframes dialTick { 0% { transform: scale(1); } 60% { transform: scale(1.02); } 100% { transform: scale(1); } }

    .q3-icon { position: absolute; top: -45px; left: 50%; transform: translateX(-50%); width: 56px; height: 36px; z-index: 5; }
    .q3-icon svg { width: 56px; height: 36px; }
    .q3-hide { display: none; }

    /* LOADING — 컨테이너 유지(72px), 사진만 올림(top: 36px) */
    .loading-page { display: flex; align-items: center; justify-content: center; }
    .loading-wrap { width: 100%; max-width: 420px; margin-top: 24px; text-align: center; }
    .loading-title { font-size: 16px; font-weight: 600; color: #333; margin-bottom: 12px; }
    .loading-visual { position: relative; width: 180px; height: 260px; margin: 72px auto 0; }
    .device-img { width: 160px; position: absolute; left: 50%; transform: translateX(-50%); top: 36px; z-index: 2; border-radius: 6px; }
    .window-clip { position: absolute; left: 50%; transform: translateX(-50%); bottom: 26px; width: 76px; height: 110px; border-radius: 10px; overflow: hidden; z-index: 3; box-shadow: inset 0 0 0 1px rgba(255,255,255,.08); }
    .liquid { position: absolute; bottom: 0; left: 29%; width: 42%; height: 0%; background: #A4A9FF; border-radius: 4px; animation: slosh 1.8s ease-in-out infinite alternate; }
    @keyframes slosh { from { left: 27.5%; } to { left: 30.5%; } }
    .liquid-top { position: absolute; left: -40%; width: 180%; height: 16px; bottom: 0; background: radial-gradient(40px 10px at 50% 50%, rgba(255,255,255,.35) 0%, rgba(255,255,255,0) 60%) repeat-x; background-size: 80px 16px; opacity: .7; animation: topWave 1.2s ease-in-out infinite alternate; }
    @keyframes topWave { from { transform: translateX(-8px); } to { transform: translateX(8px); } }

    /* RESULT — 질문과 동일 타이포 */
    .result-wrap { display: flex; flex-direction: column; align-items: center; justify-content: center; height: 100vh; gap: 28px; }
    .result-title { font-size: 20px; font-weight: 700; color: #222; text-align: center; line-height: 1.3; }
    .result-image { max-width: 360px; max-height: 360px; border-radius: 14px; }

    /* Q4 */
    .q4-dial-area { position: absolute; top: 50%; left: 50%; transform: translate(-50%, -50%); width: 320px; height: 320px; display:flex; align-items:center; justify-content:center; }
    .q4-dial-img { position: absolute; width: 320px; height: 320px; transform-origin: center; will-change: transform; }
    .q4-touch { position: absolute; width: 284px; height: 284px; border-radius: 50%; pointer-events: none; background-size: cover; background-position: center; }
    .q4-state-img { position: absolute; top: -86px; left: 50%; transform: translateX(-50%); width: 52px; height: auto; pointer-events: none; z-index: 6; } /* 위로 올리고 사이즈 축소 */

    .q4-step-kick { animation: q4Kick .09s cubic-bezier(.2,.8,.2,1); }
    @keyframes q4Kick { 0%{ transform: scale(1); } 60%{ transform: scale(1.008); } 100%{ transform: scale(1); } }

    @media (max-width: 768px) {
      .start-title { font-size: 24px; }
      .question-title { font-size: 18px; }
      .dial-area { width: 300px; height: 300px; }
      .dial-background, .q2-draggable-dial { width: 300px; height: 300px; }
      .touch-pad, .q2-touch-pad { width: 260px; height: 260px; }
      .waveform-container { width: 130px; top: -42px; }
    }
  </style>
</head>
<body>
  <!-- START -->
  <div id="start-page" class="page start-page fade-in">
    <div class="start-container">
      <h1 class="start-title">당신만의 지구 추억의<br>향과 향수병을 제작해보세요.</h1>
      <div class="input-wrap">
        <div class="input-inner">
          <input id="name-input" class="name-input" type="text" placeholder="이름을 입력해주세요" />
          <div class="input-line"></div>
        </div>
      </div>
      <button id="start-btn" class="btn-next disabled">START</button>
    </div>
  </div>

  <!-- INFO -->
  <div id="info-page" class="page info-page hidden">
    <button id="info-back-btn" class="btn-back">BACK</button>
    <div class="info-center">
      <h2 class="question-title" style="margin:0 0 6px;">추억의 때는 몇월이었나요?</h2>
      <div class="month-grid" id="month-grid">
        <button class="month-btn">1월</button><button class="month-btn">2월</button><button class="month-btn">3월</button><button class="month-btn">4월</button><button class="month-btn">5월</button><button class="month-btn">6월</button>
        <button class="month-btn">7월</button><button class="month-btn">8월</button><button class="month-btn">9월</button><button class="month-btn">10월</button><button class="month-btn">11월</button><button class="month-btn">12월</button>
      </div>
      <h2 class="question-title" style="margin:42px 0 8px;">추억의 도시는 어느곳인가요?</h2>
      <div class="city-input-wrap">
        <input id="city-input" class="city-input" type="text" placeholder="예: 수원, 서울, 부산 ..." />
        <div class="city-line"></div>
      </div>
    </div>
    <div class="button-area">
      <button id="info-next-btn" class="btn-next disabled">NEXT</button>
    </div>
  </div>

  <!-- Q1 -->
  <div id="q1-page" class="page q1-page hidden">
    <div class="q-badge">*총 네개의 질문으로 구성되어있습니다.</div>
    <button id="q1-back-btn" class="btn-back">BACK</button>
    <div class="question-area">
      <h2 class="question-title">Q1. 그 때의 주변의 온도는 어땠나요?</h2>
      <p class="question-subtitle">가운데 패드를 터치해 느낌을 표현해보세요.</p>
    </div>
    <div class="dial-area">
      <img src="https://i.imgur.com/okVDs9K.png" alt="다이얼" class="dial-background">
      <div id="q1-state-label" class="state-label">normal</div>
      <div id="q1-touch-pad" class="touch-pad">
        <div id="q1-ring1" class="ring"></div>
        <div id="q1-ring2" class="ring"></div>
      </div>
    </div>
    <div class="button-area">
      <button id="q1-next-btn" class="btn-next">NEXT</button>
    </div>
  </div>

  <!-- Q2 -->
  <div id="q2-page" class="page q2-page hidden">
    <div class="q-badge">*총 네개의 질문으로 구성되어있습니다.</div>
    <button id="q2-back-btn" class="btn-back">BACK</button>
    <div class="question-area">
      <h2 class="question-title">Q2. 그 날의 날씨는 어땠나요? 날씨를 클릭하고 다이얼을 돌려 강도를 표현해주세요.</h2>
      <p class="question-subtitle">선택 시 버튼 우상단에 점이 표시됩니다.</p>
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
          <path id="waveform-path" class="waveform-path" d="M 10 15 L 150 15" />
        </svg>
      </div>
      <img id="q2-draggable-dial" src="https://i.imgur.com/okVDs9K.png" alt="다이얼" class="q2-draggable-dial">
      <div id="q2-touch-pad" class="q2-touch-pad vib-0"></div>
    </div>
    <div class="button-area">
      <button id="q2-next-btn" class="btn-next disabled">NEXT</button>
    </div>
  </div>

  <!-- Q3 -->
  <div id="q3-page" class="page q3-page hidden">
    <div class="q-badge">*총 네개의 질문으로 구성되어있습니다.</div>
    <button id="q3-back-btn" class="btn-back">BACK</button>
    <div class="question-area">
      <h2 class="question-title">Q3. 그 때의 주변 환경은 자연과 도시중 어느곳에 가까웠나요?</h2>
      <p class="question-subtitle">다이얼을 좌측으로 돌리면 자연,<br>우측으로 돌리면 도시 소리가 납니다.</p>
    </div>
    <div class="dial-area">
      <div class="q3-icon">
        <svg viewBox="0 0 56 36" xmlns="http://www.w3.org/2000/svg">
          <g id="icon-leaf" fill="#38A169" opacity="0.95">
            <path d="M8,26 C8,18 14,10 24,8 C34,6 46,10 48,12 C40,14 30,16 24,22 C20,26 18,30 18,32 C14,32 10,30 8,26 Z" />
            <path d="M18,32 C20,26 28,19 40,16" stroke="#2F855A" stroke-width="2" fill="none" stroke-linecap="round"/>
          </g>
          <g id="icon-city" class="q3-hide">
            <rect x="16" y="10" width="10" height="20" fill="#B0B3BA" rx="1"/>
            <rect x="30" y="6" width="12" height="24" fill="#9AA0A6" rx="1"/>
          </g>
        </svg>
      </div>
      <img id="q3-dial" src="https://i.imgur.com/OS1T7IS.png" alt="다이얼" class="dial-background" style="pointer-events:auto; cursor:grab;">
      <div id="q3-touch-pad" class="touch-pad" style="background-image:url('https://i.imgur.com/RouU2oD.png');"></div>
    </div>
    <div class="button-area">
      <button id="q3-next-btn" class="btn-next disabled">NEXT</button>
    </div>
  </div>

  <!-- Q4 -->
  <div id="q4-page" class="page q4-page hidden">
    <div class="q-badge">*총 네개의 질문으로 구성되어있습니다.</div>
    <button id="q4-back-btn" class="btn-back">BACK</button>
    <div class="question-area">
      <h2 class="question-title">Q4. 그 때 내 마음은 어땠나요?</h2>
      <p class="question-subtitle">다이얼을 돌려 마음의 상태를 표현해보세요.</p>
    </div>
    <div class="q4-dial-area">
      <img id="q4-state-img" class="q4-state-img" src="https://i.imgur.com/cdMEbIV.png" alt="상태 이미지">
      <img id="q4-dial-img" class="q4-dial-img" alt="감정 다이얼" src="https://i.imgur.com/5AyUHoa.png">
      <div id="q4-touch" class="q4-touch" style="background-image:url('https://i.imgur.com/NhNfjTk.png');"></div>
    </div>
    <div class="button-area">
      <button id="q4-finish-btn" class="btn-next">FINISH</button>
    </div>
  </div>

  <!-- LOADING -->
  <div id="loading-page" class="page loading-page hidden">
    <div class="loading-wrap">
      <div class="loading-title">향기 만드는 중...</div>
      <div class="loading-visual">
        <img class="device-img" src="https://i.imgur.com/yWhabuk.png" alt="장치 이미지">
        <div class="window-clip" id="windowClip">
          <div class="liquid" id="liquid">
            <div class="liquid-top" id="liquidTop"></div>
          </div>
        </div>
      </div>
    </div>
  </div>

  <!-- RESULT -->
  <div id="result-page" class="page result-page hidden">
    <div class="result-wrap">
      <div class="result-title" id="result-message">님의 추억의 향기가 완성 되었습니다.</div>
      <img id="result-image" class="result-image" src="https://i.imgur.com/uwJHQSt.png" alt="완성된 향기 이미지" />
      <button id="result-home-btn" class="btn-next" style="background:#9EA4FF;">HOME</button>
    </div>
  </div>

  <!-- 오디오 -->
  <audio id="aud-nature" src="assets/nature.mp3" preload="auto" loop autoplay muted></audio>
  <audio id="aud-crowd"  src="assets/crowd.mp3"  preload="auto" loop autoplay muted></audio>
  <audio id="aud-horn"   src="assets/car_horn.mp3" preload="auto"></audio>

  <script>
    // ===== 상태/요소
    let answers = {};
    let selectedWeather = null; let q2DialRotation=0, q2DialStep=0;
    let q3Step = 1; let infoMonth = null;

    const startBtn=document.getElementById('start-btn'); const nameInput=document.getElementById('name-input');
    const infoBack=document.getElementById('info-back-btn'); const infoNext=document.getElementById('info-next-btn');
    const monthGrid=document.getElementById('month-grid'); const cityInput=document.getElementById('city-input');

    const q1Pad=document.getElementById('q1-touch-pad'); const q1Next=document.getElementById('q1-next-btn'); const q1Label=document.getElementById('q1-state-label');
    const ring1=document.getElementById('q1-ring1'); const ring2=document.getElementById('q1-ring2');

    const q2Dial=document.getElementById('q2-draggable-dial'); const q2Pad=document.getElementById('q2-touch-pad'); const wave=document.getElementById('waveform-path'); const q2Next=document.getElementById('q2-next-btn');

    const q3Dial=document.getElementById('q3-dial'); const q3Next=document.getElementById('q3-next-btn'); const iconLeaf=document.getElementById('icon-leaf'); const iconCity=document.getElementById('icon-city');

    const q4DialImg=document.getElementById('q4-dial-img'); const q4StateImg=document.getElementById('q4-state-img');

    const windowClip=document.getElementById('windowClip'); const liquid=document.getElementById('liquid');

    const audNature=document.getElementById('aud-nature'); const audCrowd=document.getElementById('aud-crowd'); const audHorn=document.getElementById('aud-horn');

    function tryPlayMuted(){ try{ audNature.muted=true; audCrowd.muted=true; audNature.play().catch(()=>{}); audCrowd.play().catch(()=>{});}catch(e){} }
    window.addEventListener('load', tryPlayMuted, {once:true}); document.addEventListener('pointerdown', tryPlayMuted, {once:true});

    function show(id){
      document.querySelectorAll('.page').forEach(p=>p.classList.add('hidden'));
      const page=document.getElementById(id+'-page'); page.classList.remove('hidden'); page.classList.add('fade-in');
      if(id==='loading') startPrinting(); else stopPrinting();
      if(id==='q3'){ q3TargetRotation=0; q3CurrentRotation=0; q3DragAccum=0; q3Dragging=false; try{ audNature.muted=false; audCrowd.muted=false; audNature.play().catch(()=>{}); audCrowd.play().catch(()=>{});}catch(e){} }
    }

    function resetAll(){
      nameInput.value=''; startBtn.classList.add('disabled');
      infoMonth=null; cityInput.value=''; infoNext.classList.add('disabled'); monthGrid.querySelectorAll('.month-btn').forEach(b=>b.classList.remove('selected'));

      q1Label.textContent='normal'; q1Next.classList.remove('disabled');

      selectedWeather=null; document.querySelectorAll('.weather-btn').forEach(b=>b.classList.remove('selected'));
      q2DialRotation=0; q2DialStep=0; q2Dial.style.setProperty('--rotation','0deg'); q2Pad.className='q2-touch-pad vib-0';
      wave.setAttribute('d','M 10 15 L 150 15'); wave.classList.remove('wave-anim-1','wave-anim-2','wave-anim-3'); q2Next.classList.add('disabled');

      q3Dial.style.transform='rotate(0deg)'; iconLeaf.classList.remove('q3-hide'); iconCity.classList.add('q3-hide'); q3Step=1;

      q4State={ target:0, current:0, dragging:false, lastA:0, lastStep:0, lastImgKey:'0' };
      q4DialImg.style.transform='rotate(0deg)';
      q4StateImg.src='https://i.imgur.com/cdMEbIV.png';
    }

    // START
    nameInput.addEventListener('input', ()=> startBtn.classList.toggle('disabled', nameInput.value.trim().length===0));
    startBtn.addEventListener('click', ()=>{ if(startBtn.classList.contains('disabled')) return; answers.userName=nameInput.value.trim(); show('info'); });

    // INFO
    infoBack.addEventListener('click', ()=> show('start'));
    monthGrid.querySelectorAll('.month-btn').forEach((btn, idx)=> btn.addEventListener('click', ()=>{ monthGrid.querySelectorAll('.month-btn').forEach(b=>b.classList.remove('selected')); btn.classList.add('selected'); infoMonth=idx+1; validateInfo(); }));
    cityInput.addEventListener('input', validateInfo);
    function validateInfo(){ const ok=!!infoMonth && cityInput.value.trim().length>0; infoNext.classList.toggle('disabled', !ok); }
    infoNext.addEventListener('click', ()=>{ if(infoNext.classList.contains('disabled')) return; answers.month=infoMonth; answers.city=cityInput.value.trim(); show('q1'); });

    // Q1 normal ↔ cold ↔ hot
    const Q1_SOSO=0, Q1_COOL=1, Q1_WARM=2; const q1Order=[Q1_SOSO,Q1_COOL,Q1_WARM]; let q1Idx=0;
    function playRings(color){ [ring1,ring2].forEach(r=>{ r.className='ring'; r.style.animation='none'; void r.offsetWidth; r.classList.add(color?'blue':'orange'); }); ring1.style.animation='ringSpread 950ms ease-out forwards'; ring2.style.animation='ringSpread 950ms ease_out 140ms forwards'; }
    function applyQ1(state){
      if(state===Q1_COOL){ q1Label.textContent='cold'; playRings(true); }
      else if(state===Q1_WARM){ q1Label.textContent='hot'; playRings(false); }
      else { q1Label.textContent='normal'; [ring1,ring2].forEach(r=> r.style.animation='none'); }
      q1Next.classList.remove('disabled');
    }
    q1Pad.addEventListener('click', ()=>{ q1Idx=(q1Idx+1)%q1Order.length; applyQ1(q1Order[q1Idx]); });
    applyQ1(Q1_SOSO);
    document.getElementById('q1-back-btn').onclick=()=> show('info');
    q1Next.addEventListener('click', ()=> show('q2'));

    // Q2
    const weatherBtns=[ 'weather-clear-btn','weather-rain-btn','weather-snow-btn','weather-wind-btn' ].map(id=>document.getElementById(id));
    weatherBtns.forEach((btn,i)=> btn.addEventListener('click', ()=>{ weatherBtns.forEach(b=>b.classList.remove('selected')); btn.classList.add('selected'); selectedWeather=['clear','rain','snow','wind'][i]; updateQ2(); }));
    function angleAt(el, x, y){ const r=el.getBoundingClientRect(); const cx=r.left+r.width/2, cy=r.top+r.height/2; return Math.atan2(y-cy, x-cx)*180/Math.PI; }
    function norm(a){ while(a>180) a-=360; while(a<-180)a+=360; return a; }
    let dragging=false, lastA=0; const stepAngles=[0,90,180,270];
    const wavePaths=[ 'M 10 15 L 150 15','M 10 15 Q 20 8 30 15 Q 40 22 50 15 Q 60 8 70 15 Q 80 22 90 15 Q 100 8 110 15 Q 120 22 130 15 Q 140 8 150 15','M 10 15 Q 18 6 26 15 Q 34 24 42 15 Q 50 6 58 15 Q 66 24 74 15 Q 82 6 90 15 Q 98 24 106 15 Q 114 6 122 15 Q 130 24 138 15 Q 146 6 150 15','M 10 15 Q 16 4 22 15 Q 28 26 34 15 Q 40 4 46 15 Q 52 26 58 15 Q 64 4 70 15 Q 76 26 82 15 Q 88 4 94 15 Q 100 26 106 15 Q 112 4 118 15 Q 124 26 130 15 Q 136 4 142 15 Q 148 26 150 15' ];
    function setVibration(step){ q2Pad.className=`q2-touch-pad vib-${step}`; }
    function updateQ2(){ q2Dial.style.setProperty('--rotation', `${stepAngles[q2DialStep]}deg`); setVibration(q2DialStep); wave.setAttribute('d', wavePaths[q2DialStep]); wave.classList.remove('wave-anim-1','wave-anim-2','wave-anim-3'); if(q2DialStep===1) wave.classList.add('wave-anim-1'); if(q2DialStep===2) wave.classList.add('wave-anim-2'); if(q2DialStep===3) wave.classList.add('wave-anim-3'); if(selectedWeather && q2DialStep>0) q2Next.classList.remove('disabled'); else q2Next.classList.add('disabled'); }
    function startQ2Drag(e){ dragging=true; const pt=e.touches?e.touches[0]:e; lastA=angleAt(q2Dial, pt.clientX, pt.clientY); q2Dial.style.transition='none'; e.preventDefault(); }
    function moveQ2Drag(e){ if(!dragging) return; const pt=e.touches?e.touches[0]:e; const a=angleAt(q2Dial, pt.clientX, pt.clientY); const d=norm(a-lastA); q2DialRotation=Math.max(0, Math.min(270, q2DialRotation+d)); const ns=Math.round(q2DialRotation/90); if(ns!==q2DialStep){ q2DialStep=ns; updateQ2(); } else { q2Dial.style.setProperty('--rotation', `${q2DialRotation}deg`); } lastA=a; e.preventDefault(); }
    function endQ2Drag(){ if(!dragging) return; dragging=false; q2DialRotation=q2DialStep*90; q2Dial.style.transition='transform .18s ease'; q2Dial.style.setProperty('--rotation', `${stepAngles[q2DialStep]}deg`); updateQ2(); }
    q2Dial.addEventListener('mousedown', startQ2Drag); document.addEventListener('mousemove', moveQ2Drag); document.addEventListener('mouseup', endQ2Drag);
    q2Dial.addEventListener('touchstart', startQ2Drag, {passive:false}); document.addEventListener('touchmove', moveQ2Drag, {passive:false}); document.addEventListener('touchend', endQ2Drag);
    q2Next.addEventListener('click', ()=> show('q3'));

    // Q3 중앙 기본 + 첫 드래그부터 좌우 가능
    let q3Dragging=false, q3LastA=0, q3TargetRotation=0, q3CurrentRotation=0, q3DragAccum=0;
    function angleQ3(el, x, y){ const r=el.getBoundingClientRect(); const cx=r.left+r.width/2, cy=r.top+r.height/2; return Math.atan2(y-cy, x-cx)*180/Math.PI; }
    function clamp(v,min,max){ return Math.max(min, Math.min(max, v)); }
    function setQ3Step(step){ if(step===q3Step) return; q3Step=step; if(step===0){ iconLeaf.classList.remove('q3-hide'); iconCity.classList.add('q3-hide'); q3Next.classList.remove('disabled'); } else if(step===2){ iconLeaf.classList.add('q3-hide'); iconCity.classList.remove('q3-hide'); q3Next.classList.remove('disabled'); } else { iconLeaf.classList.remove('q3-hide'); iconCity.classList.add('q3-hide'); q3Next.classList.add('disabled'); } }
    const NAT_MAX=0.8, CITY_MAX=0.65, CURVE=1.6; let lastHornAt=0;
    function updateQ3Sound(){ const x=clamp(q3CurrentRotation/45,-1,1); const nat=Math.pow(Math.max(0,-x),CURVE); const city=Math.pow(Math.max(0, x),CURVE); audNature.volume=NAT_MAX*nat; audCrowd.volume=CITY_MAX*city; const now=performance.now(); if(city>0.85 && now-lastHornAt>2500){ try{ audHorn.currentTime=0; audHorn.play(); }catch(e){} lastHornAt=now; } }
    function animateQ3(){ q3CurrentRotation+=(q3TargetRotation-q3CurrentRotation)*0.15; q3Dial.style.transform=`rotate(${q3CurrentRotation}deg)`; const r=q3CurrentRotation; if(r<=-18) setQ3Step(0); else if(r>=18) setQ3Step(2); else setQ3Step(1); updateQ3Sound(); requestAnimationFrame(animateQ3); }
    requestAnimationFrame(animateQ3);
    q3Dial.addEventListener('mousedown', e=>{ q3Dragging=true; q3LastA=angleQ3(q3Dial,e.clientX,e.clientY); q3DragAccum=0; e.preventDefault(); });
    document.addEventListener('mousemove', e=>{ if(!q3Dragging) return; const a=angleQ3(q3Dial,e.clientX,e.clientY); let d=a-q3LastA; while(d>180)d-=360; while(d<-180)d+=360; q3DragAccum+=d; q3TargetRotation=clamp(q3DragAccum,-45,45); q3LastA=a; e.preventDefault(); });
    document.addEventListener('mouseup', ()=>{ if(!q3Dragging) return; q3Dragging=false; q3TargetRotation=[-45,0,45][q3Step]; });
    q3Dial.addEventListener('touchstart', e=>{ q3Dragging=true; const t=e.touches[0]; q3LastA=angleQ3(q3Dial,t.clientX,t.clientY); q3DragAccum=0; e.preventDefault(); }, {passive:false});
    document.addEventListener('touchmove', e=>{ if(!q3Dragging) return; const t=e.touches[0]; const a=angleQ3(q3Dial,t.clientX,t.clientY); let d=a-q3LastA; while(d>180)d-=360; while(d<-180)d+=360; q3DragAccum+=d; q3TargetRotation=clamp(q3DragAccum,-45,45); q3LastA=a; e.preventDefault(); }, {passive:false});
    document.addEventListener('touchend', ()=>{ if(!q3Dragging) return; q3Dragging=false; q3TargetRotation=[-45,0,45][q3Step]; });
    q3Next.addEventListener('click', ()=> show('q4'));

    // Q4: 360° + 단계별 상태 이미지
    const Q4_STEP_COUNT=7, Q4_STEP_DEG=360/Q4_STEP_COUNT;
    let q4State={ target:0, current:0, dragging:false, lastA:0, lastStep:0, lastImgKey:'0' };

    const Q4_IMAGES={
      '0':'https://i.imgur.com/cdMEbIV.png',
      '-1':'https://i.imgur.com/6KM038i.png',
      '-2':'https://i.imgur.com/aFlSOz5.png',
      '-3':'https://i.imgur.com/aFlSOz5.png',
      '1':'https://i.imgur.com/Wuax2xW.png',
      '2':'https://i.imgur.com/gp6VpuU.png',
      '3':'https://i.imgur.com/gp6VpuU.png'
    };

    function q4NearestStep(angle){
      const idx=Math.round(angle/Q4_STEP_DEG);
      const wrapped=((idx%Q4_STEP_COUNT)+Q4_STEP_COUNT)%Q4_STEP_COUNT;
      const map=[-3,-2,-1,0,1,2,3];
      return map[wrapped];
    }
    function q4AngleAt(el,x,y){ const r=el.getBoundingClientRect(); return Math.atan2(y-(r.top+r.height/2), x-(r.left+r.width/2))*180/Math.PI; }
    function q4Norm(d){ while(d>180)d-=360; while(d<-180)d+=360; return d; }

    function q4UpdateImage(step){
      let key='0';
      if(step<=-2) key='-2';
      else if(step===-1) key='-1';
      else if(step===0) key='0';
      else if(step===1) key='1';
      else if(step>=2) key='2';
      if(key!==q4State.lastImgKey){
        q4StateImg.src = Q4_IMAGES[key];
        q4State.lastImgKey = key;
      }
    }

    function q4Animate(){
      q4State.current += (q4State.target - q4State.current) * 0.18;
      q4DialImg.style.transform = `rotate(${q4State.current}deg)`;
      const step = q4NearestStep(q4State.current);
      if(step!==q4State.lastStep){
        q4DialImg.classList.remove('q4-step-kick'); void q4DialImg.offsetWidth; q4DialImg.classList.add('q4-step-kick');
        q4State.lastStep=step;
      }
      q4UpdateImage(step);
      requestAnimationFrame(q4Animate);
    }
    requestAnimationFrame(q4Animate);

    q4DialImg.addEventListener('mousedown', e=>{ q4State.dragging=true; q4State.lastA=q4AngleAt(q4DialImg,e.clientX,e.clientY); e.preventDefault(); });
    document.addEventListener('mousemove', e=>{
      if(!q4State.dragging) return;
      const a=q4AngleAt(q4DialImg,e.clientX,e.clientY);
      const d=q4Norm(a-q4State.lastA);
      q4State.target+=d;
      q4State.lastA=a; e.preventDefault();
    });
    document.addEventListener('mouseup', ()=>{
      if(!q4State.dragging) return;
      q4State.dragging=false;
      const step=Math.round(q4State.target/Q4_STEP_DEG);
      q4State.target=step*Q4_STEP_DEG;
    });

    q4DialImg.addEventListener('touchstart', e=>{
      q4State.dragging=true; const t=e.touches[0];
      q4State.lastA=q4AngleAt(q4DialImg,t.clientX,t.clientY); e.preventDefault();
    }, {passive:false});
    document.addEventListener('touchmove', e=>{
      if(!q4State.dragging) return;
      const t=e.touches[0]; const a=q4AngleAt(q4DialImg,t.clientX,t.clientY);
      const d=q4Norm(a-q4State.lastA);
      q4State.target+=d; q4State.lastA=a; e.preventDefault();
    }, {passive:false});
    document.addEventListener('touchend', ()=>{
      if(!q4State.dragging) return;
      q4State.dragging=false;
      const step=Math.round(q4State.target/Q4_STEP_DEG);
      q4State.target=step*Q4_STEP_DEG;
    });

    // LOADING: 5초, 채움 45%
    let loadingRAF=null, loadingStart=0, loadingDur=5000, fillRatio=0.45;
    function startPrinting(){
      stopPrinting();
      loadingStart=performance.now();
      const clipH=windowClip?windowClip.clientHeight:0;
      function tick(now){
        if(!windowClip) return;
        const t=Math.min(1,(now-loadingStart)/loadingDur);
        const ease=t<0.5?2*t*t:1-Math.pow(-2*t+2,2)/2;
        const h=Math.max(2,Math.round(clipH*fillRatio*ease));
        liquid.style.height=h+'px';
        loadingRAF=requestAnimationFrame(tick);
      }
      loadingRAF=requestAnimationFrame(tick);
    }
    function stopPrinting(){ if(loadingRAF){ cancelAnimationFrame(loadingRAF); loadingRAF=null; } if(liquid){ liquid.style.height='0px'; } }

    // 네비
    document.getElementById('q1-back-btn').onclick=()=> show('info');
    document.getElementById('q2-back-btn').onclick=()=> show('q1');
    document.getElementById('q3-back-btn').onclick=()=> show('q2');
    document.getElementById('q4-back-btn').onclick=()=> show('q3');

    document.getElementById('q4-finish-btn').addEventListener('click', ()=>{
      show('loading');
      setTimeout(()=>{
        const imgs=['https://i.imgur.com/uwJHQSt.png','https://i.imgur.com/rYmbPsr.png','https://i.imgur.com/KI2WR6a.png'];
        document.getElementById('result-image').src=imgs[Math.floor(Math.random()*imgs.length)];
        document.getElementById('result-message').textContent=`${answers.userName||''}님의 추억의 향기가 완성 되었습니다.`;
        show('result');
      }, 5000);
    });

    document.getElementById('result-home-btn').addEventListener('click', ()=>{ resetAll(); show('start'); });

    // 초기
    resetAll(); show('start');
  </script>
</body>
</html>
