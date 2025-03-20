<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Shohrab's Vision Animation</title>
    <style>
        body {
            background-color: black;
            color: white;
            text-align: center;
            overflow: hidden;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            height: 100vh;
            font-family: Arial, sans-serif;
            position: relative;
        }

        #shohrabsVision {
            font-size: 50px;
            font-weight: bold;
            background-image: linear-gradient(45deg, red, orange, yellow, green, blue, indigo, violet);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            text-shadow: 3px 3px 20px rgba(255, 215, 0, 0.8);
            animation: rotateExpand 5s ease-in-out infinite alternate;
        }

        @keyframes rotateExpand {
            0% { transform: rotate(0deg) scale(1); }
            50% { transform: rotate(180deg) scale(2); }
            100% { transform: rotate(360deg) scale(1); }
        }

        #subscribeMessage {
            font-size: 24px;
            font-weight: bold;
            margin-top: 20px;
            opacity: 0;
            animation: fadeMessage 3s infinite alternate;
            background-image: linear-gradient(90deg, red, blue, green, yellow);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }

        @keyframes fadeMessage {
            0% { opacity: 0; transform: scale(1); }
            50% { opacity: 1; transform: scale(1.2); }
            100% { opacity: 0; transform: scale(1); }
        }

        #subscribeButton {
            font-size: 18px;
            font-weight: bold;
            color: white;
            background-color: red;
            padding: 12px 30px;
            border: none;
            border-radius: 50px;
            cursor: pointer;
            position: absolute;
            bottom: 20%;
            left: 50%;
            transform: translate(-50%, -50%);
            transition: transform 0.2s ease, left 0.2s ease, top 0.2s ease;
        }

        #thankYouMessage {
            display: none;
            font-size: 30px;
            font-weight: bold;
            color: gold;
            position: absolute;
            top: 35%;
            left: 50%;
            transform: translate(-50%, -50%);
            animation: blink 1s infinite alternate;
        }

        #thanksMessage {
            display: none;
            font-size: 24px;
            font-weight: bold;
            color: lightgreen;
            position: absolute;
            top: 60%;
            left: 50%;
            transform: translate(-50%, -50%);
        }

        @keyframes blink {
            0% { opacity: 0.2; }
            100% { opacity: 1; }
        }

        .floating-text {
            position: absolute;
            font-size: 14px;
            color: rgba(255, 255, 255, 0.5);
            animation: floatUp 5s linear infinite;
        }

        @keyframes floatUp {
            from { transform: translateY(100vh); opacity: 1; }
            to { transform: translateY(-10vh); opacity: 0; }
        }
    </style>
</head>
<body>
    <div id="shohrabsVision">Shohrab's Vision</div>
    <div id="subscribeMessage">Subscribe for more Informational Videos</div>
    <button id="subscribeButton">SUBSCRIBE NOW</button>
    <div id="thankYouMessage">🎉 स्वागत है हमारे YouTube परिवार में! 🎉</div>
    <div id="thanksMessage">🙏 शुक्रिया दोस्त! 🙏</div>

    <script>
        let clickCount = 0;
        const button = document.getElementById("subscribeButton");
        const thankYouMessage = document.getElementById("thankYouMessage");
        const shohrabsVision = document.getElementById("shohrabsVision");
        const subscribeMessage = document.getElementById("subscribeMessage");
        const thanksMessage = document.getElementById("thanksMessage");

        button.addEventListener("click", function() {
            clickCount++;
            if (clickCount < 3) {
                button.style.left = `${Math.random() * 80 + 10}%`;
                button.style.top = `${Math.random() * 80 + 10}%`;
            } else {
                window.open("https://youtube.com/@shohrabsvision?si=ITs0oOAKwiGJRpiP", "_blank");
                button.style.display = "none";
                subscribeMessage.style.display = "none";
                thankYouMessage.style.display = "block";
                thanksMessage.style.display = "block";
                shohrabsVision.style.animation = "none";
                shohrabsVision.style.textShadow = "0px 0px 30px rgba(255, 255, 0, 1)";
            }
        });

        function createFloatingText() {
            const text = document.createElement("div");
            text.classList.add("floating-text");
            text.textContent = "Shohrab's Vision";
            document.body.appendChild(text);
            text.style.left = `${Math.random() * 100}vw`;
            text.style.top = "100vh";
            setTimeout(() => text.remove(), 5000);
        }

        setInterval(createFloatingText, 500);
    </script>
</body>
</html>
