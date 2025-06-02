<html lang="zh">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>动物表情乐园</title>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Comic+Neue:wght@700&display=swap');
        
        body {
            font-family: 'Comic Neue', cursive;
            text-align: center;
            background: linear-gradient(135deg, #ffcce6, #ccf2ff);
            height: 100vh;
            margin: 0;
            overflow: hidden;
            cursor: url("data:image/svg+xml;utf8,<svg xmlns='http://www.w3.org/2000/svg' width='32' height='32' viewBox='0 0 32 32'><text x='0' y='28' font-size='28'>🐾</text></svg>"), auto;
        }
        
        h1 {
            color: #ff6699;
            font-size: 2.8rem;
            text-shadow: 3px 3px 0 #fff;
            margin-top: 20px;
            position: relative;
            z-index: 100;
        }
        
        .subtitle {
            color: #66b3ff;
            font-size: 1.2rem;
            margin-top: -10px;
            margin-bottom: 30px;
        }
        
        .emoji {
            position: absolute;
            font-size: 60px;
            pointer-events: none;
            user-select: none;
            animation: float 3s ease-in-out infinite;
            z-index: 10;
            filter: drop-shadow(0 0 5px rgba(255,255,255,0.7));
        }
        
        @keyframes float {
            0%, 100% { transform: translateY(0) rotate(0deg); }
            50% { transform: translateY(-30px) rotate(10deg); }
        }
        
        .ground {
            position: absolute;
            bottom: 0;
            width: 100%;
            height: 100px;
            background: linear-gradient(to top, #a6e3a1, #c8f7c5);
            z-index: 1;
        }
        
        .cloud {
            position: absolute;
            background: white;
            border-radius: 50%;
            opacity: 0.8;
            filter: blur(5px);
            z-index: 0;
        }
        
        .counter {
            position: fixed;
            bottom: 20px;
            right: 20px;
            background: rgba(255,255,255,0.7);
            padding: 10px 15px;
            border-radius: 20px;
            font-size: 1.2rem;
            color: #ff6699;
            box-shadow: 0 0 10px rgba(0,0,0,0.1);
            z-index: 100;
        }
    </style>
</head>
<body>
    <h1>动物表情乐园 🎡</h1>
    <div class="subtitle">点击屏幕任何地方召唤可爱动物！</div>
    <div class="ground"></div>
    <div class="counter">已召唤: <span id="count">0</span> 只动物</div>
    
    <script>
        const animals = [
            '😺', '😸', '😹', '😻', '😼', '😽', '🙀', '😿', '😾',
            '🦁', '🐯', '🦊', '🦝', '🐰', '🐹', '🐭', '🐮', '🐻',
            '🐨', '🐸', '🐼', '🐙', '🦑', '🦉', '🐧', '🐥', '🐌'
        ];
        
        let counter = 0;
        
        // 创建背景云朵
        for (let i = 0; i < 15; i++) {
            createCloud();
        }
        
        function createCloud() {
            const cloud = document.createElement('div');
            cloud.className = 'cloud';
            const size = Math.random() * 100 + 50;
            cloud.style.width = `${size}px`;
            cloud.style.height = `${size/1.5}px`;
            cloud.style.left = `${Math.random() * 100}%`;
            cloud.style.top = `${Math.random() * 30 + 10}%`;
            cloud.style.opacity = Math.random() * 0.5 + 0.3;
            document.body.appendChild(cloud);
        }
        
        document.addEventListener('click', function(e) {
            // 创建动物表情
            const emoji = document.createElement('div');
            emoji.className = 'emoji';
            emoji.textContent = animals[Math.floor(Math.random() * animals.length)];
            
            // 设置位置
            emoji.style.left = (e.clientX - 30) + 'px';
            emoji.style.top = (e.clientY - 30) + 'px';
            
            // 随机大小和旋转
            const size = Math.random() * 20 + 50;
            emoji.style.fontSize = `${size}px`;
            emoji.style.transform = `rotate(${Math.random() * 30 - 15}deg)`;
            
            document.body.appendChild(emoji);
            
            // 更新计数器
            counter++;
            document.getElementById('count').textContent = counter;
            
            // 播放音效
            playAnimalSound();
            
            // 5-8秒后移除表情
            setTimeout(() => {
                emoji.style.transition = 'all 0.5s';
                emoji.style.opacity = '0';
                emoji.style.transform = emoji.style.transform + ' scale(0.5)';
                setTimeout(() => {
                    emoji.remove();
                }, 500);
            }, Math.random() * 3000 + 5000);
        });
        
        function playAnimalSound() {
            const sounds = [
                'https://assets.mixkit.co/sfx/preview/mixkit-cat-meow-117.mp3',
                'https://assets.mixkit.co/sfx/preview/mixkit-bird-whistle-1560.mp3',
                'https://assets.mixkit.co/sfx/preview/mixkit-monkey-little-squeak-108.mp3'
            ];
            const sound = new Audio(sounds[Math.floor(Math.random() * sounds.length)]);
            sound.volume = 0.3;
            sound.play().catch(e => console.log('需要用户交互后才能播放声音'));
        }
    </script>
</body>
</html>
