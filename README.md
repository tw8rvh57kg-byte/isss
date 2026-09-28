<!DOCTYPE html>
<html lang="ko">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>크라임씬: 랜덤 추리 사건집</title>
    <style>
        * {
            box-sizing: border-box;
            font-family: 'Pretendard', -apple-system, BlinkMacSystemFont, system-ui, Roboto, sans-serif;
        }
        body {
            background-color: #0d1117;
            color: #c9d1d9;
            display: flex;
            justify-content: center;
            align-items: center;
            min-height: 100vh;
            margin: 0;
            padding: 20px;
        }
        .container {
            background-color: #161b22;
            padding: 28px;
            border-radius: 16px;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.8);
            max-width: 540px;
            width: 100%;
            border: 1px solid #30363d;
        }
        h1 {
            color: #ff4757;
            text-align: center;
            margin-top: 0;
            font-size: 1.5rem;
        }
        .story-box {
            background-color: #21262d;
            border-left: 4px solid #ff4757;
            padding: 15px;
            border-radius: 6px;
            font-size: 0.92rem;
            line-height: 1.6;
            margin-bottom: 20px;
        }
        .story-title {
            font-weight: bold;
            color: #ffffff;
            margin-bottom: 6px;
            font-size: 1.05rem;
        }
        .input-group {
            margin-bottom: 12px;
        }
        label {
            display: block;
            margin-bottom: 4px;
            font-size: 0.85rem;
            color: #8b949e;
        }
        input {
            width: 100%;
            padding: 10px 12px;
            border-radius: 8px;
            border: 1px solid #30363d;
            background-color: #0d1117;
            color: #fff;
            font-size: 0.95rem;
        }
        button {
            width: 100%;
            padding: 13px;
            border: none;
            border-radius: 8px;
            background-color: #ff4757;
            color: white;
            font-size: 1rem;
            font-weight: bold;
            cursor: pointer;
            transition: background 0.2s;
            margin-top: 10px;
        }
        button:hover {
            background-color: #ff6b81;
        }
        .btn-secondary {
            background-color: #238636;
        }
        .btn-secondary:hover {
            background-color: #2ea043;
        }
        .btn-truth {
            background-color: #8a2be2;
        }
        .btn-truth:hover {
            background-color: #9932cc;
        }
        .card {
            background: #21262d;
            border: 2px dashed #ff4757;
            border-radius: 12px;
            padding: 24px 20px;
            margin: 20px 0;
            text-align: center;
            cursor: pointer;
            user-select: none;
            min-height: 200px;
        }
        .hidden {
            display: none !important;
        }
        .role-title {
            font-size: 1.4rem;
            font-weight: bold;
            color: #f1e05a;
            margin-bottom: 8px;
        }
        .is-killer {
            color: #ff4757;
            font-weight: bold;
            background: #3c1e1e;
            padding: 8px 12px;
            border-radius: 6px;
            display: inline-block;
            margin-bottom: 12px;
        }
        .is-innocent {
            color: #2ea043;
            font-weight: bold;
            background: #1e3c23;
            padding: 8px 12px;
            border-radius: 6px;
            display: inline-block;
            margin-bottom: 12px;
        }
        .info-block {
            text-align: left;
            background: #0d1117;
            padding: 14px;
            border-radius: 8px;
            font-size: 0.88rem;
            line-height: 1.6;
            margin-top: 10px;
            border: 1px solid #30363d;
        }
        .info-block strong {
            color: #58a6ff;
        }
        .secret-text {
            color: #ff7b72;
            font-weight: bold;
        }
        .clue-box {
            background: #21262d;
            border: 1px solid #30363d;
            padding: 14px;
            border-radius: 8px;
            margin-bottom: 12px;
            font-size: 0.9rem;
            line-height: 1.5;
            text-align: left;
        }
        .clue-box strong {
            color: #f1e05a;
        }
        .truth-box {
            background: #1a1528;
            border: 2px solid #8a2be2;
            padding: 16px;
            border-radius: 8px;
            margin-bottom: 16px;
            font-size: 0.9rem;
            line-height: 1.6;
            text-align: left;
        }
        .truth-box strong {
            color: #d8b4fe;
        }
        .notice {
            font-size: 0.8rem;
            color: #8b949e;
            text-align: center;
            margin-top: 8px;
        }
        .round-tag {
            background: #1f6beb;
            color: white;
            padding: 4px 8px;
            border-radius: 4px;
            font-size: 0.8rem;
            display: inline-block;
            margin-bottom: 10px;
        }
    </style>
