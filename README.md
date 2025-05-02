<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Happy 21st Birthday My Love!</title>
    <style>
        body {
            font-family: 'Arial', sans-serif;
            background: linear-gradient(135deg, #ff9a9e 0%, #fad0c4 100%);
            margin: 0;
            padding: 0;
            min-height: 100vh;
            display: flex;
            justify-content: center;
            align-items: center;
            color: #333;
            overflow-x: hidden;
        }
        
        .container {
            background-color: rgba(255, 255, 255, 0.9);
            border-radius: 20px;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.2);
            width: 90%;
            max-width: 500px;
            padding: 30px;
            margin: 20px 0;
            position: relative;
            overflow: hidden;
        }
        
        h1 {
            color: #ff6b6b;
            text-align: center;
            margin-bottom: 20px;
            font-size: 28px;
        }
        
        p {
            line-height: 1.6;
            margin-bottom: 15px;
            font-size: 16px;
        }
        
        .heart {
            color: #ff6b6b;
            font-size: 24px;
            display: inline-block;
            animation: pulse 1.5s infinite;
        }
        
        @keyframes pulse {
            0% { transform: scale(1); }
            50% { transform: scale(1.3); }
            100% { transform: scale(1); }
        }
        
        .reasons {
            margin-top: 20px;
            max-height: 300px;
            overflow-y: auto;
            padding-right: 10px;
        }
        
        .reason {
            background-color: rgba(255, 214, 214, 0.3);
            padding: 10px;
            border-radius: 10px;
            margin-bottom: 10px;
            animation: fadeIn 0.5s ease-in;
        }
        
        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(20px); }
            to { opacity: 1; transform: translateY(0); }
        }
        
        .hearts-container {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
            z-index: -1;
        }
        
        .heart-particle {
            position: absolute;
            opacity: 0;
            font-size: 20px;
            animation: float 5s ease-in infinite;
        }
        
        @keyframes float {
            0% { 
                opacity: 0;
                transform: translateY(0) rotate(0deg);
            }
            10% { 
                opacity: 1;
            }
            90% { 
                opacity: 1;
            }
            100% { 
                opacity: 0;
                transform: translateY(-100px) rotate(360deg);
            }
        }
        
        button {
            background-color: #ff6b6b;
            color: white;
            border: none;
            padding: 12px 20px;
            border-radius: 30px;
            font-size: 16px;
            cursor: pointer;
            display: block;
            margin: 30px auto 0;
            transition: all 0.3s;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
        }
        
        button:hover {
            background-color: #ff5252;
            transform: translateY(-2px);
            box-shadow: 0 6px 12px rgba(0, 0, 0, 0.15);
        }
    </style>
</head>
<body>
    <div class="container">
        <div class="hearts-container" id="heartsContainer"></div>
        
        <h1>✨ Happy 21st Birthday My Love! ✨</h1>
        
        <p>To the most amazing girlfriend in the world,</p>
        
        <p>Today we celebrate <span class="heart">❤</span> YOU <span class="heart">❤</span> - the beautiful, wonderful person you are. 21 looks absolutely stunning on you!</p>
        
        <p>Here are 21 reasons why I love you:</p>
        
        <div class="reasons" id="reasonsContainer">
            <!-- Reasons will be added by JavaScript -->
        </div>
        
        <button id="surpriseBtn">Click for a Special Surprise!</button>
    </div>

    <script>
        // Reasons list
        const reasons = [
            "Your smile that brightens my darkest days",
            "The way you make me laugh until my stomach hurts",
            "Your kindness that touches everyone around you",
            "Your intelligence and unique perspective on life",
            "Your passion for the things you care about",
            "How you understand me better than anyone else",
            "Your courage to face any challenge head-on",
            "Your creativity that constantly inspires me",
            "The comfort I feel when I'm with you",
            "Your beautiful heart that loves so deeply",
            "How you make ordinary moments feel magical",
            "Your strength that amazes me every day",
            "Your gorgeous eyes that I could get lost in",
            "The way you always know exactly what to say",
            "Your ambition and determination to chase your dreams",
            "The warmth and safety of your embrace",
            "Your patience with me when I'm being difficult",
            "How you motivate me to be a better person",
            "Your beautiful soul that shines so bright",
            "The way you love me unconditionally",
            "Simply because you're YOU - my perfect match"
        ];

        // Create heart particles
        function createHearts() {
            const container = document.getElementById('heartsContainer');
            const heartIcons = ['❤', '🧡', '💛', '💚', '💙', '💜', '🤎', '🖤', '💖', '💗', '💓', '💞', '💕'];
            
            for (let i = 0; i < 30; i++) {
                const heart = document.createElement('div');
                heart.className = 'heart-particle';
                heart.textContent = heartIcons[Math.floor(Math.random() * heartIcons.length)];
                heart.style.left = Math.random() * 100 + '%';
                heart.style.top = Math.random() * 100 + '%';
                heart.style.animationDelay = Math.random() * 5 + 's';
                heart.style.fontSize = (Math.random() * 20 + 15) + 'px';
                container.appendChild(heart);
            }
        }

        // Display reasons with animation
        function displayReasons() {
            const container = document.getElementById('reasonsContainer');
            
            reasons.forEach((reason, index) => {
                setTimeout(() => {
                    const div = document.createElement('div');
                    div.className = 'reason';
                    div.textContent = `${index + 1}. ${reason}`;
                    container.appendChild(div);
                    
                    // Scroll to bottom
                    container.scrollTop = container.scrollHeight;
                }, index * 500);
            });
        }

        // Surprise button action
        function setupSurpriseButton() {
            const btn = document.getElementById('surpriseBtn');
            btn.addEventListener('click', () => {
                // Create a heart explosion
                const container = document.querySelector('.container');
                const heartIcons = ['❤', '🧡', '💛', '💚', '💙', '💜', '🤎', '🖤', '💖', '💗', '💓', '💞', '💕'];
                
                for (let i = 0; i < 50; i++) {
                    const heart = document.createElement('div');
                    heart.style.position = 'absolute';
                    heart.style.fontSize = (Math.random() * 30 + 20) + 'px';
                    heart.style.color = heartIcons[Math.floor(Math.random() * heartIcons.length)];
                    heart.textContent = heartIcons[Math.floor(Math.random() * heartIcons.length)];
                    heart.style.left = Math.random() * 100 + '%';
                    heart.style.top = Math.random() * 100 + '%';
                    heart.style.animation = 'float 3s ease-out forwards';
                    heart.style.animationDelay = Math.random() * 0.5 + 's';
                    container.appendChild(heart);
                    
                    // Remove heart after animation
                    setTimeout(() => {
                        heart.remove();
                    }, 3000);
                }
                
                // Show final message
                setTimeout(() => {
                    alert("I love you more than words can say!\n\nHappy 21st Birthday my love! ❤️");
                }, 1000);
            });
        }

        // Initialize everything when page loads
        window.onload = function() {
            createHearts();
            displayReasons();
            setupSurpriseButton();
        };
    </script>
</body>
</html>
