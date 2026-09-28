<!DOCTYPE html>
<html lang="ko">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>크라임씬: 블루비치 살인사건</title>
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
            font-size: 1.6rem;
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
    <h1>🩸 크라임씬: 블루비치 살인사건</h1>

    <!-- 1단계: 설정 -->
    <div id="setup-screen">
        <div class="story-box">
            <div class="story-title">📌 사건 개요</div>
            폭풍우가 치던 밤 10시, 블루비치 리조트 VIP 룸에서 리조트 회장 **'김회장(50대)'**이 숨진 채 발견되었습니다. 사망 원인은 청산가리 중독.<br>
            현장에 있던 4명의 용의자 중 **단 한 명만이 진범**입니다!
        </div>

        <p style="font-size:0.85rem; color:#8b949e; margin-bottom:12px;">참가자 4명의 이름을 입력하세요:</p>
        
        <div class="input-group"><label>용의자 1 (박파트너 - 사업 동업자)</label><input type="text" id="p1" value="철수"></div>
        <div class="input-group"><label>용의자 2 (최지배인 - 리조트 매니저)</label><input type="text" id="p2" value="영희"></div>
        <div class="input-group"><label>용의자 3 (이주치의 - 개인 의사)</label><input type="text" id="p3" value="민수"></div>
        <div class="input-group"><label>용의자 4 (강배우자 - 김회장의 아내)</label><input type="text" id="p4" value="지민"></div>

        <button onclick="startGame()">역할 및 은밀한 시나리오 확인</button>
    </div>

    <!-- 2단계: 개별 비밀 역할 카드 -->
    <div id="game-screen" class="hidden">
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
                    <strong>[사건 당일 상세 동선 (21:00~22:00)]</strong><br><span id="char-alibi"></span><br><br>
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
            <!-- 라운드별 단서가 여기에 동적으로 들어감 -->
        </div>

        <button id="round-btn" onclick="nextRound()" class="btn-secondary">2라운드 단서 공개하기 (심층 수사)</button>
    </div>
</div>

