<!DOCTYPE html>
<html lang="th">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
    <title>รักนะที่รัก 💖</title>
    <style>
        body {
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            height: 100vh;
            background-color: #ffe6f2;
            font-family: Arial, sans-serif;
            text-align: center;
            overflow: hidden;
            position: relative;
        }
        h1 {
            color: #ff4081;
        }
        .heart-button {
            background-color: #ff4081;
            color: white;
            border: none;
            padding: 10px 20px;
            font-size: 18px;
            cursor: pointer;
            border-radius: 20px;
            margin-top: 20px;
            z-index: 10;
        }
        .heart {
            position: absolute;
            color: red;
            font-size: 24px;
            animation: float 2s linear forwards;
            pointer-events: none;
        }
        @keyframes float {
            0% {
                transform: translateY(0) scale(1);
                opacity: 1;
            }
            100% {
                transform: translateY(-150px) scale(1.5);
                opacity: 0;
            }
        }
        .progress-container {
            width: 80%;
            height: 20px;
            background-color: #f3f3f3;
            border-radius: 10px;
            margin-top: 20px;
            overflow: hidden;
            border: 2px solid #ff4081;
        }
        .progress-bar {
            width: 0%;
            height: 100%;
            background-color: #ff4081;
            transition: width 0.3s ease-in-out;
        }
    </style>
</head>
<body>
    <h1>Happy Valentine's Day ❤️</h1>
    <p>เรารักเธอเท่ากับจำนวนหัวใจที่แสดงขึ้นมาเลย💕</p>
    <button class="heart-button" onclick="showHeart(event)">ลองกดซ้ำๆดูสิ 💖</button>
    <div class="progress-container">
        <div class="progress-bar" id="progress-bar"></div>
    </div>

    <script>
        let clickCount = 0;
        const maxClicks = 15;
        
        function showHeart(event) {
            clickCount++;
            
            let progressBar = document.getElementById("progress-bar");
            progressBar.style.width = (clickCount / maxClicks) * 100 + "%";
            
            if (clickCount >= maxClicks) {
                window.location.href = "Untitled-1.html";
                return;
            }
            
            for (let i = 0; i < 10; i++) {
                setTimeout(() => {
                    let heart = document.createElement('div');
                    heart.innerHTML = '❤️';
                    heart.classList.add('heart');
                    document.body.appendChild(heart);

                    let x = Math.random() * window.innerWidth; 
                    let y = window.innerHeight - 50;
                    let size = Math.random() * 20 + 20;

                    heart.style.left = x + 'px';
                    heart.style.top = y + 'px';
                    heart.style.fontSize = size + 'px';
                    heart.style.opacity = Math.random() * 0.5 + 0.5;

                    setTimeout(() => { heart.remove(); }, 2000);
                }, i * 100);
            }
        }
    </script>
</body>
</html>


