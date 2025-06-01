<html lang="zh">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>喵喵乐园 - 点击就有猫咪表情</title>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Mali:wght@400;600&display=swap');
        
        body {
            font-family: 'Mali', cursive, sans-serif;
            text-align: center;
            background-color: #ffebf3;
            background-image: url('data:image/svg+xml;utf8,<svg xmlns="http://www.w3.org/2000/svg" width="100" height="100" viewBox="0 0 100 100"><circle cx="20" cy="20" r="3" fill="%23ff9ec6" opacity="0.4"/><circle cx="50" cy="30" r="4" fill="%23ff9ec6" opacity="0.4"/><circle cx="80" cy="20" r="3" fill="%23ff9ec6" opacity="0.4"/><circle cx="30" cy="60" r="5" fill="%23ff9ec6" opacity="0.4"/><circle cx="70" cy="70" r="4" fill="%23ff9ec6" opacity="0.4"/></svg>');
            height: 100vh;
            margin: 0;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            cursor: url("data:image/svg+xml;utf8,<svg xmlns='http://www.w3.org/2000/svg' width='24' height='24' viewBox='0 0 24 24'><text x='0' y='20' font-size='20'>🐾</text></svg>"), auto;
            overflow: hidden;
            position: relative;
        }
        
        h1 {
            color: #ff6b9e;
            font-size: 2.5rem;
            text-shadow: 3px 3px 0px rgba(255,255,255,0.8);
            margin-bottom: 10px;
            position: relative;
            display: inline-block;
        }
        
        h1:after {
            content: "";
            position: absolute;
            bottom: -5px;
            left: 0;
            width: 100%;
            height: 15px;
            background: url('data:image/svg+xml;utf8,<svg xmlns="http://www.w3.org/2000/svg" width="20" height="10" viewBox="0 0 20 10"><path d="M0,5 Q5,0 10,5 T20,5" fill="none" stroke="%23ff9ec6" stroke-width="2"/></svg>') repeat-x;
            background-size: 20px 10px;
        }
        
        .instructions {
            margin-top: 20px;
            color: #ff85b2;
            font-size: 1.2rem;
            background-color: rgba(255, 255, 255, 0.7);
            padding: 10px 20px;
            border-radius: 20px;
            box-shadow: 0 4px 8px rgba(255, 105, 158, 0.2);
        }
        
        .cat-emoji {
            font-size: 70px;
            position: absolute;
            animation: float 3s ease-in-out infinite;
            text-shadow: 0 0 10px rgba(255, 255, 255, 0.8);
            user-select: none;
            pointer-events: none;
            z-index: 10;
        }
        
        @keyframes float {
            0%, 100% { transform: translateY(0) rotate(-5deg); }
            50% { transform: translateY(-30px) rotate(5deg); }
        }
        
        .cloud {
            position: absolute;
            background-color: rgba(255, 255, 255, 0.8);
            border-radius: 50%;
            filter: blur(5px);
            z-index: -1;
        }
        
        .paw {
            position: absolute;
            font-size: 20px;
            opacity: 0.3;
            animation: fade 4s linear infinite;
        }
        
        @keyframes fade {
            0%, 100% { opacity: 0.1; }
            50% { opacity: 0.4; }
        }
    </style>
</head>
<body>
    <h1>喵喵乐园 🎀</h1>
    <p class="instructions">点击屏幕任何地方都会出现可爱的猫咪表情哦～</p>
    
    <script>
        const catEmojis = ['😺', '😸', '😹', '😻', '😼', '😽', '🙀', '😿', '😾'];
        
        // 创建背景云朵
        for (let i = 0; i < 10; i++) {
            const cloud = document.createElement('div');
            cloud.className = 'cloud';
            const size = Math.random() * 100 + 50;
            cloud.style.width = `${size}px`;
            cloud.style.height = `${size}px`;
            cloud.style.left = `${Math.random() * 100}%`;
            cloud.style.top = `${Math.random() * 100}%`;
            document.body.appendChild(cloud);
        }
        
        // 创建背景小爪印
        for (let i = 0; i < 30; i++) {
            const paw = document.createElement('div');
            paw.className = 'paw';
            paw.textContent = '🐾';
            paw.style.left = `${Math.random() * 100}%`;
            paw.style.top = `${Math.random() * 100}%`;
            paw.style.fontSize = `${Math.random() * 15 + 10}px`;
            paw.style.animationDelay = `${Math.random() * 4}s`;
            document.body.appendChild(paw);
        }
        
        document.addEventListener('click', function(e) {
            const emoji = document.createElement('div');
            emoji.className = 'cat-emoji';
            emoji.textContent = catEmojis[Math.floor(Math.random() * catEmojis.length)];
            
            // 设置表情位置为点击位置
            emoji.style.left = (e.clientX - 35) + 'px';
            emoji.style.top = (e.clientY - 35) + 'px';
            
            // 随机旋转角度
            emoji.style.transform = `rotate(${Math.random() * 30 - 15}deg)`;
            
            document.body.appendChild(emoji);
            
            // 播放喵喵声
            playMeow();
            
            // 3-6秒后移除表情
            setTimeout(() => {
                emoji.style.transition = 'all 0.5s';
                emoji.style.opacity = '0';
                emoji.style.transform = `${emoji.style.transform} scale(0.5)`;
                setTimeout(() => {
                    emoji.remove();
                }, 500);
            }, Math.random() * 3000 + 3000);
        });
        
        function playMeow() {
            const meows = [
                'https://assets.mixkit.co/sfx/preview/mixkit-cat-meow-117.mp3',
                'https://assets.mixkit.co/sfx/preview/mixkit-cat-purring-148.mp3',
                'https://assets.mixkit.co/sfx/preview/mixkit-cat-meow-119.mp3'
            ];
            const audio = new Audio(meows[Math.floor(Math.random() * meows.length)]);
            audio.volume = 0.3;
            audio.play().catch(e => console.log('自动播放被阻止，请点击页面后重试'));
        }
    </script>
</body>
</html>