</head>
<body>

<div class="container">
    <h1 id="game-main-title">🕵️ 크라임씬 추리 시뮬레이터</h1>

    <!-- 1단계: 설정 -->
    <div id="setup-screen">
        <div class="story-box" style="border-left-color:#58a6ff;">
            <div class="story-title">🎲 시나리오 무작위 추첨</div>
            게임을 시작하면 준비된 다양한 살인사건 시나리오 중 하나가 **랜덤으로 배정**됩니다.<br>
            참가자 4명의 이름을 입력하고 시작해 주세요.
        </div>

        <p style="font-size:0.85rem; color:#8b949e; margin-bottom:12px;">참가자 4명의 이름을 입력하세요:</p>
        
        <div class="input-group"><label>참가자 1</label><input type="text" id="p1" value="철수"></div>
        <div class="input-group"><label>참가자 2</label><input type="text" id="p2" value="영희"></div>
        <div class="input-group"><label>참가자 3</label><input type="text" id="p3" value="민수"></div>
        <div class="input-group"><label>참가자 4</label><input type="text" id="p4" value="지민"></div>

        <button onclick="startGame()">🎲 무작위 사건 생성 및 역할 배정</button>
    </div>

    <!-- 2단계: 개별 비밀 역할 카드 -->
    <div id="game-screen" class="hidden">
        <div class="story-box" id="case-overview-box"></div>

        <h2 id="current-player-display" style="text-align:center; color:#58a6ff; margin-bottom:5px;"></h2>
        
        <div class="card" id="role-card" onclick="toggleRole()">
            <div id="card-prompt">
                🔍 <strong>터치하여 본인의 캐릭터/상세 알리바이/치명적 비밀 확인</strong>
            </div>
            
            <div id="card-content" class="hidden">
                <div id="char-name" class="role-title"></div>
                <div id="killer-status"></div>
                
                <div class="info-block">
                    <strong>[인물 배경]</strong> <span id="char-bg"></span><br><br>
                    <strong>[사건 당일 상세 동선]</strong><br><span id="char-alibi"></span><br><br>
                    <strong>[나만의 은밀한 비밀 & 동기]</strong><br><span id="char-secret" class="secret-text"></span>
                </div>
            </div>
        </div>

        <p class="notice">본인의 역할을 확인하고 숙지한 후 다시 터치하여 숨겨주세요.</p>
        <button id="next-btn" onclick="nextPlayer()" class="hidden">확인 완료 (다음 사람에게 넘기기)</button>
    </div>

    <!-- 3단계: 라운드별 단서 및 진행 화면 -->
    <div id="board-screen" class="hidden">
        <div style="text-align:center;">
            <span id="round-indicator" class="round-tag">ROUND 1</span>
        </div>
        <h2 id="round-title" style="text-align:center; margin-top:5px;">1라운드: 현장 조사 및 1차 토론</h2>
        
        <div id="clue-container">
            <!-- 라운드별 내용 동적 삽입 -->
        </div>

        <button id="round-btn" onclick="nextRound()" class="btn-secondary">2라운드 단서 공개하기 (심층 수사)</button>
    </div>
</div>

