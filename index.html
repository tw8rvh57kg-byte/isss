<!DOCTYPE html>
<html lang="ko">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>CRIMESCENE : PIXEL MYSTERY</title>
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
        .nav-btn:hover { color: #fff; border-color: #ff4757; }

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
        .story-title { font-weight: bold; color: #f1e05a; margin-bottom: 6px; }

        .input-group { margin-bottom: 8px; }
        label { display: block; margin-bottom: 3px; font-size: 0.8rem; color: #a0a7c4; }
        input, select {
            width: 100%;
            padding: 8px;
            border: 3px solid #3a3f58;
            background-color: #0d0e15;
            color: #fff;
            font-size: 0.88rem;
            outline: none;
        }
        input:focus, select:focus { border-color: #ff4757; }

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
        button.btn-main:active { transform: translate(2px, 2px); box-shadow: 0 0 0 #000; }

        /* 색상 명확화 된 버튼들 */
        .btn-prev { background-color: #f1e05a !important; color: #000 !important; } /* 이전: 노란색 */
        .btn-next { background-color: #2ed573 !important; color: #000 !important; } /* 다음: 초록색 */
        .btn-purple { background-color: #9b59b6 !important; color: #fff !important; }

        .hidden { display: none !important; }

        .card {
            background: #212538;
            border: 3px dashed #ff4757;
            padding: 18px 14px;
            margin: 14px 0;
            text-align: center;
            cursor: pointer;
            user-select: none;
            min-height: 240px;
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
            color: #ff4757; font-weight: bold; background: #3c1e1e;
            padding: 4px 8px; border: 1px solid #ff4757; display: inline-block; margin-bottom: 6px; font-size: 0.8rem;
        }
        .is-innocent {
            color: #2ed573; font-weight: bold; background: #1e3c23;
            padding: 4px 8px; border: 1px solid #2ed573; display: inline-block; margin-bottom: 6px; font-size: 0.8rem;
        }

        /* 버튼 고정 컨트롤러 레이아웃 */
        .fixed-btn-row {
            display: flex;
            gap: 10px;
            margin-top: 10px;
        }
        .fixed-btn-row button {
            flex: 1;
            margin-top: 0;
        }

        .timeline-item {
            margin-bottom: 8px;
            padding-bottom: 6px;
            border-bottom: 1px dashed #2a2e45;
        }
        .timeline-time { color: #f1e05a; font-weight: bold; }
    </style>
</head>
<body>

<div class="outer-nav">
    <button class="nav-btn" onclick="resetToHome()">🏠 처음으로</button>
</div>

<div class="container">
    <div class="pixel-header" id="game-title">👾 CRIMESCENE 👾</div>

    <!-- 1단계: 설정 화면 -->
    <div id="setup-screen">
        <div class="story-box">
            <div class="story-title">🎮 사건 및 인원 설정</div>
            플레이 인원(4~6명)과 사건 테마를 선택하고 각 플레이어의 이름을 입력해 주세요!
        </div>

        <div class="input-group">
            <label>사건 배경 테마</label>
            <select id="theme-select">
                <option value="snow">🏔️ 1. 설산 산장 밀실 살인사건</option>
                <option value="beach">🌊 2. 해변 VIP룸 독살사건</option>
                <option value="gallery">🎨 3. 미술관 고성 살인사건</option>
            </select>
        </div>

        <div class="input-group">
            <label>플레이 인원 수</label>
            <select id="player-count-select" onchange="renderPlayerInputs()">
                <option value="4" selected>4명</option>
                <option value="5">5명</option>
                <option value="6">6명</option>
            </select>
        </div>

        <div id="player-inputs-container"></div>

        <button class="btn-main" onclick="generateAndStartOverview()">▶ 랜덤 사건 생성 & 개요 보기</button>
    </div>

    <!-- 2단계: 사건 개요 -->
    <div id="overview-screen" class="hidden">
        <div class="story-box" id="overview-detail-box"></div>
        <p style="font-size:0.75rem; color:#a0a7c4; text-align:center;">💡 단서와 사건 개요를 모두 함께 정독해 주세요.</p>
        <button class="btn-main btn-next" onclick="startRoleAssignmentStage()">▶ 개별 역할 및 비밀 확인 시작</button>
    </div>

    <!-- 3단계: 개별 프로필 확인 (이전/다음 고정 버튼) -->
    <div id="role-screen" class="hidden">
        <h3 id="current-player-display" style="text-align:center; color:#70a1ff; margin:0 0 8px 0;"></h3>
        
        <div class="card" id="role-card" onclick="toggleRole()">
            <div id="card-prompt">
                🔍 <strong>[터치하여 나만의 역할 & 스토리 확인]</strong>
            </div>
            
            <div id="card-content" class="hidden">
                <div id="char-name" style="font-size:1.1rem; font-weight:bold; color:#f1e05a; margin-bottom:6px;"></div>
                <div id="killer-status"></div>
                
                <div class="info-block">
                    <strong>[📜 시간대별 감정선 스토리 알리바이]</strong><br><br>
                    <div id="char-alibi-list"></div><br>
                    <strong>[🤫 나만의 은밀한 비밀]</strong><br>
                    <span id="char-secret" class="secret-text"></span>
                </div>
            </div>
        </div>

        <p style="font-size:0.75rem; color:#a0a7c4; text-align:center; margin-bottom:8px;">확인 후 카드를 한 번 더 터치해 화면을 숨겨주세요.</p>
        
        <!-- 이전/다음 고정 위치 버튼 -->
        <div class="fixed-btn-row">
            <button id="prev-btn" onclick="prevPlayer()" class="btn-main btn-prev">◀ 이전</button>
            <button id="next-btn" onclick="nextPlayer()" class="btn-main btn-next">다음 ▶</button>
        </div>
    </div>

    <!-- 4단계: 자유 토론 시간 안내문 -->
    <div id="discussion-screen" class="hidden">
        <div class="story-box" style="border-left-color:#2ed573;">
            <div class="story-title" style="color:#2ed573; font-size:1.1rem; text-align:center;">🗣️ 자유 토론 타임</div>
            <hr style="border-color:#3a3f58; margin:10px 0;">
            모든 용의자가 자신만의 비밀 프로필을 확인했습니다!<br><br>
            • 각자 자신의 시간대별 알리바이를 말하며 진범을 추리하세요.<br>
            • 단, <b>자신의 은밀한 비밀</b>은 질문을 받으면 적절히 얼버무리거나 숨길 수 있습니다.<br>
            • 진범은 들키지 않도록 거짓말과 변명을 능숙하게 늘어놓아야 합니다.<br><br>
            <b>충분히 토론한 후, 아래 버튼을 눌러 사건의 전말을 확인하세요!</b>
        </div>
        <button class="btn-main btn-purple" onclick="goToTruthScreen()">🔓 사건의 전말 & 진범 공개</button>
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
    // 역할/동기/비밀 데이터베이스 (무한 생성용 재료)
    const rolePool = [
        { title: "비서", secret: "피해자의 비리 서랍을 열어 장부를 도둑질하다 소리에 놀라 도망쳤습니다." },
        { title: "의사", secret: "피해자의 협박에 독약 캡슐을 만들어두었으나 소심해서 쓰지 못하고 놔두었습니다." },
        { title: "배우자", secret: "자신을 배제한 유언장을 고치려다 실패하고 홧김에 테이블 위 약을 타버렸습니다." },
        { title: "동업자", secret: "협박용으로 청산가리를 훔쳐 왔으나 막상 죽일 용기가 없어 쓰레기통에 버렸습니다." },
        { title: "스태프", secret: "해고 통보에 눈이 뒤집혀 주방 무쇠 팬으로 기절해 있던 피해자를 내려쳤습니다." },
        { title: "라이벌", secret: "말다툼 끝에 피해자를 난로 모서리로 밀쳐 기절하게 만들고 무서워서 도망쳤습니다." }
    ];

    const emotions = ["분노와 수치심에 손이 떨렸고", "불안한 마음에 심장이 터질 듯 뛰어", "초조함에 연신 식은땀을 흘리며", "어떻게든 상황을 피하고 싶어"];

    let players = [];
    let generatedStory = null;
    let assignedRoles = [];
    let currentIndex = 0;
    let isRevealed = false;

    function renderPlayerInputs() {
        const count = parseInt(document.getElementById('player-count-select').value);
        const container = document.getElementById('player-inputs-container');
        container.innerHTML = '';
        
        const defaultNames = ["철수", "영희", "민수", "지민", "훈이", "유리"];
        for (let i = 0; i < count; i++) {
            container.innerHTML += `
                <div class="input-group">
                    <label>용의자 ${i + 1}</label>
                    <input type="text" id="p${i+1}" value="${defaultNames[i]}">
                </div>
            `;
        }
    }
    renderPlayerInputs();

    function generateAndStartOverview() {
        const count = parseInt(document.getElementById('player-count-select').value);
        players = [];
        for (let i = 1; i <= count; i++) {
            const name = document.getElementById(`p${i}`).value.trim();
            if (!name) { alert('모든 용의자의 이름을 입력해 주세요.'); return; }
            players.push(name);
        }

        const theme = document.getElementById('theme-select').value;
        const killerIdx = Math.floor(Math.random() * count);

        // 사건 무한 무작위 생성
        let themeTitle = "🏔️ 설산 산장 밀실 살인사건";
        if (theme === 'beach') themeTitle = "🌊 해변 VIP룸 독살사건";
        if (theme === 'gallery') themeTitle = "🎨 미술관 고성 살인사건";

        assignedRoles = players.map((name, i) => {
            const rData = rolePool[i % rolePool.length];
            const isKiller = (i === killerIdx);
            
            return {
                playerName: name,
                roleTitle: rData.title,
                isKiller: isKiller,
                alibi: [
                    { time: "21:00 ~ 21:20", text: `${emotions[i % 4]} 피해자의 방 근처를 지나는 모습이 목격되었습니다.` },
                    { time: "21:20 ~ 21:45", text: `상황이 악화될까 봐 복도 구석에서 숨죽이며 주변 정황을 살폈습니다.` },
                    { time: "21:45 ~ 22:00", text: `서둘러 자신의 방으로 돌아와 마음을 가라앉히려 애썼습니다.` }
                ],
                secret: isKiller ? `[진범] 결정적 순간 우발적 충동으로 치명적인 범행을 저지른 후 범행 도구를 현장에 은닉했습니다.` : rData.secret
            };
        });

        // 사건 개요 및 전말 세팅
        generatedStory = {
            title: themeTitle,
            overview: `<b>${themeTitle}</b><br>피해자가 서재에서 차가운 사체로 발견되었습니다.<br>용의자 ${count}명 모두 사건 시각 근처에서 각자의 의문스러운 행동과 감정적 갈등을 겪었습니다.`,
            killerName: players[killerIdx],
            killerRole: assignedRoles[killerIdx].roleTitle
        };

        document.getElementById('game-title').innerText = generatedStory.title;
        document.getElementById('overview-detail-box').innerHTML = `
            <div class="story-title">📌 사건 배경 브리핑</div>
            ${generatedStory.overview}
        `;

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
        document.getElementById('current-player-display').innerText = `👤 ${players[currentIndex]} 님의 차례 (${currentIndex + 1}/${players.length})`;
        document.getElementById('card-prompt').classList.remove('hidden');
        document.getElementById('card-content').classList.add('hidden');

        // 버튼 상태 조정
        const prevBtn = document.getElementById('prev-btn');
        const nextBtn = document.getElementById('next-btn');

        if (currentIndex === 0) {
            prevBtn.style.opacity = '0.4';
            prevBtn.disabled = true;
        } else {
            prevBtn.style.opacity = '1';
            prevBtn.disabled = false;
        }

        if (currentIndex === players.length - 1) {
            nextBtn.innerText = "토론 시작 ▶";
        } else {
            nextBtn.innerText = "다음 ▶";
        }
    }

    function toggleRole() {
        const cardPrompt = document.getElementById('card-prompt');
        const cardContent = document.getElementById('card-content');

        if (!isRevealed) {
            const role = assignedRoles[currentIndex];
            document.getElementById('char-name').innerText = `${role.playerName} (${role.roleTitle})`;
            
            const killerStatus = document.getElementById('killer-status');
            killerStatus.innerHTML = role.isKiller 
                ? '<div class="is-killer">🚨 당신이 진범입니다! 범행을 숨기세요.</div>' 
                : '<div class="is-innocent">🟢 당신은 무고한 용의자입니다.</div>';

            const alibiBox = document.getElementById('char-alibi-list');
            alibiBox.innerHTML = role.alibi.map(a => `
                <div class="timeline-item">
                    <span class="timeline-time">[${a.time}]</span><br>${a.text}
                </div>
            `).join('');

            document.getElementById('char-secret').innerText = role.secret;

            cardPrompt.classList.add('hidden');
            cardContent.classList.remove('hidden');
            isRevealed = true;
        } else {
            cardPrompt.classList.remove('hidden');
            cardContent.classList.add('hidden');
            isRevealed = false;
        }
    }

    function nextPlayer() {
        if (currentIndex < players.length - 1) {
            currentIndex++;
            updateTurn();
        } else {
            // 토론 안내 화면 이동
            document.getElementById('role-screen').classList.add('hidden');
            document.getElementById('discussion-screen').classList.remove('hidden');
        }
    }

    function prevPlayer() {
        if (currentIndex > 0) {
            currentIndex--;
            updateTurn();
        }
    }

    function goToTruthScreen() {
        document.getElementById('discussion-screen').classList.add('hidden');
        document.getElementById('truth-screen').classList.remove('hidden');

        document.getElementById('truth-killer-title').innerText = `🕵️‍♂️ 사건의 진범: ${generatedStory.killerName} (${generatedStory.killerRole})`;
        document.getElementById('truth-content-box').innerHTML = `
            <b>[범행 전말]</b><br>
            진범인 <b>${generatedStory.killerName}</b>은 감정을 주체하지 못하고 치명적인 단서를 남긴 채 범행을 저지르고 말았습니다.<br><br>
            자신의 감정과 알리바이를 교묘하게 속이고 추리를 성공적으로 교란시켰는지 확인해보세요!
        `;
    }

    function resetToHome() {
        document.getElementById('role-screen').classList.add('hidden');
        document.getElementById('overview-screen').classList.add('hidden');
        document.getElementById('discussion-screen').classList.add('hidden');
        document.getElementById('truth-screen').classList.add('hidden');
        document.getElementById('setup-screen').classList.remove('hidden');
        document.getElementById('game-title').innerText = "👾 CRIMESCENE 👾";
    }
</script>

</body>
</html>
