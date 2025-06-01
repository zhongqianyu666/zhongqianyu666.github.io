<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>孙芸熙生日快乐</title>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Ma+Shan+Zheng&family=Noto+Serif+SC:wght@400;700&display=swap');
        
        body {
            margin: 0;
            padding: 0;
            font-family: 'Noto Serif SC', serif;
            color: #fff;
            overflow-x: hidden;
            background: linear-gradient(-45deg, #ff9a9e, #fad0c4, #fbc2eb, #a6c1ee);
            background-size: 400% 400%;
            animation: gradientBG 15s ease infinite;
            height: 100vh;
        }
        
        @keyframes gradientBG {
            0% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
            100% { background-position: 0% 50%; }
        }
        
        .container {
            max-width: 800px;
            margin: 0 auto;
            padding: 40px;
            text-align: center;
            position: relative;
            z-index: 1;
        }
        
        h1 {
            font-family: 'Ma Shan Zheng', cursive;
            font-size: 3.5rem;
            margin-bottom: 20px;
            text-shadow: 3px 3px 0px rgba(0,0,0,0.1);
            color: #ff4d6d;
        }
        
        .poem {
            font-size: 1.2rem;
            line-height: 2;
            margin: 30px 0;
            background: rgba(255, 255, 255, 0.2);
            padding: 30px;
            border-radius: 15px;
            backdrop-filter: blur(5px);
            box-shadow: 0 10px 30px rgba(0,0,0,0.1);
        }
        
        .cake {
            width: 300px;
            height: 300px;
            margin: 30px auto;
            position: relative;
            animation: float 3s ease-in-out infinite;
        }
        
        @keyframes float {
            0% { transform: translateY(0px); }
            50% { transform: translateY(-20px); }
            100% { transform: translateY(0px); }
        }
        
        .cake-bottom {
            position: absolute;
            width: 250px;
            height: 120px;
            background: #f8edeb;
            border-radius: 10px 10px 0 0;
            bottom: 0;
            left: 25px;
            box-shadow: inset -5px -5px 15px rgba(0,0,0,0.1);
        }
        
        .cake-top {
            position: absolute;
            width: 200px;
            height: 80px;
            background: #f8edeb;
            border-radius: 10px 10px 0 0;
            bottom: 120px;
            left: 50px;
            box-shadow: inset -5px -5px 15px rgba(0,0,0,0.1);
        }
        
        .cream {
            position: absolute;
            width: 250px;
            height: 30px;
            background: #ffddd2;
            border-radius: 50%;
            bottom: 110px;
            left: 25px;
        }
        
        .strawberry {
            position: absolute;
            width: 30px;
            height: 30px;
            background: #ff4d6d;
            border-radius: 50% 50% 50% 50% / 60% 60% 40% 40%;
            transform: rotate(45deg);
        }
        
        .strawberry:before {
            content: "";
            position: absolute;
            width: 5px;
            height: 10px;
            background: #2d6a4f;
            top: -8px;
            left: 12px;
            border-radius: 5px;
        }
        
        .candle {
            position: absolute;
            width: 10px;
            height: 60px;
            background: linear-gradient(to right, #ffb3c1, #ffccd5, #ffb3c1);
            bottom: 200px;
            left: 145px;
            z-index: 10;
        }
        
        .flame {
            position: absolute;
            width: 20px;
            height: 40px;
            background: linear-gradient(to top, #ff9e00, #ffea00);
            border-radius: 50% 50% 20% 20%;
            bottom: 260px;
            left: 140px;
            animation: flicker 1s ease-in-out infinite alternate;
            box-shadow: 0 0 20px #ff9e00, 0 0 40px #ffea00;
        }
        
        @keyframes flicker {
            0% { transform: scale(1); opacity: 1; }
            50% { transform: scale(1.1); opacity: 0.8; }
            100% { transform: scale(0.9); opacity: 1; }
        }
        
        .wish {
            font-size: 1.5rem;
            margin-top: 40px;
            font-weight: bold;
            color: #590d22;
        }
        
        .stars {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
            z-index: 0;
        }
        
        .star {
            position: absolute;
            background: white;
            border-radius: 50%;
            animation: twinkle 2s infinite;
        }
        
        @keyframes twinkle {
            0% { opacity: 0.2; }
            50% { opacity: 1; }
            100% { opacity: 0.2; }
        }
    </style>
</head>
<body>
    <div class="stars" id="stars"></div>
    
    <div class="container">
        <h1>孙芸熙生日快乐</h1>
        
        <div class="poem">
            <p>芸窗初启日熙熙，</p>
            <p>熙景韶光正此时。</p>
            <p>岁月如歌添锦绣，</p>
            <p>芳华似画展新姿。</p>
            <p>桃李春风一杯酒，</p>
            <p>江湖夜雨十年诗。</p>
            <p>愿君岁岁常欢愉，</p>
            <p>皆得所愿展鸿逵。</p>
        </div>
        
        <div class="cake">
            <div class="cake-bottom"></div>
            <div class="cream"></div>
            <div class="cake-top"></div>
            <div class="candle"></div>
            <div class="flame"></div>
            <div class="strawberry" style="bottom: 140px; left: 60px;"></div>
            <div class="strawberry" style="bottom: 150px; left: 120px;"></div>
            <div class="strawberry" style="bottom: 130px; left: 180px;"></div>
            <div class="strawberry" style="bottom: 170px; left: 90px;"></div>
            <div class="strawberry" style="bottom: 160px; left: 150px;"></div>
        </div>
        
        <div class="wish">
            <p>愿新的一岁，如春日般温暖，如夏花般绚烂，</p>
            <p>如秋实般丰盈，如冬雪般纯净。</p>
            <p>生日快乐，孙芸熙！</p>
        </div>
    </div>
    
    <script>
        // 创建星星背景
        const stars = document.getElementById('stars');
        for (let i = 0; i < 100; i++) {
            const star = document.createElement('div');
            star.classList.add('star');
            star.style.width = `${Math.random() * 3 + 1}px`;
            star.style.height = star.style.width;
            star.style.left = `${Math.random() * 100}%`;
            star.style.top = `${Math.random() * 100}%`;
            star.style.animationDelay = `${Math.random() * 2}s`;
            stars.appendChild(star);
        }
        
        // 点击页面撒花效果
        document.addEventListener('click', function(e) {
            const colors = ['#ff9a9e', '#fad0c4', '#fbc2eb', '#a6c1ee', '#ffb3c1', '#ffccd5'];
            const flower = document.createElement('div');
            flower.style.position = 'fixed';
            flower.style.left = `${e.clientX}px`;
            flower.style.top = `${e.clientY}px`;
            flower.style.width = '20px';
            flower.style.height = '20px';
            flower.style.borderRadius = '50%';
            flower.style.background = colors[Math.floor(Math.random() * colors.length)];
            flower.style.pointerEvents = 'none';
            flower.style.boxShadow = '0 0 10px currentColor';
            flower.style.animation = 'fall 3s linear forwards';
            
            document.body.appendChild(flower);
            
            // 动画
            const animation = flower.animate([
                { transform: 'translateY(0) rotate(0deg)', opacity: 1 },
                { transform: `translateY(${window.innerHeight}px) rotate(360deg)`, opacity: 0 }
            ], {
                duration: 3000,
                easing: 'linear'
            });
            
            animation.onfinish = () => flower.remove();
        });
        
        // 添加CSS动画
        const style = document.createElement('style');
        style.textContent = `
            @keyframes fall {
                to { transform: translateY(${window.innerHeight}px) rotate(360deg); opacity: 0; }
            }
        `;
        document.head.appendChild(style);
    </script>
</body>
</html>
