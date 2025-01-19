# korean-test
<html lang="ko">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>기초 한국어 퀴즈</title>
    <style>
        body {
            font-family: 'Arial', sans-serif;
            background-color: #f9f9f9;
            margin: 0;
            padding: 0;
            line-height: 1.6;
        }

        header {
            background-color: #4CAF50;
            color: white;
            padding: 20px 10px;
            text-align: center;
            font-size: 24px;
            font-weight: bold;
        }

        .container {
            max-width: 800px;
            margin: 20px auto;
            background: white;
            border-radius: 8px;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
            padding: 20px;
        }

        .question {
            margin-bottom: 20px;
        }

        .question p {
            font-size: 18px;
            font-weight: bold;
        }

        input[type="radio"] {
            margin-right: 10px;
        }

        button {
            background-color: #4CAF50;
            color: white;
            border: none;
            padding: 10px 15px;
            font-size: 16px;
            border-radius: 5px;
            cursor: pointer;
            transition: background-color 0.3s;
        }

        button:hover {
            background-color: #45a049;
        }

        .hidden {
            display: none;
        }

        .result {
            font-size: 20px;
            font-weight: bold;
            text-align: center;
            color: #333;
            margin-top: 20px;
        }

        footer {
            text-align: center;
            margin-top: 20px;
            font-size: 14px;
            color: #888;
        }
    </style>
</head>
<body>
    <header>기초 한국어 퀴즈</header>
    <div class="container">
        <h1>무엇에 대한 이야기입니까? 알맞은 것을 고르십시오.</h1>
        <div id="test-container">
            <!-- 첫 번째 질문 -->
            <div class="question" id="question-1">
                <p>1. 형은 스물한 살입니다. 누나는 스물세 살입니다.</p>
                <input type="radio" name="q1" value="0"> 날짜<br>
                <input type="radio" name="q1" value="1"> 나이<br>
                <input type="radio" name="q1" value="0"> 시간<br>
                <input type="radio" name="q1" value="0"> 이름<br>
                <button onclick="checkFirstAnswer()">확인</button>
            </div>
            
            <!-- 두 번째 질문 -->
            <div class="question hidden" id="question-2">
                <p>2. 비빔밥은 육천 원입니다. 냉면은 오천 원입니다.</p>
                <input type="radio" name="q2" value="1"> 값<br>
                <input type="radio" name="q2" value="0"> 맛<br>
                <input type="radio" name="q2" value="0"> 옷<br>
                <input type="radio" name="q2" value="0"> 일<br>
                <button onclick="checkSecondAnswer()">확인</button>
            </div>

            <!-- 세 번째 질문 -->
            <div class="question hidden" id="question-3">
                <p>3. 오늘은 날씨가 맑고 덥습니다.</p>
                <input type="radio" name="q3" value="0"> 시간<br>
                <input type="radio" name="q3" value="0"> 값<br>
                <input type="radio" name="q3" value="1"> 날씨<br>
                <input type="radio" name="q3" value="0"> 맛<br>
                <button onclick="showResult()">결과 보기</button>
            </div>

            <!-- 결과 -->
            <div id="result" class="hidden result"></div>
        </div>
    </div>
    <footer>© 2025 한국어 퀴즈</footer>

    <script>
        function checkFirstAnswer() {
            const selected = document.querySelector('input[name="q1"]:checked');
            if (selected && selected.value === "1") {
                alert("정답입니다! 다음 질문으로 넘어가세요.");
                document.getElementById("question-2").classList.remove("hidden");
            } else {
                alert("오답입니다! 다시 시도해보세요.");
            }
        }

        function checkSecondAnswer() {
            const selected = document.querySelector('input[name="q2"]:checked');
            if (selected && selected.value === "1") {
                alert("정답입니다! 다음 질문으로 넘어가세요.");
                document.getElementById("question-3").classList.remove("hidden");
            } else {
                alert("오답입니다! 다시 시도해보세요.");
            }
        }

        function showResult() {
            const selected1 = document.querySelector('input[name="q1"]:checked');
            const selected2 = document.querySelector('input[name="q2"]:checked');
            const selected3 = document.querySelector('input[name="q3"]:checked');
            const resultDiv = document.getElementById("result");

            if (selected1?.value === "1" && selected2?.value === "1" && selected3?.value === "1") {
                resultDiv.textContent = "축하합니다! 모든 질문에 정답을 맞췄습니다!";
                resultDiv.style.color = "green";
            } else {
                resultDiv.textContent = "모든 질문에 정답을 맞추지 못했습니다.";
                resultDiv.style.color = "red";
            }
            resultDiv.classList.remove("hidden");
        }
    </script>
</body>
</html>