<script>
    const characterTemplates = [
        {
            roleName: "박파트너 (사업 동업자)",
            bg: "김회장과 10년간 리조트를 공동 운영해 온 야망 있는 사업가.",
            alibi: "• 21:00~21:30 로비 카페에서 혼자 와인을 마시며 노트북 작업.<br>• 21:30~21:45 1층 화장실에 다녀옴.<br>• 21:45~22:00 로비로 돌아와 주치의(이주치의)와 잠시 대화 후 객실로 이동.",
            secret: "김회장이 자신을 배신하고 리조트 지분 전체를 해외 펀드에 몰래 넘기려던 정황을 포착했다. 오늘 밤 김회장에게 독설을 퍼부으며 와인 잔을 깨부수고 위협했었다."
        },
        {
            roleName: "최지배인 (리조트 매니저)",
            bg: "리조트의 모든 열쇠와 비상통로를 꿰뚫고 있는 꼼꼼한 총지배인.",
            alibi: "• 21:00~21:20 김회장의 요청으로 고급 와인과 잔을 VIP 룸으로 배달.<br>• 21:20~21:40 비바람 때문에 창문 점검차 3층 복도를 순찰.<br>• 21:40~22:00 카운터에서 직원 일지 작성.",
            secret: "리조트 공금 3억 원을 유용해 도박으로 날렸다. 김회장이 오늘 밤 감사 자료를 요구했고, 사실이 밝혀지면 감옥에 갈 위기였다. 청산가리를 구해 리조트 수건에 묻혀 보관 중이었다."
        },
        {
            roleName: "이주치의 (개인 의사)",
            bg: "김회장의 지병을 전담하며 심복 역할을 해온 전담 의사.",
            alibi: "• 21:00~21:15 김회장의 VIP 룸에 들러 정기 처방약(알약)을 전달.<br>• 21:15~21:50 본인 객실에서 정체불명의 전화 통화.<br>• 21:50~22:00 로비에서 박파트너와 마주쳐 인사 나눔.",
            secret: "김회장의 배우자와 불륜 관계이다. 최근 김회장이 불륜 사실을 눈치채고 나를 의료법 위반으로 매장시키겠다고 협박하여 극도의 불안 상태였다."
        },
        {
            roleName: "강배우자 (김회장의 아내)",
            bg: "김회장과 재혼한 연하의 배우자. 겉으로는 화려해 보이나 늘 감시당함.",
            alibi: "• 21:00~21:40 답답해서 우산을 쓰고 리조트 해변 산책로를 걸음.<br>• 21:40~22:00 젖은 옷을 갈아입기 위해 본인 객실로 들어감.",
            secret: "김회장 몰래 이주치의와 연인 관계를 이어왔다. 김회장이 유언장을 수정해 나에게 유산을 한 푼도 남기지 않으려 한다는 것을 알고 오늘 밤 유언장 원본을 몰래 훔쳐냈다."
        }
    ];

    let players = [];
    let assignedRoles = [];
    let currentIndex = 0;
    let isRevealed = false;
    let currentRound = 1;

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
        const killerIndex = Math.floor(Math.random() * 4);

        assignedRoles = characterTemplates.map((char, index) => ({
            ...char,
            isKiller: index === killerIndex
        }));

        assignedRoles.sort(() => Math.random() - 0.5);

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
            container.innerHTML = `
                <div class="clue-box">
                    <strong>🔍 단서 1. 피해자의 와인 잔</strong><br>
                    김회장이 마신 와인 잔에서 청산가리가 검출되었습니다. 와인병은 따져 있었으나 병 자체에는 독약이 없었습니다. (잔에만 독이 묻어있었음)
                </div>
                <div class="clue-box">
                    <strong>🔍 단서 2. 찢어진 종이 조각</strong><br>
                    VIP 룸 쓰레기통에서 "지분 인수 계약 파기 - 박..."이라고 적힌 찢어진 서류 조각이 발견되었습니다.
                </div>
                <div class="clue-box">
                    <strong>🔍 단서 3. 젖은 우산</strong><br>
                    VIP 룸 입구 신발장에서 젖어 있는 검은색 우산 하나가 발견되었습니다.
                </div>
            `;
            roundBtn.innerText = "2라운드 단서 공개하기 (심층 수사)";
        } else if (currentRound === 2) {
            roundTag.innerText = "ROUND 2";
            roundTitle.innerText = "2라운드: 결정적 심층 단서 공개";
            container.innerHTML = `
                <div class="clue-box" style="border-color:#ff7b72;">
                    <strong>🚨 심층 단서 A. 시신의 상태 (사망 추정시각 21:20~21:40)</strong><br>
                    부검 결과 독극물은 와인 잔이 아닌 **와인 오프너 손잡이**와 **처방약 캡슐 내부** 중 한 곳에 직접 도포되었을 가능성이 제기되었습니다.
                </div>
                <div class="clue-box" style="border-color:#ff7b72;">
                    <strong>🚨 심층 단서 B. 비밀 편지</strong><br>
                    김회장의 침대 밑에서 발견된 편지: "당신과 의사의 관계를 알고 있다. 오늘 밤 모든 것을 끝내겠다."
                </div>
                <div class="clue-box" style="border-color:#ff7b72;">
                    <strong>🚨 심층 단서 C. CCTV 복원 기록</strong><br>
                    21시 30분경, 누군가 VIP 룸 비상계단 문을 열고 들어가는 장면이 찍혔습니다. 그 인물은 **지배인 전용 키카드**를 사용했습니다.
                </div>
            `;
            roundBtn.innerText = "최종 지목 및 투표 단계로 이동";
            roundBtn.style.backgroundColor = "#ff4757";
        } else if (currentRound === 3) {
            roundTag.innerText = "FINAL ROUND";
            roundTitle.innerText = "3라운드: 최종 범인 지목 및 투표";
            container.innerHTML = `
                <div class="story-box" style="border-left-color:#f1e05a; text-align:center;">
                    <div class="story-title">⚖️ 투표 및 토론 마무리</div>
                    모든 단서가 공개되었습니다.<br>
                    서로의 알리바이 허점과 정황 증거를 바탕으로 토론을 마치고, **동시에 범인을 지목**하세요!
                </div>
            `;
            roundBtn.innerText = "새 게임 시작하기";
            roundBtn.style.backgroundColor = "#21262d";
        }
    }

    function nextRound() {
        if (currentRound < 3) {
            currentRound++;
            renderRound();
        } else {
            location.reload(); // 새 게임 리셋
        }
    }
</script>

</body>
</html>
