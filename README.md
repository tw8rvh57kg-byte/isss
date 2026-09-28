<!DOCTYPE html>
<html lang="ko">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>CRIMESCENE : PIXEL MYSTERY</title>
    <!-- 도트/픽셀 레트로 폰트 -->
    <link href="https://fonts.googleapis.com/css2?family=Press+Start+2P&family=Galmuri14&display=swap" rel="stylesheet">
    <style>
        * {
            box-sizing: border-box;
            font-family: 'Galmuri14', 'Pretendard', sans-serif;
        }
        body {
            background-color: #0d0e15;
            color: #e0e6ed;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            min-height: 100vh;
            margin: 0;
            padding: 20px;
            image-rendering: pixelated;
        }

        /* 상단 네비게이션 */
        .outer-nav {
            max-width: 520px;
            width: 100%;
            display: flex;
            justify-content: flex-end;
            margin-bottom: 8px;
        }
        .nav-btn {
            background-color: #212538;
            color: #a0a7c4;
            border: 2px solid #3a3f58;
            padding: 6px 12px;
            font-size: 0.8rem;
            cursor: pointer;
            box-shadow: 2px 2px 0 #000;
        }
        .nav-btn:hover {
            color: #fff;
            border-color: #ff4757;
        }

        /* 메인 컨테이너 */
        .container {
            background-color: #161824;
            padding: 22px;
            border-radius: 4px;
            box-shadow: 0 0 0 4px #2a2e45, 0 8px 0 4px #000;
            max-width: 520px;
            width: 100%;
            border: 4px solid #ff4757;
        }

        .pixel-header {
            font-family: 'Press Start 2P', monospace;
            color: #ff4757;
            text-align: center;
            font-size: 1.1rem;
            margin-bottom: 16px;
            text-shadow: 2px 2px #000;
        }

        .story-box {
            background-color: #212538;
            border: 3px solid #3a3f58;
            border-left: 6px solid #ff4757;
            padding: 12px 14px;
            font-size: 0.88rem;
            line-height: 1.5;
            margin-bottom: 14px;
        }
        .story-title {
            font-weight: bold;
            color: #f1e05a;
            margin-bottom: 6px;
        }

        .input-group {
            margin-bottom: 8px;
        }
        label {
            display: block;
            margin-bottom: 3px;
            font-size: 0.8rem;
            color: #a0a7c4;
        }
        input, select {
            width: 100%;
            padding: 8px;
            border: 3px solid #3a3f58;
            background-color: #0d0e15;
            color: #fff;
            font-size: 0.88rem;
            outline: none;
        }
        input:focus, select:focus {
            border-color: #ff4757;
        }

        button.btn-main {
            width: 100%;
            padding: 12px;
            border: 3px solid #000;
            background-color: #ff4757;
            color: white;
            font-size: 0.9rem;
            font-weight: bold;
            cursor: pointer;
            box-shadow: 3px 3px 0 #000;
            margin-top: 10px;
        }
        button.btn-main:active {
            transform: translate(2px, 2px);
            box-shadow: 0 0 0 #000;
        }
        .btn-yellow {
            background-color: #f1e05a;
            color: #000;
        }
        .btn-green {
            background-color: #2ed573;
            color: #000;
        }

        .hidden {
            display: none !important;
        }

        /* 프로필 및 비밀 카드 */
        .card {
            background: #212538;
            border: 3px dashed #ff4757;
            padding: 18px 14px;
            margin: 14px 0;
            text-align: center;
            cursor: pointer;
            user-select: none;
            min-height: 200px;
        }

        .info-block {
            text-align: left;
            background: #0d0e15;
            padding: 10px 12px;
            border: 2px solid #3a3f58;
            font-size: 0.83rem;
            line-height: 1.5;
            margin-top: 8px;
        }
        .info-block strong {
            color: #70a1ff;
        }
        .secret-text {
            color: #ff7b72;
            font-weight: bold;
        }

        .is-killer {
            color: #ff4757;
            font-weight: bold;
            background: #3c1e1e;
            padding: 4px 8px;
            border: 1px solid #ff4757;
            display: inline-block;
            margin-bottom: 6px;
            font-size: 0.8rem;
        }
        .is-innocent {
            color: #2ed573;
            font-weight: bold;
            background: #1e3c23;
            padding: 4px 8px;
            border: 1px solid #2ed573;
            display: inline-block;
            margin-bottom: 6px;
            font-size: 0.8rem;
        }

        .btn-row {
            display: flex;
            gap: 10px;
        }
        .btn-row button {
            flex: 1;
        }
    </style>
