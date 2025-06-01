<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title> - 天天来财</title>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Ma+Shan+Zheng&family=Noto+Serif+SC:wght@400;700&display=swap');
        
        body {
            margin: 0;
            padding: 0;
            font-family: 'Noto Serif SC', serif;
            color: #ffde59;
            overflow: hidden;
            background: #e53935;
            height: 100vh;
            position: relative;
        }
        
        .container {
            max-width: 800px;
            margin: 0 auto;
            padding: 40px;
            text-align: center;
            position: relative;
            z-index: 1;
            background-color: transparent;
            margin-top: 50px;
        }
        
        h1 {
            font-family: 'Ma Shan Zheng', cursive;
            font-size: 4rem;
            margin-bottom: 20px;
            text-shadow: 3px 3px 0px rgba(0,0,0,0.3);
            color: #ffde59;
        }
        
        .blessing {
            font-size: 1.5rem;
            line-height: 2;
            margin: 30px 0;
            padding: 30px;
            border-radius: 15px;
            color: #ffde59;
            text-shadow: 2px 2px 4px rgba(0,0,0,0.3);
        }
        
        .gold-text {
            color: #d4af37;
            font-weight: bold;
            text-shadow: 1px 1px 2px rgba(0,0,0,0.3);
        }
        
        .red-packet {
            position: absolute;
            width: 80px;
            height: 100px;
            background: #e53935;
            color: #ffde59;
            font-weight: bold;
            display: flex;
            justify-content: center;
            align-items: center;
            border-radius: 5px;
            box-shadow: 0 5px 15px rgba(0,0,0,0.3);
            z-index: 0;
            user-select: none;
            cursor: pointer;
            transform: rotate(15deg);
            font-family: 'Ma Shan Zheng', cursive;
            text-align: center;
            padding: 10px;
            border: 2px solid #ffde59;
            animation: fall linear forwards;
        }
        
        .red-packet:before {
            content: "";
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            height: 20px;
            background: rgba(255, 255, 255, 0.3);
            border-radius: 5px 5px 0 0;
        }
        
        .red-packet:after {
            content: "财";
            position: absolute;
            bottom: 5px;
            right: 5px;
            font-size: 1.5rem;
            color: #ffde59;
        }
        
        @keyframes fall {
            to {
                transform: translateY(100vh) rotate(360deg);
            }
        }
        
        .money-icon {
            font-size: 3rem;
            margin: 20px;
            animation: bounce 2s infinite;
            text-shadow: 0 0 10px rgba(255,222,89,0.7);
        }
        
        @keyframes bounce {
            0%, 100% { transform: translateY(0); }
            50% { transform: translateY(-20px); }
        }
        
        .wish {
            font-size: 2rem;
            margin-top: 40px;
            font-weight: bold;
            color: #ffde59;
            text-shadow: 2px 2px 4px rgba(0,0,0,0.3);
        }
        
        .gold-coins {
            position: fixed;
            bottom: 0;
            width: 100%;
            height: 100px;
            background: linear-gradient(to top, rgba(212, 175, 55, 0.8), transparent);
            z-index: 0;
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>吴子翀 天天来财</h1>
        
        <div class="money-icon">💰</div>
        
        <div class="blessing">
            <p><span class="gold-text">芸</span>窗瑞气盈门庭，</p>
            <p><span class="gold-text">熙</span>熙攘攘聚宝盆。</p>
            <p>日进斗金如潮水，</p>
            <p>年年有余福满门。</p>
            <p>生意兴隆通四海，</p>
            <p>财源茂盛达三江。</p>
        </div>
        
        <div class="wish">
            <p>愿您天天来财，时时进宝！</p>
            <p>财源滚滚，富贵吉祥！</p>
        </div>
    </div>
    
    <div class="gold-coins"></div>
    
    <script>
        // 创建红包雨
        function createRedPacket() {
            const packet = document.createElement('div');
            packet.className = 'red-packet';
            
            // 随机选择祝福语
            const blessings = ["天天来财", "招财进宝", "财源广进", "日进斗金", "生意兴隆", "财运亨通"];
            const randomBlessing = blessings[Math.floor(Math.random() * blessings.length)];
            packet.textContent = randomBlessing;
            
            // 随机位置
            packet.style.left = `${Math.random() * 100}vw`;
            packet.style.top = `-100px`;
            
            // 随机动画持续时间
            const duration = Math.random() * 5 + 3;
            packet.style.animationDuration = `${duration}s`;
            
            // 随机旋转
            const rotation = (Math.random() * 60) - 30;
            packet.style.transform = `rotate(${rotation}deg)`;
            
            document.body.appendChild(packet);
            
            // 点击红包效果
            packet.addEventListener('click', function() {
                this.style.animation = 'none';
                this.style.transform = 'scale(1.5) rotate(0deg)';
                this.style.transition = 'all 0.5s';
                this.style.opacity = '0';
                
                // 创建金币飞溅效果
                for (let i = 0; i < 5; i++) {
                    const coin = document.createElement('div');
                    coin.textContent = '💰';
                    coin.style.position = 'absolute';
                    coin.style.left = this.offsetLeft + 'px';
                    coin.style.top = this.offsetTop + 'px';
                    coin.style.fontSize = '2rem';
                    coin.style.zIndex = '100';
                    coin.style.animation = `coinFly${i} 1s forwards`;
                    
                    document.body.appendChild(coin);
                    
                    // 添加动画
                    const style = document.createElement('style');
                    style.textContent = `
                        @keyframes coinFly${i} {
                            0% { transform: translate(0, 0) scale(1); opacity: 1; }
                            100% { transform: translate(${(Math.random() - 0.5) * 200}px, ${-Math.random() * 100 - 50}px) scale(0); opacity: 0; }
                        }
                    `;
                    document.head.appendChild(style);
                    
                    // 移除金币
                    setTimeout(() => {
                        coin.remove();
                        style.remove();
                    }, 1000);
                }
                
                setTimeout(() => {
                    this.remove();
                }, 500);
            });
            
            // 红包落地后移除
            setTimeout(() => {
                packet.remove();
            }, duration * 1000);
        }
        
        // 持续生成红包
        setInterval(createRedPacket, 300);
        
        // 初始生成一批红包
        for (let i = 0; i < 20; i++) {
            setTimeout(createRedPacket, i * 150);
        }
        
        // 背景金币闪烁
        setInterval(() => {
            const goldTexts = document.querySelectorAll('.gold-text');
            goldTexts.forEach(text => {
                text.style.color = `hsl(${Math.random() * 20 + 40}, 100%, 60%)`;
            });
        }, 1000);
    </script>
</body>
</html>