<script>
    // ----------------------------------------------------
    // 다중 사건 시나리오 데이터베이스 (4개 시나리오)
    // ----------------------------------------------------
    const scenarioDatabase = [
        // 시나리오 1: 해변 리조트
        {
            title: "🩸 블루비치 리조트 살인사건",
            overview: "폭풍우가 치던 밤 10시, VIP 룸에서 리조트 회장이 숨진 채 발견되었습니다. 사망 원인은 청산가리 중독. 용의자 4명 중 진범은 단 한 명입니다!",
            characters: [
                { id: "park", roleName: "박파트너 (사업 동업자)", bg: "김회장과 10년간 리조트를 공동 운영해 온 야망 있는 사업가.", alibi: "• 21:00~21:30 로비 카페에서 커피를 마시며 노트북 작업.<br>• 21:30~21:45 1층 화장실 다녀옴.<br>• 21:45~22:00 로비에서 주치의와 만남.", secret: "김회장이 자신을 배신하고 리조트 전체를 해외에 몰래 팔아치우려 한 정황을 알고 독설을 퍼부었었다." },
                { id: "choi", roleName: "최지배인 (리조트 매니저)", bg: "리조트의 모든 열쇠와 비상통로를 꿰뚫고 있는 총지배인.", alibi: "• 21:00~21:20 김회장 요청으로 와인을 배달.<br>• 21:20~21:40 3층 복도 순찰.<br>• 21:40~22:00 카운터에서 업무 일지 작성.", secret: "공금 3억 원을 유용해 도박으로 날렸다. 오늘 밤 감사 자료 요구를 받았으며, 청산가리를 수건에 묻혀 보관 중이었다." },
                { id: "lee", roleName: "이주치의 (개인 의사)", bg: "김회장의 지병을 전담해 온 개인 의사.", alibi: "• 21:00~21:15 정기 처방약 전달.<br>• 21:15~21:50 객실에서 개인 통화.<br>• 21:50~22:00 로비에서 박파트너와 마주침.", secret: "김회장의 배우자와 불륜 관계이며, 김회장이 불륜 사실을 알고 자신을 매장 협박하여 불안 상태였다." },
                { id: "kang", roleName: "강배우자 (김회장의 아내)", bg: "김회장과 재혼한 연하의 배우자.", alibi: "• 21:00~21:40 우산을 쓰고 해변 산책.<br>• 21:40~22:00 객실로 들어가 옷을 갈아입음.", secret: "유산 상속에서 완전 배제하겠다는 유언장 개정 사실을 알고 오늘 밤 유언장 원본을 훔쳐냈다." }
            ],
            round1Clues: [
                "🔍 **단서 1. 와인 잔**: 김회장의 와인 잔 입구에서 청산가리가 검출됨. 와인병 내부는 깨끗함.",
                "🔍 **단서 2. 찢어진 서류**: 쓰레기통에서 '지분 인수 계약 파기 - 박...' 서류 발견.",
                "🔍 **단서 3. 젖은 우산**: 신발장에서 방금 사용한 젖은 검은색 우산 발견."
            ],
            round2Clues: [
                "🚨 **심층 단서 A. 시신 상태**: 사망 추정시각 21:20~21:40. 독극물은 와인 오프너 손잡이 또는 약 캡슐에 도포되었을 가능성.",
                "🚨 **심층 단서 B. 비밀 편지**: '당신과 의사의 관계를 알고 있다.' 메세지 발견.",
                "🚨 **심층 단서 C. CCTV 기록**: 21시 30분, 비상계단 문이 지배인 키카드로 열림."
            ],
            truths: {
                choi: "<strong>[진범: 최지배인]</strong><br>공금 유용 발각 위기에 처하자, 21시 와인 배달 시 수건에 묻힌 청산가리를 와인 잔과 오프너에 발라두었습니다. 21시 30분 키카드로 비상계단을 통해 들어와 사망을 확인했습니다.",
                lee: "<strong>[진범: 이주치의]</strong><br>불륜 협박에 분노하여 21시 약 전달 시 캡슐 하나를 청산가리로 교체했습니다. 김회장이 약을 먹고 와인으로 입을 헹구다 사망했습니다.",
                kang: "<strong>[진범: 강배우자]</strong><br>유산 박탈 소식에 21시 20분 비상통로로 들어와 와인 잔에 독을 타고 유언장을 훔쳤습니다. 신발장의 젖은 우산이 증거입니다.",
                park: "<strong>[진범: 박파트너]</strong><br>지분 매각 배신에 분노하여 21시 15분 VIP 룸에 침입해 계약서를 찢고 와인 잔에 청산가리를 탔습니다."
            }
        },

        // 시나리오 2: 설산 스키 산장
        {
            title: "❄️ 설산 산장 밀실 살인사건",
            overview: "폭설로 고립된 산장 밤 11시, 산장 주인 '성장원'이 난로 옆에서 흉기에 맞아 숨진 채 발견되었습니다. 외부인 침입 불가! 범인은 산장 안에 있습니다.",
            characters: [
                { id: "kim", roleName: "김산악 (산악 구조대원)", bg: "산장의 위험 요소를 잘 아는 오랜 베테랑 구조대원.", alibi: "• 22:00~22:30 창고에서 제설 장비 점검.<br>• 22:30~23:00 2층 휴게실에서 차를 마심.", secret: "과거 성주인의 과실로 동료를 잃었으나 사고사로 위장된 사실을 얼마 전 알게 되었다." },
                { id: "lee_doc", roleName: "이약사 (약사)", bg: "산장에 휴가를 온 정체불명의 조용한 손님.", alibi: "• 22:00~22:40 방에서 책을 읽음.<br>• 22:40~23:00 화장실에 들렀다가 거실로 나옴.", secret: "성주인에게 거액의 사채 빚을 지고 있었으며, 장기 매매 협박을 받고 있었다." },
                { id: "park_sub", roleName: "박알바 (산장 아르바이트생)", bg: "산장에서 청소와 요리를 담당하는 스태프.", alibi: "• 22:00~22:20 주방 정리.<br>• 22:20~22:50 와인 창고 재고 조사.", secret: "성주인의 비밀 장부를 도둑질하다 걸려 오늘 강제 퇴출 통보를 받았다." },
                { id: "choi_pro", roleName: "최프로 (프로 스키선수)", bg: "성주인의 후원을 받고 있는 유명 스키 선수.", alibi: "• 22:00~22:40 방에서 가벼운 재활 운동.<br>• 22:40~23:00 거실로 나와 난로 확인.", secret: "도핑 테스트 적발 사실을 성주인이 쥐고 언론에 터뜨리겠다고 협박하던 중이었다." }
            ],
            round1Clues: [
                "🔍 **단서 1. 혈흔이 묻은 등산 스틱**: 난로 뒤편에서 피가 묻은 금속 스틱 발견.",
                "🔍 **단서 2. 타다 남은 차용증**: 난로 내부에서 성주인의 이름이 적힌 차용증 조각 구출.",
                "🔍 **단서 3. 깨진 시계**: 피해자의 손목시계가 밤 10시 25분에 멈춰 있음."
            ],
            round2Clues: [
                "🚨 **심층 단서 A. 와인 창고 열쇠**: 와인 창고 열쇠고리에서 김산악의 지문 발견.",
                "🚨 **심층 단서 B. 협박 편지**: 최프로 방에서 '도핑 건으로 내일 매장시키겠다'는 메세지 발굴.",
                "🚨 **심층 단서 C. 약병**: 화장실 쓰레기통에서 강력 수면제 빈 병 발견."
            ],
            truths: {
                kim: "<strong>[진범: 김산악]</strong><br>동료의 억울한 죽음을 복수하기 위해, 22시 20분 등산 스틱으로 성주인을 가격했습니다.",
                lee_doc: "<strong>[진범: 이약사]</strong><br>장기 매매 협박을 견디지 못하고 차에 수면제를 타서 잠들게 한 뒤, 10시 25분 난로 옆 흉기로 살해했습니다.",
                park_sub: "<strong>[진범: 박알바]</strong><br>강제 퇴출에 분노해 와인 창고에서 가져온 둔기로 성주인을 살해하고 난로에 장부를 태웠습니다.",
                choi_pro: "<strong>[진범: 최프로]</strong><br>도핑 폭로 협박을 막기 위해 22시 25분 난로 앞에서 격투 끝에 스틱으로 범행을 저질렀습니다."
            }
        },

        // 시나리오 3: 고풍스러운 블랙우드 저택
        {
            title: "🏰 블랙우드 저택 대저택 살인사건",
            overview: "비 내리는 밤 11시, 억만장자 '블랙우드 남작'이 서재 2층 난간 아래로 떨어져 사망했습니다. 단순 추락사일까요, 치밀한 살인일까요?",
            characters: [
                { id: "butler", roleName: "집사 집사 (집사장)", bg: "저택의 모든 비밀과 열쇠를 관리하는 늙은 집사.", alibi: "• 22:15~22:45 남작의 야식을 준비함.<br>• 22:45~23:00 와인 셀러 정리.", secret: "유언장에 자신에게 저택 일부가 상속되도록 몰래 서류를 위조해 두었다." },
                { id: "artist", roleName: "화가 화가 (초상화가)", bg: "저택에 머물며 남작 부인의 초상화를 그리던 화가.", alibi: "• 22:00~22:40 화실에서 작업.<br>• 22:40~23:00 서재 앞 복도를 지남.", secret: "남작의 희귀 미술품 중 하나를 가짜와 몰래 교체한 대담한 도둑이었다." },
                { id: "baroness", roleName: "남작부인 (남작의 아내)", bg: "남작과 잦은 불화를 겪던 재벌가 출신 부인.", alibi: "• 22:00~22:30 침실에서 침대 휴식.<br>• 22:30~23:00 침실 정원 산책.", secret: "남작이 자신을 정략결혼용으로 이용하고 비밀 계좌를 동결하려던 사실을 알았다." },
                { id: "nephew", roleName: "친척 조카 (남작의 조카)", bg: "방탕한 생활로 빚더미에 앉은 조카.", alibi: "• 22:00~22:50 응접실에서 술을 마심.<br>• 22:50~23:00 서재로 이동.", secret: "오늘 밤까지 10억 원의 빚을 갚지 못하면 조직에 의해 목숨이 위험한 상황이었다." }
            ],
            round1Clues: [
                "🔍 **단서 1. 부러진 난간**: 2층 서재 난간 목재가 고의로 톱질되어 절단되어 있음.",
                "🔍 **단서 2. 진흙 발자국**: 서재 난간 근처에 고급 가죽구두의 진흙 발자국.",
                "🔍 **단서 3. 위조된 유언장**: 서재 책상 위 작성 중이던 서류 조각."
            ],
            round2Clues: [
                "🚨 **심층 단서 A. 톱가루**: 집사의 앞치마 주머니에서 미세한 목재 톱가루 검출.",
                "🚨 **심층 단서 B. 물감 묻은 장갑**: 화실 쓰레기통에서 난간에 묻은 것과 같은 유채 물감 장갑 발견.",
                "🚨 **심층 단서 C. 차용증 현금**: 조카의 가방에서 막대한 현금 수표 발견."
            ],
            truths: {
                butler: "<strong>[진범: 집사]</strong><br>위조 유언장이 발각될까 두려워, 사전 톱질해둔 2층 난간으로 남작을 밀어 살해했습니다.",
                artist: "<strong>[진범: 화가]</strong><br>위작 교체 사실을 남작이 눈치채자 서재에서 다투다 난간 밖으로 밀어버렸습니다.",
                baroness: "<strong>[진범: 남작부인]</strong><br>계좌 동결 및 이혼 협박에 분노해 정원 산책 중 서재로 들어가 난간 밖으로 던졌습니다.",
                nephew: "<strong>[진범: 조카]</strong><br>상속금을 당장 차지하기 위해 밤 10시 45분 남작을 밀어 추락사시켰습니다."
            }
        }
    ];

    // 게임 상태 변수
    let currentScenario = null;
    let players = [];
    let assignedRoles = [];
    let currentIndex = 0;
    let isRevealed = false;
    let currentRound = 1;
    let killerPlayerName = "";
    let killerCharInfo = null;

    function startGame() {
        const p1 = document.getElementById('p1').value.trim();
        const p2 = document.getElementById('p2').value.trim();
        const p3 = document.getElementById('p3').value.trim();
        const p4 = document.getElementById('p4').value.trim();

        if (!p1 || !p2 || !p3 || !p4) {
            alert('4명의 참가자 이름을 모두 입력하세요.');
            return;
        }

        players = [p1, p2, p3, p4];

        // 1. 시나리오 무작위 추첨 (0 ~ N-1)
        const randScenarioIdx = Math.floor(Math.random() * scenarioDatabase.length);
        currentScenario = scenarioDatabase[randScenarioIdx];

        // 메인 타이틀 & 개요 세팅
        document.getElementById('game-main-title').innerText = currentScenario.title;
        document.getElementById('case-overview-box').innerHTML = `
            <div class="story-title">📌 사건 개요</div>
            ${currentScenario.overview}
        `;

        // 2. 범인 무작위 지정
        const killerIndex = Math.floor(Math.random() * 4);

        assignedRoles = currentScenario.characters.map((char, index) => ({
            ...char,
            isKiller: index === killerIndex
        }));

        // 3. 순서 및 역할 셔플
        assignedRoles.sort(() => Math.random() - 0.5);

        // 범인 정보 저장
        const killerObj = assignedRoles.find(r => r.isKiller);
        const killerIdx = assignedRoles.indexOf(killerObj);
        killerPlayerName = players[killerIdx];
        killerCharInfo = killerObj;

        currentIndex = 0;
        document.getElementById('setup-screen').classList.add('hidden');
        document.getElementById('game-screen').classList.remove('hidden');

        updateTurn();
    }

    function updateTurn() {
        isRevealed = false;
        document.getElementById('current-player-display').innerText = `👤 ${players[currentIndex]} 님의 차례`;
        document.getElementById('card-prompt').classList.remove('hidden');
        document.getElementById('card-content').classList.add('hidden');
        document.getElementById('next-btn').classList.add('hidden');
    }

    function toggleRole() {
        const cardPrompt = document.getElementById('card-prompt');
        const cardContent = document.getElementById('card-content');
        const nextBtn = document.getElementById('next-btn');

        if (!isRevealed) {
            const role = assignedRoles[currentIndex];
            document.getElementById('char-name').innerText = role.roleName;
            
            const killerStatus = document.getElementById('killer-status');
            if (role.isKiller) {
                killerStatus.innerHTML = '<div class="is-killer">🚨 당신은 진범입니다!</div><br><small style="color:#ff7b72;">자신의 비밀과 거짓 알리바이를 조화롭게 섞어 다른 사람에게 죄를 뒤집어씌우세요.</small>';
            } else {
                killerStatus.innerHTML = '<div class="is-innocent">🟢 당신은 무고한 용의자입니다.</div><br><small style="color:#7ee787;">은밀한 비밀은 숨기되, 알리바이의 모순을 찾아 범인을 밝혀내세요.</small>';
            }

            document.getElementById('char-bg').innerText = role.bg;
            document.getElementById('char-alibi').innerHTML = role.alibi;
            document.getElementById('char-secret').innerText = role.secret;

            cardPrompt.classList.add('hidden');
            cardContent.classList.remove('hidden');
            nextBtn.classList.remove('hidden');
            isRevealed = true;
        } else {
            cardPrompt.classList.remove('hidden');
            cardContent.classList.add('hidden');
            isRevealed = false;
        }
    }

    function nextPlayer() {
        currentIndex++;
        if (currentIndex < players.length) {
            updateTurn();
        } else {
            document.getElementById('game-screen').classList.add('hidden');
            document.getElementById('board-screen').classList.remove('hidden');
            renderRound();
        }
    }

    function renderRound() {
        const container = document.getElementById('clue-container');
        const roundTag = document.getElementById('round-indicator');
        const roundTitle = document.getElementById('round-title');
        const roundBtn = document.getElementById('round-btn');

        if (currentRound === 1) {
            roundTag.innerText = "ROUND 1";
            roundTitle.innerText = "1라운드: 현장 조사 및 알리바이 검증";
            
            container.innerHTML = currentScenario.round1Clues.map(c => `<div class="clue-box">${c}</div>`).join('');
            roundBtn.innerText = "2라운드 단서 공개하기 (심층 수사)";
        } else if (currentRound === 2) {
            roundTag.innerText = "ROUND 2";
            roundTitle.innerText = "2라운드: 결정적 심층 단서 공개";
            
            container.innerHTML = currentScenario.round2Clues.map(c => `<div class="clue-box" style="border-color:#ff7b72;">${c}</div>`).join('');
            roundBtn.innerText = "최종 지목 및 투표 단계로 이동";
            roundBtn.style.backgroundColor = "#ff4757";
        } else if (currentRound === 3) {
            roundTag.innerText = "FINAL ROUND";
            roundTitle.innerText = "3라운드: 최종 범인 지목 및 투표";
            container.innerHTML = `
                <div class="story-box" style="border-left-color:#f1e05a; text-align:center;">
                    <div class="story-title">⚖️ 투표 진행</div>
                    모든 단서가 공개되었습니다.<br>
                    서로의 알리바이 허점과 정황 증거를 바탕으로 토론을 마치고, **동시에 범인을 지목**하세요!
                </div>
            `;
            roundBtn.innerText = "🔓 해답 및 범행 전말 공개";
            roundBtn.className = "btn-truth";
        } else if (currentRound === 4) {
            roundTag.innerText = "TRUTH REVEALED";
            roundTag.style.backgroundColor = "#8a2be2";
            roundTitle.innerText = "🎭 사건의 진실 및 범행 전말";

            const truthStory = currentScenario.truths[killerCharInfo.id];

            container.innerHTML = `
                <div class="truth-box">
                    <h3 style="color:#ff4757; margin-top:0; text-align:center;">
                        🩸 진범: ${killerPlayerName} (${killerCharInfo.roleName})
                    </h3>
                    <hr style="border-color:#30363d; margin: 12px 0;">
                    ${truthStory}
                </div>
            `;
            roundBtn.innerText = "🔄 새로운 사건 시작하기 (랜덤)";
            roundBtn.style.backgroundColor = "#21262d";
        }
    }

    function nextRound() {
        if (currentRound < 4) {
            currentRound++;
            renderRound();
        } else {
            location.reload();
        }
    }
</script>

</body>
</html>