</head>
<body>

<div class="outer-nav">
    <button class="nav-btn" onclick="resetToHome()">🏠 처음으로</button>
</div>

<div class="container">
    <div class="pixel-header" id="game-title">👾 CRIMESCENE 👾</div>

    <!-- 1단계: 사건 선택 및 용의자 이름 입력 -->
    <div id="setup-screen">
        <div class="story-box">
            <div class="story-title">🎮 플레이할 사건 배경 선택</div>
            플레이하고 싶은 사건을 선택하고 용의자 4명의 이름을 입력해 주세요.
        </div>

        <div class="input-group">
            <label>사건 배경 시나리오</label>
            <select id="scenario-select">
                <option value="0">🩸 1. 블루비치 VIP룸 독살사건</option>
                <option value="1">❄️ 2. 설산 산장 밀실 살인사건</option>
            </select>
        </div>

        <div class="input-group"><label>용의자 1</label><input type="text" id="p1" value="철수"></div>
        <div class="input-group"><label>용의자 2</label><input type="text" id="p2" value="영희"></div>
        <div class="input-group"><label>용의자 3</label><input type="text" id="p3" value="민수"></div>
        <div class="input-group"><label>용의자 4</label><input type="text" id="p4" value="지민"></div>

        <button class="btn-main" onclick="startOverviewStage()">▶ 사건 개요 보기</button>
    </div>

    <!-- 2단계: 사건 개요 및 현장 브리핑 (모두 함께 보는 화면) -->
    <div id="overview-screen" class="hidden">
        <div class="story-box" id="overview-detail-box"></div>
        <p style="font-size:0.75rem; color:#a0a7c4; text-align:center;">💡 모든 플레이어가 사건 개요를 함께 숙지해 주세요.</p>
        <button class="btn-main btn-green" onclick="startRoleAssignmentStage()">▶ 개별 비밀 프로필 확인 시작</button>
    </div>

    <!-- 3단계: 개별 역할 및 비밀 확인 화면 (순차 진행) -->
    <div id="role-screen" class="hidden">
        <h3 id="current-player-display" style="text-align:center; color:#70a1ff; margin:0 0 8px 0;"></h3>
        
        <div class="card" id="role-card" onclick="toggleRole()">
            <div id="card-prompt">
                🔍 <strong>[터치하여 나만의 비밀 프로필 확인]</strong>
            </div>
            
            <div id="card-content" class="hidden">
                <div id="char-name" style="font-size:1.1rem; font-weight:bold; color:#f1e05a; margin-bottom:6px;"></div>
                <div id="killer-status"></div>
                
                <div class="info-block">
                    <strong>[시간대별 상세 동선 & 목격 정황]</strong><br><span id="char-alibi"></span><br><br>
                    <strong>[나만의 은밀한 비밀]</strong><br><span id="char-secret" class="secret-text"></span>
                </div>
            </div>
        </div>

        <p style="font-size:0.75rem; color:#a0a7c4; text-align:center; margin-bottom:8px;">확인 후 카드 영역을 다시 터치하여 화면을 숨겨주세요.</p>
        <div class="btn-row">
            <button id="prev-player-btn" onclick="prevPlayer()" class="btn-main btn-yellow">◀ 이전 사람</button>
            <button id="next-btn" onclick="nextPlayer()" class="btn-main hidden">다음 사람 ▶</button>
        </div>
    </div>

    <!-- 4단계: 사건의 전말 공개 -->
    <div id="truth-screen" class="hidden">
        <div class="story-box" style="border-left-color:#9b59b6;">
            <div class="story-title" style="color:#ff4757; text-align:center; font-size:1rem;" id="truth-killer-title"></div>
            <hr style="border-color:#3a3f58; margin:8px 0;">
            <div id="truth-content-box" style="font-size:0.85rem; line-height:1.6;"></div>
        </div>
        <button class="btn-main" onclick="resetToHome()">🔄 메인으로 돌아가기</button>
    </div>
</div>

