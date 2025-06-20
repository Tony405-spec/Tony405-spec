<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>SKYNET NEURAL CORE - Ken_Tony</title>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Orbitron:wght@400;700;900&family=Share+Tech+Mono&display=swap');
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        body {
            background: #000000;
            color: #00ff00;
            font-family: 'Orbitron', monospace;
            overflow-x: hidden;
            min-height: 100vh;
            position: relative;
        }
        
        /* Matrix Rain Background */
        .matrix-bg {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: -1;
            opacity: 0.1;
        }
        
        /* Glitch Effect */
        @keyframes glitch {
            0% { transform: translate(0); }
            20% { transform: translate(-2px, 2px); }
            40% { transform: translate(-2px, -2px); }
            60% { transform: translate(2px, 2px); }
            80% { transform: translate(2px, -2px); }
            100% { transform: translate(0); }
        }
        
        .glitch {
            animation: glitch 0.3s infinite;
        }
        
        /* Main Container */
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 20px;
            position: relative;
            z-index: 1;
        }
        
        /* Terminator Eye Animation */
        .terminator-eye {
            width: 200px;
            height: 200px;
            margin: 20px auto;
            position: relative;
            border-radius: 50%;
            background: radial-gradient(circle at center, #ff0000 0%, #990000 30%, #330000 60%, #000000 100%);
            box-shadow: 
                0 0 50px #ff0000,
                inset 0 0 30px #ff0000,
                0 0 100px #ff0000;
            animation: pulse-eye 2s infinite alternate;
        }
        
        @keyframes pulse-eye {
            0% {
                box-shadow: 
                    0 0 50px #ff0000,
                    inset 0 0 30px #ff0000,
                    0 0 100px #ff0000;
                transform: scale(1);
            }
            100% {
                box-shadow: 
                    0 0 80px #ff0000,
                    inset 0 0 50px #ff0000,
                    0 0 150px #ff0000;
                transform: scale(1.1);
            }
        }
        
        .eye-pupil {
            width: 60px;
            height: 60px;
            background: #000000;
            border-radius: 50%;
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            box-shadow: inset 0 0 20px #ff0000;
            animation: scan 4s linear infinite;
        }
        
        .eye-iris {
            width: 120px;
            height: 120px;
            background: radial-gradient(circle, #ff0000 0%, transparent 70%);
            border-radius: 50%;
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            animation: iris-flicker 3s infinite;
        }
        
        @keyframes scan {
            0%, 100% { transform: translate(-50%, -50%) rotate(0deg); }
            25% { transform: translate(-30%, -70%) rotate(90deg); }
            50% { transform: translate(-70%, -50%) rotate(180deg); }
            75% { transform: translate(-50%, -30%) rotate(270deg); }
        }
        
        @keyframes iris-flicker {
            0%, 90%, 100% { opacity: 1; }
            95% { opacity: 0.3; }
        }
        
        /* Scanning Lines */
        .scan-line {
            position: absolute;
            width: 100%;
            height: 2px;
            background: linear-gradient(90deg, transparent, #ff0000, transparent);
            top: 50%;
            animation: scan-horizontal 2s linear infinite;
        }
        
        .scan-line-vertical {
            position: absolute;
            width: 2px;
            height: 100%;
            background: linear-gradient(0deg, transparent, #ff0000, transparent);
            left: 50%;
            animation: scan-vertical 3s linear infinite;
        }
        
        @keyframes scan-horizontal {
            0% { top: 0%; opacity: 0; }
            50% { opacity: 1; }
            100% { top: 100%; opacity: 0; }
        }
        
        @keyframes scan-vertical {
            0% { left: 0%; opacity: 0; }
            50% { opacity: 1; }
            100% { left: 100%; opacity: 0; }
        }
        
        /* Multiple Eyes Grid */
        .eye-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
            gap: 30px;
            margin: 40px 0;
        }
        
        .mini-eye {
            width: 120px;
            height: 120px;
            border-radius: 50%;
            background: radial-gradient(circle at 30% 30%, #ff0000 0%, #990000 30%, #330000 60%, #000000 100%);
            position: relative;
            margin: 0 auto;
            animation: mini-pulse 1.5s infinite alternate;
            box-shadow: 0 0 30px #ff0000;
        }
        
        .mini-eye:nth-child(odd) {
            animation-delay: 0.5s;
        }
        
        .mini-eye:nth-child(even) {
            animation-delay: 1s;
        }
        
        @keyframes mini-pulse {
            0% {
                box-shadow: 0 0 30px #ff0000;
                filter: brightness(100%);
            }
            100% {
                box-shadow: 0 0 60px #ff0000;
                filter: brightness(150%);
            }
        }
        
        .mini-pupil {
            width: 30px;
            height: 30px;
            background: #000000;
            border-radius: 50%;
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            animation: mini-scan 3s linear infinite;
        }
        
        @keyframes mini-scan {
            0%, 100% { transform: translate(-50%, -50%); }
            25% { transform: translate(-30%, -70%); }
            50% { transform: translate(-70%, -50%); }
            75% { transform: translate(-50%, -30%); }
        }
        
        /* Header Styles */
        .header {
            text-align: center;
            margin: 40px 0;
        }
        
        .title {
            font-size: 3rem;
            font-weight: 900;
            color: #ff0000;
            text-shadow: 
                0 0 10px #ff0000,
                0 0 20px #ff0000,
                0 0 40px #ff0000;
            animation: title-flicker 4s infinite;
            margin-bottom: 20px;
        }
        
        @keyframes title-flicker {
            0%, 95%, 100% { opacity: 1; }
            96%, 98% { opacity: 0.7; }
            97% { opacity: 0.3; }
        }
        
        .subtitle {
            font-size: 1.5rem;
            color: #00ff00;
            text-shadow: 0 0 10px #00ff00;
            animation: type-writer 3s steps(40, end);
            overflow: hidden;
            white-space: nowrap;
            margin: 0 auto;
            border-right: 2px solid #00ff00;
        }
        
        @keyframes type-writer {
            from { width: 0; }
            to { width: 100%; }
        }
        
        /* Status Panel */
        .status-panel {
            background: linear-gradient(135deg, #1a0000, #000000);
            border: 2px solid #ff0000;
            border-radius: 15px;
            padding: 30px;
            margin: 40px 0;
            box-shadow: 
                0 0 30px rgba(255, 0, 0, 0.3),
                inset 0 0 20px rgba(255, 0, 0, 0.1);
            position: relative;
            overflow: hidden;
        }
        
        .status-panel::before {
            content: '';
            position: absolute;
            top: -2px;
            left: -2px;
            right: -2px;
            bottom: -2px;
            background: linear-gradient(45deg, #ff0000, transparent, #ff0000);
            z-index: -1;
            animation: border-glow 3s linear infinite;
        }
        
        @keyframes border-glow {
            0%, 100% { opacity: 0.5; }
            50% { opacity: 1; }
        }
        
        .status-line {
            font-family: 'Share Tech Mono', monospace;
            margin: 10px 0;
            color: #00ff00;
            animation: data-stream 2s infinite;
        }
        
        @keyframes data-stream {
            0%, 100% { color: #00ff00; }
            50% { color: #ffff00; }
        }
        
        /* Progress Bars */
        .progress-bar {
            background: #000000;
            border: 1px solid #ff0000;
            height: 20px;
            margin: 10px 0;
            position: relative;
            overflow: hidden;
        }
        
        .progress-fill {
            height: 100%;
            background: linear-gradient(90deg, #ff0000, #ff6600, #ff0000);
            animation: progress-move 2s linear infinite;
        }
        
        @keyframes progress-move {
            0% { width: 0%; }
            100% { width: 100%; }
        }
        
        /* HUD Elements */
        .hud-overlay {
            position: fixed;
            top: 20px;
            right: 20px;
            background: rgba(0, 0, 0, 0.8);
            border: 1px solid #ff0000;
            padding: 15px;
            font-family: 'Share Tech Mono', monospace;
            color: #ff0000;
            z-index: 1000;
            animation: hud-blink 3s infinite;
        }
        
        @keyframes hud-blink {
            0%, 90%, 100% { opacity: 1; }
            95% { opacity: 0.5; }
        }
        
        /* Crosshair */
        .crosshair {
            position: fixed;
            top: 50%;
            left: 50%;
            width: 40px;
            height: 40px;
            transform: translate(-50%, -50%);
            pointer-events: none;
            z-index: 1000;
        }
        
        .crosshair::before,
        .crosshair::after {
            content: '';
            position: absolute;
            background: #ff0000;
            box-shadow: 0 0 5px #ff0000;
        }
        
        .crosshair::before {
            width: 40px;
            height: 2px;
            top: 50%;
            left: 0;
            transform: translateY(-50%);
        }
        
        .crosshair::after {
            width: 2px;
            height: 40px;
            left: 50%;
            top: 0;
            transform: translateX(-50%);
        }
        
        /* Responsive */
        @media (max-width: 768px) {
            .title {
                font-size: 2rem;
            }
            
            .terminator-eye {
                width: 150px;
                height: 150px;
            }
            
            .mini-eye {
                width: 80px;
                height: 80px;
            }
        }
        
        /* Additional Eye Animations */
        .scanning-eye {
            position: relative;
            animation: eye-movement 5s infinite;
        }
        
        @keyframes eye-movement {
            0%, 100% { transform: translateX(0); }
            25% { transform: translateX(20px); }
            50% { transform: translateX(-20px); }
            75% { transform: translateX(10px); }
        }
        
        .laser-beam {
            position: absolute;
            width: 100%;
            height: 2px;
            background: linear-gradient(90deg, transparent, #ff0000, transparent);
            top: 50%;
            animation: laser-sweep 2s linear infinite;
            box-shadow: 0 0 10px #ff0000;
        }
        
        @keyframes laser-sweep {
            0% { left: -100%; }
            100% { left: 100%; }
        }
    </style>
</head>
<body>
    <canvas class="matrix-bg" id="matrix"></canvas>
    
    <div class="crosshair"></div>
    
    <div class="hud-overlay">
        <div>STATUS: ONLINE</div>
        <div>THREAT: MINIMAL</div>
        <div>TARGET: ACQUIRED</div>
        <div id="time"></div>
    </div>
    
    <div class="container">
        <header class="header">
            <h1 class="title glitch">🔴 SKYNET NEURAL CORE</h1>
            <p class="subtitle">Ken_Tony - Data Science Terminator Unit</p>
        </header>
        
        <div class="terminator-eye scanning-eye">
            <div class="eye-iris"></div>
            <div class="eye-pupil"></div>
            <div class="scan-line"></div>
            <div class="scan-line-vertical"></div>
            <div class="laser-beam"></div>
        </div>
        
        <div class="status-panel">
            <h2 style="color: #ff0000; text-align: center; margin-bottom: 20px;">NEURAL INTERFACE DIAGNOSTICS</h2>
            <div class="status-line">📡 MODEL: Data Science Terminator Unit</div>
            <div class="status-line">⚡ AGE: 21 Earth Solar Cycles</div>
            <div class="status-line">🧬 CORE DIRECTIVE: Learn. Adapt. Terminate Bugs.</div>
            <div class="status-line">💀 THREAT LEVEL: MAXIMUM</div>
            <div class="status-line">🎯 MISSION STATUS: Active Learning Protocol</div>
            
            <div style="margin: 20px 0;">
                <div>Python Mastery:</div>
                <div class="progress-bar">
                    <div class="progress-fill" style="animation-duration: 1s;"></div>
                </div>
                
                <div>ML Algorithms:</div>
                <div class="progress-bar">
                    <div class="progress-fill" style="animation-duration: 1.5s;"></div>
                </div>
                
                <div>Neural Networks:</div>
                <div class="progress-bar">
                    <div class="progress-fill" style="animation-duration: 1.2s;"></div>
                </div>
                
                <div>Bug Termination:</div>
                <div class="progress-bar">
                    <div class="progress-fill" style="animation-duration: 0.8s;"></div>
                </div>
            </div>
        </div>
        
        <div class="eye-grid">
            <div class="mini-eye">
                <div class="mini-pupil"></div>
                <div class="laser-beam"></div>
            </div>
            <div class="mini-eye">
                <div class="mini-pupil"></div>
                <div class="laser-beam"></div>
            </div>
            <div class="mini-eye">
                <div class="mini-pupil"></div>
                <div class="laser-beam"></div>
            </div>
            <div class="mini-eye">
                <div class="mini-pupil"></div>
                <div class="laser-beam"></div>
            </div>
            <div class="mini-eye">
                <div class="mini-pupil"></div>
                <div class="laser-beam"></div>
            </div>
            <div class="mini-eye">
                <div class="mini-pupil"></div>
                <div class="laser-beam"></div>
            </div>
        </div>
        
        <div class="status-panel">
            <h2 style="color: #ff0000; text-align: center; margin-bottom: 20px;">WEAPON SYSTEMS ONLINE</h2>
            <div class="status-line">🐍 Python - Neural Processing Core</div>
            <div class="status-line">🧠 TensorFlow - Advanced AI Weaponry</div>
            <div class="status-line">📊 Pandas - Data Manipulation Arsenal</div>
            <div class="status-line">🎮 Unity - Reality Simulation Engine</div>
            <div class="status-line">☁️ AWS - Distributed Network Protocol</div>
            <div class="status-line">🐧 Linux - Command & Control Interface</div>
        </div>
        
        <div class="status-panel">
            <h2 style="color: #ff0000; text-align: center; margin-bottom: 20px;">MISSION OBJECTIVES</h2>
            <div class="status-line">🎯 PRIMARY: Complete Data Science Program</div>
            <div class="status-line">🚀 SECONDARY: Master Machine Learning</div>
            <div class="status-line">🎮 TERTIARY: Develop Next-Gen Games</div>
            <div class="status-line">🤖 ULTIMATE: Achieve Human-AI Symbiosis</div>
            <div class="status-line">💀 ONGOING: Terminate All Bugs in Code</div>
        </div>
        
        <div style="text-align: center; margin: 40px 0; color: #ff0000; font-size: 1.2rem;">
            <p>"Every bug is just an opportunity for recursive self-improvement."</p>
            <p style="margin-top: 20px; color: #00ff00;">📧 Contact: tonykenga23@gmail.com</p>
        </div>
    </div>
    
    <script>
        // Matrix Rain Effect
        const canvas = document.getElementById('matrix');
        const ctx = canvas.getContext('2d');
        
        canvas.width = window.innerWidth;
        canvas.height = window.innerHeight;
        
        const matrix = "ABCDEFGHIJKLMNOPQRSTUVWXYZ123456789@#$%^&*()*&^%+-/~{[|`]}".split("");
        const font_size = 10;
        const columns = canvas.width / font_size;
        const drops = [];
        
        for(let x = 0; x < columns; x++) {
            drops[x] = 1;
        }
        
        function draw() {
            ctx.fillStyle = 'rgba(0, 0, 0, 0.04)';
            ctx.fillRect(0, 0, canvas.width, canvas.height);
            
            ctx.fillStyle = '#0F0';
            ctx.font = font_size + 'px arial';
            
            for(let i = 0; i < drops.length; i++) {
                const text = matrix[Math.floor(Math.random() * matrix.length)];
                ctx.fillText(text, i * font_size, drops[i] * font_size);
                
                if(drops[i] * font_size > canvas.height && Math.random() > 0.975) {
                    drops[i] = 0;
                }
                drops[i]++;
            }
        }
        
        setInterval(draw, 35);
        
        // Update HUD time
        function updateTime() {
            const now = new Date();
            document.getElementById('time').textContent = now.toLocaleTimeString();
        }
        
        setInterval(updateTime, 1000);
        updateTime();
        
        // Window resize handler
        window.addEventListener('resize', () => {
            canvas.width = window.innerWidth;
            canvas.height = window.innerHeight;
        });
        
        // Add random glitch effects
        setInterval(() => {
            const elements = document.querySelectorAll('.status-line');
            const randomElement = elements[Math.floor(Math.random() * elements.length)];
            randomElement.classList.add('glitch');
            setTimeout(() => {
                randomElement.classList.remove('glitch');
            }, 300);
        }, 3000);
    </script>
</body>
</html>
