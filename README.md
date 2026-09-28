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

        /* 네비게이션 버튼 영역 (상단) */
        .outer-nav {
            max-width: 520px;
            width: 100%;
            display: flex;
            justify-content: flex-end;
            margin-bottom: 12px;
        }
        .nav-btn {
            background-color: #1e2230;
            color: #8c9ba5;
            border: 2px solid #3a4259;
            padding: 8px 16px;
            font-size: 0.85rem;
            cursor: pointer;
            box-shadow: 2px 2px 0px #000;
            transition: all 0.1s;
        }
        .nav-btn:hover {
            background-color: #2a3045;
            color: #fff;
        }

        /* 메인 컨테이너 카드 */
        .card-container {
            max-width: 520px;
            width: 100%;
            background-color: #181b26;
            border: 4px solid #3a4259;
            box-shadow: 6px 6px 0px #000;
            padding: 24px;
            position: relative;
        }

        h1.title {
            font-size: 1.25rem;
            text-align: center;
            color: #ff5555;
            margin-top: 0;
            margin-bottom: 8px;
            text-shadow: 2px 2px 0px #000;
        }

        .subtitle {
            font-size: 1.1rem;
            text-align: center;
            color: #55ffff;
            margin-bottom: 20px;
            font-weight: bold;
        }

        /* 터치 및 프로필 영역 */
        .secret-box {
            background-color: #0f111a;
            border: 2px dashed #ff5555;
            padding: 20px;
            text-align: center;
            cursor: pointer;
            min-height: 240px;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            user-select: none;
            transition: background-color 0.2s;
        }
        .secret-box:hover {
            background-color: #141724;
        }

        .click-hint {
            color: #ffff55;
            font-size: 1rem;
            font-weight: bold;
            line-height: 1.5;
        }

        .profile-content {
            display: none;
            text-align: left;
            width: 100%;
        }

        .role-badge {
            display: inline-block;
            padding: 4px 8px;
            font-size: 0.85rem;
            font-weight: bold;
            color: #000;
            background-color: #ffb86c;
            margin-bottom: 12px;
            border: 1px solid #000;
        }
        .role-badge.killer {
            background-color: #ff5555;
            color: #fff;
        }

        .info-group {
            margin-bottom: 12px;
            font-size: 0.92rem;
            line-height: 1.5;
        }
        .info-label {
            color: #8be9fd;
            font-weight: bold;
        }

        /* 하단 안내 및 컨트롤 버튼 */
        .bottom-guide {
            font-size: 0.8rem;
            color: #6272a4;
            text-align: center;
            margin-top: 16px;
            margin-bottom: 16px;
        }

        .action-btn {
            width: 100%;
            background-color: #f1fa8c;
            color: #000;
            border: 3px solid #000;
            padding: 14px;
            font-size: 1rem;
            font-weight: bold;
            cursor: pointer;
            box-shadow: 4px 4px 0px #000;
            transition: transform 0.05s, box-shadow 0.05s;
        }
        .action-btn:active {
            transform: translate(2px, 2px);
            box-shadow: 2px 2px 0px #000;
        }

        .btn-group {
            display: flex;
            gap: 10px;
        }

        /* 사건 진실 스타일 */
        .truth-text {
            font-size: 0.88rem;
            line-height: 1.6;
            color: #f8f8f2;
            background: #11131d;
            padding: 12px;
            border: 1px solid #44475a;
            max-height: 280px;
            overflow-y: auto;
        }
    </style>
