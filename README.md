<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>BLACK PAPA-BOT | ULTIMATE NEON</title>
    <style>
        /* Full Page Animated RGB Background */
        body {
            background: #000;
            margin: 0;
            padding: 0;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            font-family: 'Orbitron', sans-serif;
            overflow: hidden;
            /* Animated Background Glow */
            box-shadow: inset 0 0 150px rgba(0, 210, 255, 0.2);
        }

        /* Continuous RGB Border Animation for Full Page */
        body::before {
            content: "";
            position: absolute;
            top: 0; left: 0; right: 0; bottom: 0;
            border: 4px solid transparent;
            border-image: linear-gradient(45deg, #ff0000, #00ff00, #0000ff, #ff0000) 1;
            animation: border-glow 3s linear infinite;
            pointer-events: none;
            z-index: 10;
        }

        @keyframes border-glow {
            0% { filter: hue-rotate(0deg); }
            100% { filter: hue-rotate(360deg); }
        }

        /* Glassmorphism Main Card */
        .main-card {
            background: rgba(0, 0, 0, 0.8);
            border: 2px solid rgba(0, 255, 255, 0.5);
            padding: 50px;
            border-radius: 30px;
            text-align: center;
            width: 380px;
            box-shadow: 0 0 50px rgba(0, 255, 255, 0.3), inset 0 0 20px rgba(0, 255, 255, 0.1);
            backdrop-filter: blur(10px);
            position: relative;
            z-index: 5;
        }

        /* Neon Title with Glitch & Glow */
        h1 {
            font-size: 35px;
            color: #fff;
            text-transform: uppercase;
            letter-spacing: 6px;
            margin: 0;
            text-shadow: 0 0 10px #00f2ff, 0 0 20px #00f2ff, 0 0 40px #00f2ff;
            animation: text-pulse 2s infinite alternate;
        }

        @keyframes text-pulse {
            from { transform: scale(1); text-shadow: 0 0 10px #00f2ff; }
            to { transform: scale(1.05); text-shadow: 0 0 30px #ff00c1, 0 0 60px #ff00c1; }
        }

        .status {
            color: #00ff88;
            font-size: 10px;
            margin-bottom: 30px;
            letter-spacing: 4px;
            font-weight: bold;
        }

        /* Cyberpunk Input Box */
        input {
            width: 100%;
            padding: 18px;
            background: rgba(255, 255, 255, 0.05);
            border: 1px solid #00f2ff;
            border-radius: 15px;
            color: #fff;
            font-size: 18px;
            text-align: center;
            outline: none;
            transition: 0.4s;
            box-sizing: border-box;
        }

        input:focus {
            background: rgba(0, 242, 255, 0.1);
            box-shadow: 0 0 20px #00f2ff;
            border-color: #fff;
        }

        /* Ultra Glowing Button */
        button {
            width: 100%;
            padding: 18px;
            margin-top: 30px;
            background: transparent;
            color: #00f2ff;
            border: 2px solid #00f2ff;
            border-radius: 15px;
            font-size: 16px;
            font-weight: bold;
            cursor: pointer;
            text-transform: uppercase;
            letter-spacing: 2px;
            transition: 0.5s;
            position: relative;
            overflow: hidden;
        }

        button:hover {
            background: #00f2ff;
            color: #000;
            box-shadow: 0 0 40px #00f2ff;
            transform: translateY(-5px);
        }

        /* Floating Scanline Effect */
        .scanline {
            width: 100%;
            height: 100px;
            z-index: 2;
            background: linear-gradient(0deg, rgba(0, 255, 255, 0) 0%, rgba(0, 255, 255, 0.1) 50%, rgba(0, 255, 255, 0) 100%);
            opacity: 0.1;
            position: absolute;
            bottom: 100%;
            animation: scanline 4s linear infinite;
        }

        @keyframes scanline {
            0% { bottom: 100%; }
            100% { bottom: -100%; }
        }

        #output {
            margin-top: 25px;
            font-size: 22px;
            font-weight: bold;
            color: #ff00c1;
            text-shadow: 0 0 10px #ff00c1;
        }
    </style>
</head>
<body>

    <div class="scanline"></div>

    <div class="main-card">
        <h1>BLACK PAPA</h1>
        <div class="status">SYSTEM ONLINE • V3.0</div>
        
        <p style="color: #888; font-size: 12px; margin-bottom: 15px;">ENTER PHONE NUMBER WITH COUNTRY CODE</p>
        
        <input type="text" id="phone" placeholder="+8801XXXXXXXXX">
        
        <button onclick="process()">INITIALIZE PAIRING</button>
        
        <div id="output"></div>
        
        <p style="font-size: 9px; color: #444; margin-top: 30px;">© 2026 BLACK PAPA TECH | SECURE ENCRYPTION</p>
    </div>

    <script>
        function process() {
            const input = document.getElementById('phone').value;
            const output = document.getElementById('output');

            if(!input) {
                alert("ERROR: Enter Number First!");
                return;
            }

            output.style.color = "#00f2ff";
            output.innerText = "ACCESSING DATABASE...";

            setTimeout(() => {
                output.style.color = "#ff00c1";
                output.innerText = "WAITING FOR OTP...";
            }, 2000);
        }
    </script>

</body>
</html>
