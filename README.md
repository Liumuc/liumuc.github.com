<!DOCTYPE html>
<html lang="zh">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>贺卡 - AP Computer Science Principles</title>
    <style>
        /* 背景样式 */
        body {
            margin: 0;
            height: 100vh;
            overflow: hidden;
            background: #000000; /* 夜晚背景为纯黑 */
            display: flex;
            justify-content: center;
            align-items: center;
            flex-direction: column;
            transition: background 5s ease-in-out;
        }

        /* 黑夜变成白昼的背景渐变 */
        .day {
            background: #FFFFFF; /* 白天背景为纯白 */
        }

        /* 烟花和祝福语样式 */
        .fireworks-container {
            position: relative;
            width: 100%;
            height: 100%;
            display: flex;
            flex-wrap: wrap;
            justify-content: space-around;
            align-items: center;
            padding: 20px;
        }

        .firework {
            position: absolute;
            width: 350px;
            height: 350px;
            display: flex;
            flex-direction: column;
            align-items: center;
            opacity: 0;
            transition: opacity 1s ease-in-out;
        }

        /* 签名图片和祝福语样式 */
        .firework img {
            width: 100px;
            height: auto;
            margin-bottom: 10px;
            border: none;
            border-radius: 0;
        }

        /* 黑白反色效果 */
         .invert img {
         filter: invert(1); /* 黑白反色效果 */
         }

        /* 黑白效果，只保留黑色和白色 */
        .black-white img {
           filter: grayscale(1) contrast(200%); /* 黑白效果，强化对比 */
       }

        .greeting {
            color: #000;
            font-size: 14px;
            text-align: center;
            font-family: Arial, sans-serif;
        }

        /* 太阳样式 */
        .sun {
            position: absolute;
            width: 100px;
            height: 100px;
            background: radial-gradient(circle at center, #fffae3, #ffd700, #ff8c00);
            border-radius: 50%;
            box-shadow: 0 0 30px 15px rgba(255, 223, 0, 0.5);
            opacity: 0;
            transition: transform 5s ease-in-out, opacity 5s ease-in-out;
            transform: translateY(200%);
        }

        .sunrise {
            opacity: 1;
            transform: translate(-50vw, -40vh); /* 从底部移到左上角 */
        }

        /* 祝福语样式 */
        .final-message {
            position: absolute;
            top: 40%;
            font-size: 24px;
            color: #333;
            font-family: "Times New Roman", serif;
            opacity: 0;
            transition: opacity 2s ease-in-out;
        }

        .show-message {
            opacity: 1;
        }
    </style>
</head>
<body>
    <!-- 烟花容器 -->
    <div class="fireworks-container">
        <!-- 夜晚第一波烟花 -->
        <div class="firework" style="top: 10%; left: 15%;" data-night="1">
            <img src="/pics/z_1.jpg" alt="z1">
            <p class="greeting">xxx</p>
        </div>
        <div class="firework" style="top: 20%; left: 35%;" data-night="1">
            <img src="/pics/z_2.jpg" alt="z2">
            <p class="greeting">xxx</p>
        </div>
        <div class="firework" style="top: 30%; left: 60%;" data-night="1">
            <img src="/pics/z_3.jpg" alt="z3">
            <p class="greeting">xxx</p>
        </div>
        <div class="firework" style="top: 50%; left: 25%;" data-night="1">
            <img src="/pics/z_4.jpg" alt="z4">
            <p class="greeting">xxx</p>
        </div>
        <div class="firework" style="top: 10%; left: 77%;" data-night="1">
            <img src="/pics/z_5.jpg" alt="z5">
            <p class="greeting">xxx</p>
        </div>
        <div class="firework" style="top: 60%; left: 57%;" data-night="1">
            <img src="/pics/z_6.jpg" alt="z6">
            <p class="greeting">xxx</p>
        </div>
        <div class="firework" style="top: 27%; left: 12%;" data-night="1">
            <img src="/pics/z_7.jpg" alt="z7">
            <p class="greeting">xxx</p>
        </div>

        <!-- 夜晚第二波烟花 -->
        <div class="firework" style="top: 86%; left: 57%;" data-night="2">
            <img src="/pics/z_8.jpg" alt="z8">
            <p class="greeting">xxx</p>
        </div>
        <div class="firework" style="top: 10%; left: 40%;" data-night="2">
            <img src="/pics/z_9.jpg" alt="z9">
            <p class="greeting">xxx</p>
        </div>
        <div class="firework" style="top: 30%; left: 3%;" data-night="2">
            <img src="/pics/z_10.jpg" alt="z10">
            <p class="greeting">xxx</p>
        </div>
        <div class="firework" style="top: 40%; left: 50%;" data-night="2">
            <img src="/pics/z_11.jpg" alt="z11">
            <p class="greeting">xxx</p>
        </div>
        <div class="firework" style="top: 90%; left: 30%;" data-night="2">
            <img src="/pics/z_12.jpg" alt="z12">
            <p class="greeting">xxx</p>
        </div>
        <div class="firework" style="top: 50%; left: 40%;" data-night="2">
            <img src="/pics/z_13.jpg" alt="z13">
            <p class="greeting">xxx</p>
        </div>
        <div class="firework" style="top: 15%; left: 65%;" data-night="2">
            <img src="/pics/z_14.jpg" alt="z14">
            <p class="greeting">xxx</p>
        </div>

        <!-- 白天第一波烟花 -->
        <div class="firework" style="top: 15%; left: 20%;" data-day="1">
            <img src="/pics/b_1.jpg" alt="b1">
            <p class="greeting">xxx</p>
        </div>
        <div class="firework" style="top: 67%; left: 65%;" data-day="1">
            <img src="/pics/b_2.jpg" alt="b2">
            <p class="greeting">xxx</p>
        </div>
        <div class="firework" style="top: 60%; left: 14%;" data-day="1">
            <img src="/pics/b_3.jpg" alt="b3">
            <p class="greeting">xxx</p>
        </div>
        <div class="firework" style="top: 45%; left: 75%;" data-day="1">
            <img src="/pics/b_4.jpg" alt="b4">
            <p class="greeting">xxx</p>
        </div>

        <div class="firework" style="top: 40%; left: 12%;" data-day="1">
            <img src="/pics/b_5.jpg" alt="b5">
            <p class="greeting">xxx</p>
        </div>
        <div class="firework" style="top: 70%; left: 29%;" data-day="1">
            <img src="/pics/b_6.jpg" alt="b6">
            <p class="greeting">xxx</p>
        </div>
        <div class="firework" style="top: 75%; left: 54%;" data-day="1">
            <img src="/pics/b_7.jpg" alt="b7">
            <p class="greeting">xxx</p>
        </div>
        <div class="firework" style="top: 29%; left: 50%;" data-day="1">
            <img src="/pics/b_8.jpg" alt="b8">
            <p class="greeting">xxx</p>
        </div>
    </div>

    <!-- 太阳 -->
    <div class="sun"></div>

    <!-- 最后祝福语 -->
    <div class="final-message" id="finalMessage">愿美好的事物与你常伴！</div>
    <script>
        function showFireworks(group, duration = 3000) {
    const fireworks = document.querySelectorAll(`.firework[data-${group}]`);
    fireworks.forEach(firework => {
        const img = firework.querySelector('img');
        
        // 如果图片文件名以 "b_" 开头，添加黑白效果
        if (img && img.src.includes('/b_')) {
            firework.classList.add('black-white');
        }

        firework.style.opacity = '1';
    });
    setTimeout(() => {
        fireworks.forEach(firework => {
            firework.style.opacity = '0';
        });
    }, duration);
    }

    function replayAllFireworks() {
        const allFireworks = document.querySelectorAll('.firework');
        allFireworks.forEach(firework => {
            const img = firework.querySelector('img');
            
            if (img && img.src.includes('/z_')) {
                firework.classList.add('invert'); // 添加黑白反色效果
            }

            if (img && img.src.includes('/b_')) {
                firework.classList.add('black-white'); // 保持黑白效果
            }

            firework.style.opacity = '1';
        });
        setTimeout(() => {
            allFireworks.forEach(firework => {
                firework.style.opacity = '0';
            });
        }, 4000);
    }


        function startSequence() {
            // 夜晚两波烟花
            setTimeout(() => showFireworks('night="1"'), 0);
            setTimeout(() => showFireworks('night="2"'), 6000);
            
            // 过渡到白天
            setTimeout(() => {
                document.body.classList.add('day');
            }, 12000);

            // 延迟太阳升起，直接移到左上角
            setTimeout(() => {
                document.querySelector('.sun').classList.add('sunrise');
            }, 12000);

            // 白天烟花，太阳完全升起后展示一波
            setTimeout(() => showFireworks('day="1"'), 18000);

            // 回顾展示所有祝福语和签名图片
            setTimeout(replayAllFireworks, 26000);

            // 显示最终祝福语
            setTimeout(() => {
                document.getElementById('finalMessage').classList.add('show-message');
            }, 31000);
        }

        window.onload = startSequence;
    </script>
</body>
</html>