</head>
<body>

    <!-- 상단 바: '처음으로' 버튼만 남김 -->
    <div class="outer-nav">
        <button class="nav-btn" onclick="resetGame()">🏠 처음으로</button>
    </div>

    <!-- 메인 네모 카드 -->
    <div class="card-container">
        <h1 class="title">❄️ 설산 산장 밀실 살인사건</h1>
        <div class="subtitle" id="step-title">👤 참자가 1 님의 차례 (1/4)</div>

        <!-- 카드 안의 비밀 프로필 박스 -->
        <div class="secret-box" id="secret-box" onclick="toggleSecret()">
            <div class="click-hint" id="click-hint">
                🔍 [터치하여 나만의 비밀 프로필 확인]
            </div>
            <div class="profile-content" id="profile-content">
                <!-- JS로 비밀 내용 삽입 -->
            </div>
        </div>

        <div class="bottom-guide">확인 후 카드 영역을 다시 터치하여 화면을 숨겨주세요.</div>

        <!-- 하단 노란색 컨트롤 버튼 -->
        <div id="button-area">
            <button class="action-btn" id="main-btn" onclick="nextPlayer()">다음 사람 ▶</button>
        </div>
    </div>

    <script>
        // 시나리오 데이터 정의
        const playersData = [
            {
                name: "참가자 1 (김의사)",
                role: "용의자 (무고함)",
                secret: "피해자인 한진태 대표가 병원 설립 자금을 미끼로 사기를 치려 한 정황을 포착하고, 사건 당일 밤 몰래 그의 서재에서 차용증과 장부를 수색하려 했습니다. 하지만 살인은 저지르지 않았으며, 그가 사망한 것을 보고 겁에 질려 아무것도 건드리지 못하고 도망쳐 나왔습니다.",
                alibi: "사건 시각 무렵, 서재 근처 복도에서 서성이며 기회를 노리고 있었습니다."
            },
            {
                name: "참가자 2 (이변호사)",
                role: "범인 (진범)",
                secret: "당신이 진범입니다! 피해자의 불법 비리를 폭로하려다 억울하게 파면당한 옛 동료의 가족입니다. 당신은 복수와 진실 은폐를 위해 한진태를 정교하게 살해했습니다.",
                alibi: "사건 시각 정전이 일어났을 때, 자신은 거실 피아노 옆에 그대로 서 있었다고 주장합니다."
            },
            {
                name: "참가자 3 (박회계)",
                role: "용의자 (무고함)",
                secret: "최근 투자 실패로 거액의 빚을 지고 한진태에게 자금 지원을 애원하러 왔습니다. 그러나 한진태가 자신을 모욕하며 거절하자 극심한 분노를 느꼈습니다. 하지만 살해할 담력은 없었으며, 사건 당일 밤 혼자 와인을 마시며 분을 삭이고 있었습니다.",
                alibi: "사건 시각 산장 2층 테라스에서 혼자 와인을 마시며 야경을 보고 있었습니다."
            },
            {
                name: "참가자 4 (최비서)",
                role: "용의자 (무고함)",
                secret: "회사 공금을 일부 유용하다 한진태에게 약점을 잡혀 지속적인 협박과 갑질을 당해왔습니다. 한진태가 죽어서 내심 속으로 다행이라 생각하지만, 그를 직접 죽이지는 않았습니다.",
                alibi: "사건 시각 주방에서 피해자의 밤샘 작업용 차를 끓이고 있었습니다."
            }
        ];

        const truthData = `
            <div class="truth-text">
                <b style="color:#ff5555;">[사건의 전말 및 동기]</b><br>
                범인은 <b>'이변호사'</b>입니다.<br>
                피해자 한진태는 과거 로펌 내 거대 비리를 덮기 위해 억울한 동료에게 죄를 뒤집어씌워 파면시키고 매장했습니다. 그 동료의 가족이었던 이변호사는 신분을 숨기고 접근하여 복수할 기회를 노려왔습니다.<br><br>

                <b style="color:#8be9fd;">[범행 수법 및 밀실 트릭]</b><br>
                1. <b>정전 공작</b>: 이변호사는 산장 뒤편의 두꺼비집에 미리 소금물 얼음 퓨즈를 설치하여 지정된 시각에 정전이 발생하도록 유도했습니다.<br>
                2. <b>살해 수법</b>: 산장의 극심한 추위를 이용해 밖에서 미리 만들어둔 <b>'얼음 송곳'</b>을 코트 속에 숨겨 들어갔습니다. 정전으로 순식간에 어두워진 틈을 타 서재로 이동, 피해자의 목을 정확히 찌르고 얼음 송곳을 현장에 방치했습니다.<br>
                3. <b>밀실 및 증거 은폐</b>: 얼음 송곳은 산장의 센 난로 열기에 의해 녹아 소멸되었으며, 문은 안쪽에서 걸어 잠긴 것처럼 보이도록 실과 고리를 이용한 레트로 물리 트릭을 사용했습니다. 손에 묻은 피는 알코올 소독 솜으로 닦아낸 뒤 난로 속으로 던져 완전히 태워버렸습니다.<br><br>

                <b style="color:#50fa7b;">[결정적 단서]</b><br>
                이변호사의 소매 끝에서 <b>녹은 얼음물에 젖은 흔적</b>과 난로 속에서 다 타지 않은 <b>알코올 솜의 합성섬유 재</b>가 발견되었습니다!
            </div>
        `;

        let currentIndex = 0;
        let isRevealed = false;

        function updateCard() {
            isRevealed = false;
            const secretBox = document.getElementById("secret-box");
            const clickHint = document.getElementById("click-hint");
            const profileContent = document.getElementById("profile-content");
            const stepTitle = document.getElementById("step-title");
            const mainBtn = document.getElementById("main-btn");
            const buttonArea = document.getElementById("button-area");

            // 마지막 단계 (사건의 진실)
            if (currentIndex >= playersData.length) {
                stepTitle.innerText = "🔍 사건의 진실 공개";
                clickHint.style.display = "none";
                profileContent.style.display = "block";
                profileContent.innerHTML = truthData;

                buttonArea.innerHTML = `
                    <button class="action-btn" onclick="resetGame()">🔄 게임 다시 시작하기</button>
                `;
                return;
            }

            // 일반 플레이어 단계
            const data = playersData[currentIndex];
            stepTitle.innerText = `👤 ${data.name} 님의 차례 (${currentIndex + 1}/${playersData.length})`;
            
            clickHint.style.display = "block";
            profileContent.style.display = "none";

            const isKiller = data.role.includes("범인");
            profileContent.innerHTML = `
                <span class="role-badge ${isKiller ? 'killer' : ''}">${data.role}</span>
                <div class="info-group">
                    <span class="info-label">🤫 당신만의 비밀:</span><br>${data.secret}
                </div>
                <div class="info-group">
                    <span class="info-label">🕰️ 주장하는 알리바이:</span><br>${data.alibi}
                </div>
            `;

            // 버튼 상태 제어 (첫 번째 사람일 때는 '이전 사람' 버튼 미표시)
            if (currentIndex === 0) {
                buttonArea.innerHTML = `
                    <button class="action-btn" onclick="nextPlayer()">다음 사람 ▶</button>
                `;
            } else {
                buttonArea.innerHTML = `
                    <div class="btn-group">
                        <button class="action-btn" style="background-color:#ffb86c;" onclick="prevPlayer()">◀ 이전 사람</button>
                        <button class="action-btn" onclick="nextPlayer()">다음 사람 ▶</button>
                    </div>
                `;
            }
        }

        function toggleSecret() {
            if (currentIndex >= playersData.length) return; // 진실 단계에서는 카드 터치 동작 안 함
            
            const clickHint = document.getElementById("click-hint");
            const profileContent = document.getElementById("profile-content");

            isRevealed = !isRevealed;
            if (isRevealed) {
                clickHint.style.display = "none";
                profileContent.style.display = "block";
            } else {
                clickHint.style.display = "block";
                profileContent.style.display = "none";
            }
        }

        function nextPlayer() {
            if (currentIndex < playersData.length) {
                currentIndex++;
                updateCard();
            }
        }

        function prevPlayer() {
            if (currentIndex > 0) {
                currentIndex--;
                updateCard();
            }
        }

        function resetGame() {
            currentIndex = 0;
            updateCard();
        }

        // 초기화 실행
        updateCard();
    </script>
</body>
</html>