<script>
    const scenarioDatabase = [
        {
            title: "🩸 블루비치 VIP룸 독살사건",
            overview: "<b>해변 리조트 3층 VIP룸에서 회장이 와인을 마시던 중 독살당했습니다.</b><br>문은 잠겨있지 않았고 용의자 4명 모두 정해진 시간 동안 피해자의 방 근처를 기웃거렸습니다.",
            characters: [
                {
                    id: "park", roleName: "박파트너 (동업자)",
                    alibi: "• 21:00~21:20 : 회장실에서 매각 문제로 크게 다툼.<br>• 21:20~21:45 : 복도 끝 화장실에서 담배를 피움.<br>• 21:45~22:00 : 로비에서 이주치의를 마주치고 인사함.",
                    secret: "회장의 비리를 협박하려고 최지배인 서랍에서 청산가리 병을 몰래 훔쳤으나, 겁이 나서 1층 쓰레기통에 버렸습니다."
                },
                {
                    id: "choi", roleName: "최지배인 (총지배인)",
                    alibi: "• 21:00~21:15 : VIP룸에 와인을 배달함.<br>• 21:15~21:40 : 2층 비상계단을 서성이다 누군가 계단을 올라가는 발소리를 들음.<br>• 21:40~22:00 : 프런트 카운터로 복귀.",
                    secret: "공금 유용 장부를 빼돌리기 위해 비상계단으로 몰래 들어가 회장의 서랍 속 장부만 도둑질해 나왔습니다."
                },
                {
                    id: "lee", roleName: "이주치의 (전담의사)",
                    alibi: "• 21:00~21:10 : 회장에게 혈압약을 전달함.<br>• 21:10~21:45 : 개인 객실에서 불안하게 전화 통화를 함.<br>• 21:45~22:00 : 로비에서 박파트너를 목격함.",
                    secret: "회장의 협박에 지쳐 약상자에 독약 캡슐을 몰래 만들어 두었으나, 차마 쓰지 못하고 방에 놔두고 나왔습니다."
                },
                {
                    id: "kang", roleName: "강배우자 (회장 아내)",
                    alibi: "• 21:00~21:30 : 비를 피하며 우산을 쓰고 해변 산책.<br>• 21:30~21:50 : VIP룸 근처 복도를 서성임.<br>• 21:50~22:00 : 개인 객실로 복귀.",
                    secret: "유언장을 훔치러 갔다가 이주치의가 두고 간 독약 캡슐을 발견하고, 회장의 와인 잔 입구에 캡슐 가루를 바르고 탈출했습니다."
                }
            ],
            truth: {
                killerId: "kang",
                title: "범인: 강배우자 (아내)",
                story: "<b>[범행 동기]</b><br>자신을 배제한 유언장이 작성되었다는 소식을 듣고 살인을 결심했습니다.<br><br><b>[살해 수법 및 은폐]</b><br>21시 35분 유언장을 훔치러 들어갔다가 테이블 위 이주치의의 독약 캡슐을 발견, 와인 잔 입구에 바르고 유언장을 빼돌렸습니다. 박파트너가 버린 독약병 덕분에 다른 용의자들에게 혐의가 쏠렸습니다."
            }
        },
        {
            title: "❄️ 설산 산장 밀실 살인사건",
            overview: "<b>폭설로 고립된 산장 1층에서 산장 주인이 머리에 둔기를 맞고 숨졌습니다.</b><br>정전이 일어났던 짧은 순간 용의자들의 행적이 엇갈렸습니다.",
            characters: [
                {
                    id: "kim", roleName: "김산악 (구조대원)",
                    alibi: "• 22:00~22:30 : 야외 창고에서 제설 장비 점검.<br>• 22:30~22:45 : 2층 복도에서 둔탁한 '쿵' 소리를 들음.<br>• 22:45~23:00 : 휴게실에서 홀로 차를 마심.",
                    secret: "주인과 따지려고 피 묻은 등산 스틱을 들고 갔으나 이미 쓰러져 있어 당황해 스틱을 난로 뒤에 떨구고 도망쳤습니다."
                },
                {
                    id: "lee_doc", roleName: "이약사 (손님)",
                    alibi: "• 22:00~22:40 : 1층 서재에서 독서.<br>• 22:40~22:50 : 화장실에 다녀오며 꺼져가는 난로 불을 봄.<br>• 22:50~23:00 : 방으로 복귀.",
                    secret: "차용증을 빼돌리기 위해 주인이 마시던 차에 수면제를 탔고, 주인이 재워지자 난로에 차용증만 태우고 나왔습니다."
                },
                {
                    id: "park_sub", roleName: "박알바 (스태프)",
                    alibi: "• 22:00~22:20 : 주방 정리.<br>• 22:20~22:50 : 와인 창고 재고 조사 중 고성을 들음.<br>• 22:50~23:00 : 쓰레기를 치우고 방으로 이동.",
                    secret: "억울하게 해고당한 분노로 와인 창고의 두꺼운 와인병을 가져와, 수면제에 잠든 주인의 머리를 내려쳐 살해했습니다."
                },
                {
                    id: "choi_pro", roleName: "최프로 (선수)",
                    alibi: "• 22:00~22:35 : 2층 재활실에서 운동.<br>• 22:35~22:50 : 거실 난로 앞에서 주인과 대화.<br>• 22:50~23:00 : 방으로 복귀.",
                    secret: "도핑 폭로 문제로 주인과 다투다 밀쳐 난로 모서리에 머리를 부딪히게 만들고 놀라 도망쳤습니다. (이때 주인은 기절만 함)"
                }
            ],
            truth: {
                killerId: "park_sub",
                title: "범인: 박알바 (스태프)",
                story: "<b>[범행 동기]</b><br>일방적인 해고와 폭언에 증오심이 폭발하여 살인을 저질렀습니다.<br><br><b>[살해 수법 및 은폐]</b><br>최프로에게 밀쳐지고 이약사의 수면제에 취해 쓰러져 있던 주인을 와인 창고의 묵직한 와인병으로 내려쳐 즉사시킨 뒤, 와인병을 창고 구석에 은닉했습니다."
            }
        }
    ];

    let currentScenario = null;
    let players = [];
    let assignedRoles = [];
    let currentIndex = 0;
    let isRevealed = false;

    function startOverviewStage() {
        const p1 = document.getElementById('p1').value.trim();
        const p2 = document.getElementById('p2').value.trim();
        const p3 = document.getElementById('p3').value.trim();
        const p4 = document.getElementById('p4').value.trim();

        if (!p1 || !p2 || !p3 || !p4) {
            alert('4명의 용의자 이름을 모두 입력하세요.');
            return;
        }

        players = [p1, p2, p3, p4];
        const scenarioIdx = document.getElementById('scenario-select').value;
        currentScenario = scenarioDatabase[scenarioIdx];

        document.getElementById('game-title').innerText = currentScenario.title;
        document.getElementById('overview-detail-box').innerHTML = `
            <div class="story-title">📌 사건 배경 및 개요</div>
            ${currentScenario.overview}
        `;

        // 역할 무작위 지정 (1명만 범인)
        const killerIndex = Math.floor(Math.random() * 4);
        assignedRoles = currentScenario.characters.map((char, index) => ({
            ...char,
            isKiller: char.id === currentScenario.truth.killerId
        }));
        assignedRoles.sort(() => Math.random() - 0.5);

        document.getElementById('setup-screen').classList.add('hidden');
        document.getElementById('overview-screen').classList.remove('hidden');
    }

    function startRoleAssignmentStage() {
        currentIndex = 0;
        document.getElementById('overview-screen').classList.add('hidden');
        document.getElementById('role-screen').classList.remove('hidden');
        updateTurn();
    }

    function updateTurn() {
        isRevealed = false;
        document.getElementById('current-player-display').innerText = `👤 ${players[currentIndex]} 님의 차례 (${currentIndex + 1}/4)`;
        document.getElementById('card-prompt').classList.remove('hidden');
        document.getElementById('card-content').classList.add('hidden');
        document.getElementById('next-btn').classList.add('hidden');

        const prevBtn = document.getElementById('prev-player-btn');
        if (currentIndex === 0) {
            prevBtn.style.display = 'none';
        } else {
            prevBtn.style.display = 'block';
        }
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
                killerStatus.innerHTML = '<div class="is-killer">🚨 당신은 범인입니다!</div>';
            } else {
                killerStatus.innerHTML = '<div class="is-innocent">🟢 무고한 용의자입니다.</div>';
            }

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
            // 모든 확인 종료 -> 사건의 전말 해설로 이동
            document.getElementById('role-screen').classList.add('hidden');
            document.getElementById('truth-screen').classList.remove('hidden');
            
            const killerPlayerIdx = assignedRoles.findIndex(r => r.isKiller);
            const killerName = players[killerPlayerIdx];

            document.getElementById('truth-killer-title').innerText = `🩸 ${currentScenario.truth.title} (플레이어: ${killerName})`;
            document.getElementById('truth-content-box').innerHTML = currentScenario.truth.story;
        }
    }

    function prevPlayer() {
        if (currentIndex > 0) {
            currentIndex--;
            updateTurn();
        }
    }

    function resetToHome() {
        document.getElementById('role-screen').classList.add('hidden');
        document.getElementById('overview-screen').classList.add('hidden');
        document.getElementById('truth-screen').classList.add('hidden');
        document.getElementById('setup-screen').classList.remove('hidden');
        document.getElementById('game-title').innerText = "👾 CRIMESCENE 👾";
    }
</script>

</body>
</html>
