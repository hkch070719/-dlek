<!DOCTYPE html>
    <html lang="ko">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>카운트다운 타이머</title>
    <style>
        body {
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            font-family: Arial, sans-serif;
            background-image: url(FSEAhGSakAESQMO.jpg);
            background-size: cover;
            background-position: center;
            margin: 0;
        }
        .countdown {
            text-align: center;
            background-color: rgba(255, 255, 255, 0.8);
            padding: 20px;
            border-radius: 10px;
        }
        h1 {
            font-size: 2em;
            color: black;
            margin: 0;
        }
        .time {
            font-size: 1.5em;
            color: black;
        }
    </style>
</head>
<body>

    <div class="countdown">
        <h1>클로티드 쿠키 뽑기 기원</h1>
        <div id="time" class="time">00일 00시간 00분 00초</div>
    </div>

    <script>
        function updateCountdown() {
            // 타겟 시간을 2024년 11월 16일 오후 5시로 설정
            const targetDate = new Date('2024-11-16T17:00:00+09:00').getTime();
            const now = new Date().getTime();
            const timeDifference = targetDate - now;

            if (timeDifference > 0) {
                // 남은 시간 계산
                const days = Math.floor(timeDifference / (1000 * 60 * 60 * 24));
                const hours = Math.floor((timeDifference % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
                const minutes = Math.floor((timeDifference % (1000 * 60 * 60)) / (1000 * 60));
                const seconds = Math.floor((timeDifference % (1000 * 60)) / 1000);

                // 남은 시간을 화면에 표시
                document.getElementById("time").innerHTML =
                    `${days}일 ${hours}시간 ${minutes}분 ${seconds}초`;
            } else {
                // 타이머가 끝났을 때의 메시지
                document.getElementById("time").innerHTML = "타이머가 종료되었습니다!";
                clearInterval(countdownInterval);
            }
        }

        // 1초마다 카운트다운 업데이트
        const countdownInterval = setInterval(updateCountdown, 1000);
        updateCountdown(); // 페이지 로딩 시 초기 카운트다운 업데이트
    </script>

</body>
</html>
