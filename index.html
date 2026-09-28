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
            line-height: 1.6;
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
        .btn-yellow { background-color: #f1e05a; color: #000; }
        .btn-green { background-color: #2ed573; color: #000; }
        .btn-purple { background-color: #9b59b6; color: #fff; }

        .hidden { display: none !important; }

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
            padding: 12px;
            border: 2px solid #3a3f58;
            font-size: 0.85rem;
            line-height: 1.6;
            margin-top: 8px;
        }
        .info-block strong { color: #70a1ff; }
        .secret-text { color: #ff7b72; font-weight: bold; }

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
        .btn-row button { flex: 1; }

        /* 투표 버튼 스타일 */
        .vote-btn {
            background-color: #2a2e45;
            color: #fff;
            border: 2px solid #70a1ff;
            padding: 10px;
            margin-bottom: 8px;
            text-align: left;
            width: 100%;
            cursor: pointer;
            font-size: 0.9rem;
        }
        .vote-btn:hover {
            background-color: #70a1ff;
            color: #000;
        }
        .vote-btn.selected {
            background-color: #ff4757;
            color: #fff;
            border-color: #fff;
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
                <option value="0">❄️ 1. 설산 산장 밀실 살인사건</option>
                <option value="1">🩸 2. 블루비치 VIP룸 독살사건</option>
            </select>
        </div>

        <div class="input-group"><label>용의자 1</label><input type="text" id="p1" value="철수"></div>
        <div class="input-group"><label>용의자 2</label><input type="text" id="p2" value="영희"></div>
        <div class="input-group"><label>용의자 3</label><input type="text" id="p3" value="민수"></div>
        <div class="input-group"><label>용의자 4</label><input type="text" id="p4" value="지민"></div>

        <button class="btn-main" onclick="startOverviewStage()">▶ 사건 개요 보기</button>
    </div>

    <!-- 2단계: 사건 개요 및 현장 브리핑 -->
    <div id="overview-screen" class="hidden">
        <div class="story-box" id="overview-detail-box"></div>
        <p style="font-size:0.75rem; color:#a0a7c4; text-align:center;">💡 모든 플레이어가 사건 개요와 현장 단서를 함께 숙지해 주세요.</p>
        <button class="btn-main btn-green" onclick="startRoleAssignmentStage()">▶ 개별 비밀 프로필 확인 시작</button>
    </div>

    <!-- 3단계: 개별 역할 및 비밀 확인 화면 -->
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
                    <strong>[📜 내가 진술할 알리바이 스토리]</strong><br><span id="char-alibi"></span><br><br>
                    <strong>[🤫 나만의 은밀한 비밀]</strong><br><span id="char-secret" class="secret-text"></span>
                </div>
            </div>
        </div>

        <p style="font-size:0.75rem; color:#a0a7c4; text-align:center; margin-bottom:8px;">확인 후 카드 영역을 다시 터치하여 화면을 숨겨주세요.</p>
        <div class="btn-row">
            <button id="prev-player-btn" onclick="prevPlayer()" class="btn-main btn-yellow">◀ 이전 사람</button>
            <button id="next-btn" onclick="nextPlayer()" class="btn-main hidden">다음 사람 ▶</button>
        </div>
    </div>

    <!-- 4단계: 투표하기 화면 -->
    <div id="vote-screen" class="hidden">
        <div class="story-box">
            <div class="story-title">🗳️ 범인 지목 투표</div>
            모든 알리바이와 단서 확인이 끝났습니다. 플레이어들끼리 자유롭게 토론한 뒤, 범인이라고 생각하는 사람을 지목하세요!
        </div>
        <div id="vote-options"></div>
        <button class="btn-main btn-purple" id="reveal-truth-btn" onclick="goToTruthScreen()" style="margin-top:15px;">🔓 사건의 전말 확인하기</button>
    </div>

    <!-- 5단계: 사건의 전말 공개 -->
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
            title: "❄️ 설산 산장 밀실 살인사건",
            overview: "<b>폭설로 고립된 산장 거실에서 산장 주인이 머리에 둔기를 맞고 숨진 채 발견되었습니다.</b><br><br>" +
                      "<b>🔍 현장 브리핑 단서:</b><br>" +
                      "1. 피해자의 상의 옷깃이 길게 찢어져 있었습니다.<br>" +
                      "2. 난로 속에서 다 타지 않은 <b>'가죽 장갑 조각'</b>이 발견되었습니다.<br>" +
                      "3. 주방의 <b>기름때 전용 강력 세제</b>가 바닥에 흘려져 있었습니다.<br>" +
                      "4. 피해자 머리의 정수리 부근에 네모나고 평평한 함몰 상처가 남아있습니다.",
            characters: [
                {
                    id: "kim", roleName: "김구조 (산악구조대원)",
                    alibi: "밤 10시쯤 눈보라가 심해져 창고에서 제설 장비를 점검하고 있었습니다. 10시 반쯤 2층 복도를 지나는데 아래층에서 뭔가 거칠게 다투는 소리와 '북' 하고 옷감 찢어지는 소리가 났습니다. 무서워서 내려가지 못하고 2층 방에서 숨죽이고 있었습니다.",
                    secret: "주인의 거칠었던 폭언에 화가 나 등산 스틱을 들고 내려갔으나, 이미 사체가 되어 있는 주인을 보고 놀라 등산 스틱만 쥔 채 도로 방으로 도망쳤습니다."
                },
                {
                    id: "lee_doc", roleName: "이약사 (산장 투숙객)",
                    alibi: "밤 10시 40분쯤 차를 마시러 1층 서재로 내려왔습니다. 난로 불이 희미해져 있길래 장작을 몇 개 더 던져 넣었고, 화장실에 잠시 들렀다가 곧바로 방으로 돌아가 잠에 들었습니다.",
                    secret: "주인에게 잡힌 거액의 차용증을 태우기 위해 난로에 서류를 던지던 중, 난로 열기에 가죽 장갑 한쪽이 타버려 급히 떼어내느라 탄 조각을 난로에 남겼습니다."
                },
                {
                    id: "park_sub", roleName: "박알바 (산장 스태프)",
                    alibi: "밤 10시부터 주방에서 내일 아침 재료를 손질하고 있었습니다. 10시 50분쯤 산장 전체가 순간 정전되었고, 두꺼비집을 올려 전기를 복구한 뒤 쓰레기를 버리고 방으로 올라갔습니다.",
                    secret: "주인의 억울한 해고 통보에 증오심이 폭발하여, 주방에 있던 묵직한 네모 모양 무쇠 프라이팬으로 쓰러져 있던 주인의 머리를 내려쳤습니다."
                },
                {
                    id: "choi_pro", roleName: "최선수 (전 프로선수)",
                    alibi: "밤 10시 30분쯤 거실 난로 앞에서 주인과 대화를 나누었습니다. 대화 도중 약간의 언성이 높아지긴 했으나 금방 사과하고 10시 45분쯤 2층 제 방으로 올라왔습니다.",
                    secret: "도핑 폭로 문제로 주인과 멱살잡이를 하다 옷깃을 찢었고, 주인을 밀쳐 난로 모서리에 머리를 부딪혀 기절하게 만들었습니다. 죽은 줄 알고 놀라 도망쳤으나 시점엔 살아있었습니다."
                }
            ],
            truth: {
                killerId: "park_sub",
                title: "진범: 박알바 (산장 스태프)",
                story: "<b>[사건의 전말 & 코난식 트릭 풀이]</b><br><br>" +
                       "1. <b>상처의 비밀</b>: 최선수가 멱살을 잡고 밀쳐 난로 모서리에 머리를 부딪힌 주인은 기절만 했을 뿐 살아있었습니다.<br><br>" +
                       "2. <b>스태프의 범행</b>: 기절한 주인을 발견한 박알바는 복수심에 주방의 <b>네모난 무쇠 프라이팬</b>으로 머리를 찍어 살해했습니다. (네모난 함몰 상처의 원인)<br><br>" +
                       "3. <b>은폐 시도와 허점</b>: 프라이팬에 피와 주방 기름때가 엉키자 강력 세제로 급하게 세척하다 바닥에 흘렸고, 무쇠팬을 아무렇지 않게 주방에 다시 가져다 놓았습니다!"
            }
        },
        {
            title: "🩸 블루비치 VIP룸 독살사건",
            overview: "<b>해변 리조트 VIP룸에서 회장이 와인을 마시던 중 독살당했습니다.</b><br><br>" +
                      "<b>🔍 현장 브리핑 단서:</b><br>" +
                      "1. 와인 잔 입구 부근에 희미한 캡슐 가루 자국이 남아있습니다.<br>" +
                      "2. 1층 쓰레기통에서 청산가리가 담겼던 빈 약병이 발견되었습니다.<br>" +
                      "3. 회장의 서랍장이 열려있었으나 비리 장부만 사라져 있었습니다.",
            characters: [
                {
                    id: "park", roleName: "박파트너 (동업자)",
                    alibi: "밤 9시쯤 회장실에서 매각 문제로 크게 다투고 나왔습니다. 화가 나서 복도 화장실에서 담배를 피우며 마음을 가라앉힌 뒤, 로비로 내려와 이주치의와 인사를 나누었습니다.",
                    secret: "회장을 협박하려 최지배인 서랍에서 청산가리 병을 몰래 훔쳤으나, 막상 죽일 용기가 안 나 1층 쓰레기통에 버렸습니다."
                },
                {
                    id: "choi", roleName: "최지배인 (총지배인)",
                    alibi: "9시 15분쯤 VIP룸에 부탁받은 와인을 배달했습니다. 이후 비상계단 부근을 청소하다 계단을 서둘러 올라가는 발소리를 들었습니다.",
                    secret: "자신의 공금 유용 장부를 빼돌리기 위해 비상계단으로 몰래 침입해 회장 서랍의 장부만 도둑질해 나왔습니다."
                },
                {
                    id: "lee", roleName: "이주치의 (전담의사)",
                    alibi: "9시쯤 회장에게 혈압약을 전달한 뒤 개인 객실로 돌아왔습니다. 9시 45분쯤 로비로 내려가다 박파트너를 만났습니다.",
                    secret: "회장의 협박에 지쳐 독약 캡슐을 몰래 만들어 두었으나 차마 쓰지 못하고 회장 방 테이블 위에 놔두고 나왔습니다."
                },
                {
                    id: "kang", roleName: "강배우자 (회장 아내)",
                    alibi: "9시 30분쯤 비를 피하며 해변 산책을 하다가 VIP룸 복도를 잠시 서성였고, 9시 50분쯤 객실로 돌아왔습니다.",
                    secret: "유언장을 훔치러 갔다가 이주치의가 두고 간 독약 캡슐을 발견, 와인 잔 입구에 캡슐 가루를 바르고 탈출했습니다."
                }
            ],
            truth: {
                killerId: "kang",
                title: "진범: 강배우자 (아내)",
                story: "<b>[사건의 전말 & 코난식 트릭 풀이]</b><br><br>" +
                       "1. <b>독약의 출처</b>: 이주치의가 미처 챙기지 못하고 테이블에 둔 독약 캡슐을 본 강배우자가 와인 잔 입구에 발라 독살했습니다.<br><br>" +
                       "2. <b>교란 작전</b>: 박파트너가 버린 청산가리 병 때문에 경찰의 수사선상이 청산가리로 쏠렸으나, 실제 독극물은 이주치의의 독약 캡슐이었습니다!"
            }
        }
    ];

    let currentScenario = null;
    let players = [];
    let assignedRoles = [];
    let currentIndex = 0;
    let isRevealed = false;
    let selectedSuspectIndex = null;

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

        assignedRoles = currentScenario.characters.map((char) => ({
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
        prevBtn.style.display = currentIndex === 0 ? 'none' : 'block';
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

            document.getElementById('char-alibi').innerText = role.alibi;
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
            // 모든 확인 종료 -> 투표 화면 이동
            startVoteStage();
        }
    }

    function prevPlayer() {
        if (currentIndex > 0) {
            currentIndex--;
            updateTurn();
        }
    }

    function startVoteStage() {
        document.getElementById('role-screen').classList.add('hidden');
        document.getElementById('vote-screen').classList.remove('hidden');

        const voteOptionsBox = document.getElementById('vote-options');
        voteOptionsBox.innerHTML = '';

        players.forEach((playerName, idx) => {
            const role = assignedRoles[idx];
            const btn = document.createElement('button');
            btn.className = 'vote-btn';
            btn.innerHTML = `👉 <b>${playerName}</b> (${role.roleName})`;
            btn.onclick = () => selectSuspect(idx, btn);
            voteOptionsBox.appendChild(btn);
        });
    }

    function selectSuspect(idx, btnElement) {
        selectedSuspectIndex = idx;
        const allBtns = document.querySelectorAll('.vote-btn');
        allBtns.forEach(b => b.classList.remove('selected'));
        btnElement.classList.add('selected');
    }

    function goToTruthScreen() {
        document.getElementById('vote-screen').classList.add('hidden');
        document.getElementById('truth-screen').classList.remove('hidden');

        const killerPlayerIdx = assignedRoles.findIndex(r => r.isKiller);
        const killerPlayerName = players[killerPlayerIdx];
        const killerRole = assignedRoles[killerPlayerIdx];

        document.getElementById('truth-killer-title').innerHTML = `🕵️‍♂️ ${currentScenario.truth.title}<br><span style="color:#fff; font-size:0.9rem;">(지목된 지목 대상 / 진짜 범인: ${killerPlayerName})</span>`;
        document.getElementById('truth-content-box').innerHTML = currentScenario.truth.story;
    }

    function resetToHome() {
        document.getElementById('role-screen').classList.add('hidden');
        document.getElementById('overview-screen').classList.add('hidden');
        document.getElementById('vote-screen').classList.add('hidden');
        document.getElementById('truth-screen').classList.add('hidden');
        document.getElementById('setup-screen').classList.remove('hidden');
        document.getElementById('game-title').innerText = "👾 CRIMESCENE 👾";
    }
</script>

</body>
</html>
