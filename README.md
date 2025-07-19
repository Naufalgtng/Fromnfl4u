```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Hujan Love ❤️</title>
    <style>
        body {
            margin: 0;
            padding: 0;
            overflow: hidden;
            background-color: #ffcce6;
            font-family: 'Arial', sans-serif;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            height: 100vh;
        }

        .container {
            position: relative;
            width: 100%;
            height: 100%;
            display: flex;
            justify-content: center;
            align-items: center;
        }

        .signature {
            position: absolute;
            bottom: 20px;
            color: #ff3399;
            font-weight: bolder;
            font-size: 28px;
            text-shadow: 0 0 10px white;
            z-index: 100;
            animation: glow 1.5s ease-in-out infinite alternate;
        }

        @keyframes glow {
            from {
                text-shadow: 0 0 5px rgba(255, 0, 0, 0.7);
            }
            to {
                text-shadow: 0 0 15px rgba(255, 0, 0, 1), 0 0 20px rgba(255, 0, 0, 0.7);
            }
        }

        .heart {
            position: absolute;
            pointer-events: none;
            animation: fall linear infinite;
        }

        @keyframes fall {
            to {
                transform: translateY(100vh);
            }
        }

        .message {
            color: #fff;
            font-size: 2.5rem;
            margin-bottom: 50px;
        }
        
        .falling-text {
            position: absolute;
            top: -50px;
            font-size: 30px;
            color: #cc0066;
            text-shadow: 0 0 12px #fff;
            font-weight: bolder;
            animation: text-fall linear;
            opacity: 0.85;
            transition: all 0.3s;
            transform: rotate(-5deg);
            font-family: 'Arial Black', sans-serif;
        }
            text-align: center;
            margin-bottom: 30px;
            text-shadow: 0 0 15px rgba(0, 0, 0, 0.7);
            z-index: 10;
            font-weight: bold;
        }

        .heart-icon {
            font-size: 1.5rem;
            animation: pulse 1.5s infinite;
            margin: 0 5px;
        }

        @keyframes pulse {
            0% {
                transform: scale(1);
            }
            50% {
                transform: scale(1.3);
            }
            100% {
                transform: scale(1);
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <div class="message"></div>
        <div class="signature" style="font-size:32px;">For Ditaa</div>
        <div id="text-rain"></div>
    </div>

    <script>
        document.addEventListener('DOMContentLoaded', function() {
            const container = document.querySelector('.container');
            
            function createHeart() {
                const heart = document.createElement('div');
                heart.classList.add('heart');
                heart.innerHTML = '❤️';
                
                // Random size between 10px and 30px
                const size = Math.random() * 20 + 10;
                heart.style.fontSize = `${size}px`;
                
                // Random color with higher chance of pink/red
                const colors = ['#ff66b2', '#ff3399', '#ff99cc', '#ff0080', '#ff99aa'];
                const color = colors[Math.floor(Math.random() * colors.length)];
                heart.style.color = color;
                
                // Random starting position
                heart.style.left = `${Math.random() * 100}vw`;
                heart.style.top = '-30px';
                
                // Random animation duration between 5s and 15s
                const duration = Math.random() * 10 + 5;
                heart.style.animationDuration = `${duration}s`;
                
                container.appendChild(heart);
                
                // Remove heart after animation completes
                setTimeout(() => {
                    heart.remove();
                }, duration * 1000);
            }
            
            // Create initial hearts
            for (let i = 0; i < 20; i++) {
                setTimeout(createHeart, i * 300);
            }
            
            // Create text rain
            function createTextRain() {
                const texts = ['Ditaa ❤️', 'Ditaa', 'D I T A A', 'For Ditaa', 'Ditaa Love'];
                const textElement = document.createElement('div');
                textElement.classList.add('falling-text');
                textElement.textContent = texts[Math.floor(Math.random() * texts.length)];
                
                // Random position and animation
                textElement.style.left = `${Math.random() * 90 + 5}vw`;
                textElement.style.animationDuration = `${Math.random() * 10 + 8}s`;
                
                document.getElementById('text-rain').appendChild(textElement);
                
                // Remove after animation
                setTimeout(() => {
                    textElement.remove();
                }, 8000);
            }
            
            // Continue creating hearts and text
            setInterval(createHeart, 300);
            setInterval(createTextRain, 800);
            
            // Add animation for text rain
            const style = document.createElement('style');
            style.textContent = `@keyframes text-fall { to { transform: translateY(110vh); } }`;
            document.head.appendChild(style);
        });
    </script>
</body>
</html>
```
