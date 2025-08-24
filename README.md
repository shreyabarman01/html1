# html1
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Happy Birthday My Love ❤️</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Arial', sans-serif;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            min-height: 100vh;
            overflow-x: hidden;
            color: white;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 20px;
        }

        .page {
            min-height: 100vh;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            text-align: center;
            padding: 50px 20px;
            opacity: 0;
            transform: translateY(50px);
            transition: all 0.8s ease;
            position: absolute;
            width: 100%;
            top: 0;
            left: 0;
        }

        .page.active {
            opacity: 1;
            transform: translateY(0);
            z-index: 10;
        }

        h1 {
            font-size: 3.5rem;
            margin-bottom: 20px;
            text-shadow: 2px 2px 4px rgba(0,0,0,0.3);
        }

        h2 {
            font-size: 2rem;
            margin-bottom: 15px;
            color: #ffd700;
        }

        p {
            font-size: 1.2rem;
            line-height: 1.6;
            max-width: 600px;
            margin-bottom: 20px;
        }

        .heart {
            color: #ff6b6b;
            font-size: 2rem;
            animation: heartbeat 1.5s infinite;
        }

        @keyframes heartbeat {
            0% { transform: scale(1); }
            50% { transform: scale(1.3); }
            100% { transform: scale(1); }
        }

        .photo-container {
            margin: 30px 0;
            border-radius: 20px;
            overflow: hidden;
            box-shadow: 0 10px 30px rgba(0,0,0,0.3);
            transition: transform 0.3s ease;
            position: relative;
        }

        .photo-container:hover {
            transform: scale(1.05);
        }

        .photo-container img {
            width: 300px;
            height: 300px;
            object-fit: cover;
            display: block;
        }

        .photo-replace-note {
            background: rgba(255, 255, 255, 0.1);
            padding: 10px 20px;
            border-radius: 10px;
            margin-top: 10px;
            border: 2px dashed #ffd700;
            color: #ffd700;
            font-weight: bold;
            cursor: pointer;
            transition: all 0.3s ease;
        }

        .photo-replace-note:hover {
            background: rgba(255, 255, 255, 0.2);
            transform: scale(1.05);
        }

        .candle-container {
            position: relative;
            margin: 40px 0;
        }

        .candle {
            width: 20px;
            height: 100px;
            background: linear-gradient(to bottom, #f8f8f8, #e0e0e0);
            border-radius: 10px 10px 0 0;
            position: relative;
            margin: 0 15px;
            display: inline-block;
        }

        .flame {
            width: 15px;
            height: 30px;
            background: linear-gradient(to bottom, #ffd700, #ff6b6b);
            border-radius: 50% 50% 20% 20%;
            position: absolute;
            top: -35px;
            left: 2.5px;
            animation: flicker 2s infinite;
            box-shadow: 0 0 20px #ffd700, 0 0 40px #ff6b6b;
        }

        @keyframes flicker {
            0%, 100% { transform: scale(1) rotate(0deg); }
            25% { transform: scale(1.1) rotate(2deg); }
            50% { transform: scale(0.9) rotate(-2deg); }
            75% { transform: scale(1.05) rotate(1deg); }
        }

        .cake {
            width: 200px;
            height: 100px;
            background: linear-gradient(to bottom, #f39c12, #e67e22);
            border-radius: 20px 20px 0 0;
            position: relative;
            margin: 40px auto;
        }

        .cake:before {
            content: '';
            position: absolute;
            top: -20px;
            left: 50%;
            transform: translateX(-50%);
            width: 150px;
            height: 40px;
            background: linear-gradient(to bottom, #ff6b6b, #e74c3c);
            border-radius: 20px;
        }

        .frosting {
            position: absolute;
            top: -15px;
            width: 100%;
            height: 20px;
            background: #fff;
            border-radius: 10px;
        }

        .decoration {
            position: absolute;
            top: -25px;
            width: 100%;
            height: 10px;
            background: #ffd700;
            border-radius: 5px;
        }

        .navigation {
            position: fixed;
            bottom: 20px;
            left: 50%;
            transform: translateX(-50%);
            z-index: 100;
            display: flex;
            gap: 10px;
        }

        .nav-btn {
            background: rgba(255, 255, 255, 0.2);
            border: 2px solid white;
            color: white;
            padding: 10px 20px;
            border-radius: 25px;
            cursor: pointer;
            transition: all 0.3s ease;
            font-weight: bold;
        }

        .nav-btn:hover {
            background: rgba(255, 255, 255, 0.4);
            transform: translateY(-2px);
        }

        .confetti {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
            z-index: 9999;
        }

        .message-box {
            background: rgba(255, 255, 255, 0.1);
            padding: 30px;
            border-radius: 20px;
            margin: 20px 0;
            backdrop-filter: blur(10px);
            border: 1px solid rgba(255, 255, 255, 0.2);
        }

        .memories-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 20px;
            margin: 30px 0;
        }

        .memory-card {
            background: rgba(255, 255, 255, 0.1);
            padding: 20px;
            border-radius: 15px;
            backdrop-filter: blur(5px);
            transition: transform 0.3s ease;
        }

        .memory-card:hover {
            transform: translateY(-5px);
        }

        .upload-instructions {
            background: rgba(0, 0, 0, 0.3);
            padding: 15px;
            border-radius: 10px;
            margin: 10px 0;
            font-size: 0.9rem;
        }

        @media (max-width: 768px) {
            h1 {
                font-size: 2.5rem;
            }
            
            h2 {
                font-size: 1.5rem;
            }
            
            .photo-container img {
                width: 250px;
                height: 250px;
            }
        }
    </style>
</head>
<body>
    <div class="confetti" id="confetti"></div>

    <!-- Page 1: Birthday Greeting -->
    <div class="page active" id="page1">
        <div class="container">
            <h1>Happy Birthday <span class="heart">❤️</span></h1>
            <h2>My Beautiful Pasandita Aurat</h2>
            
            <div class="photo-container">
                <!-- REPLACE THIS IMAGE WITH YOUR PHOTO -->
                <img src="C:\Users\Shreya\Downloads\WhatsApp Image 2025-08-24 at 10.23.17 PM.jpeg" alt="Your beautiful smiling face with birthday hat and sparkling eyes" />
                <div class="photo-replace-note" onclick="showUploadInstructions()">
                    ✨ Click here to replace with your special photo ✨
                </div>
            </div>

            <div class="upload-instructions" id="uploadInstructions" style="display: none;">
                <p><strong>How to add your photo:</strong></p>
                <p>1. Right-click on the placeholder image above</p>
                <p>2. Select "Save image as" to download it</p>
                <p>3. Replace the image URL with your photo's URL or path</p>
                <p>4. Save the file and refresh your browser</p>
            </div>
            
            <div class="message-box">
                <p>On this special day, I want you to know how much you mean to me. You light up my world like nobody else.</p>
                <p>May your birthday be as beautiful and wonderful as you are!</p>
            </div>
            
            <div class="candle-container">
                <div class="candle">
                    <div class="flame"></div>
                </div>
                <div class="candle">
                    <div class="flame"></div>
                </div>
                <div class="candle">
                    <div class="flame"></div>
                </div>
            </div>
        </div>
    </div>

    <!-- Page 2: Candle Animation -->
    <div class="page" id="page2">
        <div class="container">
            <h2>Make a Wish! <span class="heart">✨</span></h2>
            
            <div class="photo-container">
                <!-- REPLACE THIS IMAGE WITH YOUR PHOTO BLOWING CANDLES -->
                <img src="https://storage.googleapis.com/workspace-0f70711f-8b4e-4d94-86f1-2a93ccde5887/image/6cbdeb77-f555-4ced-9254-6242813697fe.png" alt="You smiling while blowing birthday candles with eyes closed making a wish" />
                <div class="photo-replace-note">✨ Click here to replace with your candle-blowing moment ✨</div>
            </div>
            
            <div class="candle-container">
                <div class="candle">
                    <div class="flame"></div>
                </div>
                <div class="candle">
                    <div class="flame"></div>
                </div>
                <div class="candle">
                    <div class="flame"></div>
                </div>
                <div class="candle">
                    <div class="flame"></div>
                </div>
                <div class="candle">
                    <div class="flame"></div>
                </div>
            </div>
            
            <div class="message-box">
                <p>Blow out the candles and make your sweetest wish...</p>
                <p>I hope all your dreams come true, my love!</p>
            </div>
        </div>
    </div>

    <!-- Page 3: Birthday Cake -->
    <div class="page" id="page3">
        <div class="container">
            <h2>Your Special Cake <span class="heart">🎂</span></h2>
            
            <div class="cake">
                <div class="frosting"></div>
                <div class="decoration"></div>
            </div>
            
            <div class="photo-container">
                <!-- REPLACE THIS IMAGE WITH YOUR CAKE CELEBRATION PHOTO -->
                <img src="https://storage.googleapis.com/workspace-0f70711f-8b4e-4d94-86f1-2a93ccde5887/image/672b70d2-2ef2-4956-8cba-2895aeca253a.png" alt="You cutting birthday cake with joyful expression and festive background" />
                <div class="photo-replace-note">✨ Click here to replace with your cake-cutting celebration ✨</div>
            </div>
            
            <div class="message-box">
                <p>This cake is as sweet as your smile, but not nearly as sweet as you!</p>
                <p>May your life be filled with sweetness and joy, always.</p>
            </div>
        </div>
    </div>

    <!-- Page 4: Special Memories -->
    <div class="page" id="page4">
        <div class="container">
            <h2>Our Beautiful Memories <span class="heart">📸</span></h2>
            
            <div class="memories-grid">
                <div class="memory-card">
                    <h3>First Meeting</h3>
                    <p>The day my heart found its home in your smile...</p>
                </div>
                
                <div class="memory-card">
                    <h3>Special Moments</h3>
                    <p>Every second with you is a treasure I cherish...</p>
                </div>
                
                <div class="memory-card">
                    <h3>Future Dreams</h3>
                    <p>So many beautiful memories yet to create together...</p>
                </div>
            </div>
            
            <div class="photo-container">
                <!-- REPLACE THESE IMAGES WITH YOUR SPECIAL MEMORIES -->
                <img src="https://storage.googleapis.com/workspace-0f70711f-8b4e-4d94-86f1-2a93ccde5887/image/21da9a70-45c8-4547-9561-7d8b320ea093.png" alt="Couple romantic moment at sunset holding hands on beach" />
                <div class="photo-replace-note">✨ Click here to replace with our special memory photo 1 ✨</div>
            </div>
            
            <div class="photo-container">
                <img src="https://storage.googleapis.com/workspace-0f70711f-8b4e-4d94-86f1-2a93ccde5887/image/309ada01-447d-41f4-ae71-b17a5f6915a7.png" alt="Happy couple laughing together in a beautiful garden setting" />
                <div class="photo-replace-note">✨ Click here to replace with our special memory photo 2 ✨</div>
            </div>
        </div>
    </div>

    <!-- Page 5: Final Wish -->
    <div class="page" id="page5">
        <div class="container">
            <h1>My Final Wish <span class="heart">💝</span></h1>
            
            <div class="photo-container">
                <!-- REPLACE THIS IMAGE WITH YOUR FAVORITE PHOTO TOGETHER -->
                <img src="https://storage.googleapis.com/workspace-0f70711f-8b4e-4d94-86f1-2a93ccde5887/image/da1c8ffd-9c37-43a4-84a8-cd8eb03592d7.png" alt="Romantic couple portrait with loving embrace and happy smiles" />
                <div class="photo-replace-note">✨ Click here to replace with our favorite together photo ✨</div>
            </div>
            
            <div class="message-box">
                <p>My dearest, on your special day, I wish you:</p>
                <p>• Endless happiness and laughter</p>
                <p>• All your dreams come true</p>
                <p>• Love that grows stronger every day</p>
                <p>• Beautiful moments that turn into precious memories</p>
                <p>• And me, always by your side, loving you more each day</p>
            </div>
            
            <h2>Happy Birthday My Love! <span class="heart">🎉</span></h2>
        </div>
    </div>

    <div class="navigation">
        <button class="nav-btn" onclick="prevPage()">Previous</button>
        <button class="nav-btn" onclick="nextPage()">Next</button>
    </div>

    <script>
        let currentPage = 1;
        const totalPages = 5;
        const confettiContainer = document.getElementById('confetti');
        
        function showUploadInstructions() {
            const instructions = document.getElementById('uploadInstructions');
            instructions.style.display = instructions.style.display === 'none' ? 'block' : 'none';
        }

        // Create confetti
        function createConfetti() {
            confettiContainer.innerHTML = '';
            for (let i = 0; i < 100; i++) {
                const confetti = document.createElement('div');
                confetti.style.position = 'absolute';
                confetti.style.width = '10px';
                confetti.style.height = '10px';
                confetti.style.background = `hsl(${Math.random() * 360}, 100%, 50%)`;
                confetti.style.borderRadius = '50%';
                confetti.style.left = `${Math.random() * 100}%`;
                confetti.style.top = '-10px';
                confetti.style.animation = `fall ${Math.random() * 3 + 2}s linear forwards`;
                
                const style = document.createElement('style');
                style.textContent = `
                    @keyframes fall {
                        to {
                            transform: translateY(100vh) rotate(${Math.random() * 360}deg);
                            opacity: 0;
                        }
                    }
                `;
                
                document.head.appendChild(style);
                confettiContainer.appendChild(confetti);
            }
        }

        function showPage(pageNumber) {
            document.querySelectorAll('.page').forEach(page => {
                page.classList.remove('active');
            });
            
            const page = document.getElementById(`page${pageNumber}`);
            page.classList.add('active');
            currentPage = pageNumber;
            
            // Hide instructions when changing pages
            document.getElementById('uploadInstructions').style.display = 'none';
            
            // Add confetti on certain pages
            if ([1, 3, 5].includes(pageNumber)) {
                createConfetti();
            }
        }

        function nextPage() {
            if (currentPage < totalPages) {
                showPage(currentPage + 1);
            } else {
                showPage(1); // Loop back to first page
            }
        }

        function prevPage() {
            if (currentPage > 1) {
                showPage(currentPage - 1);
            } else {
                showPage(totalPages); // Loop to last page
            }
        }

        // Auto-advance pages every 30 seconds
        setInterval(() => {
            if (currentPage < totalPages) {
                nextPage();
            }
        }, 30000);

        // Keyboard navigation
        document.addEventListener('keydown', (e) => {
            if (e.key === 'ArrowRight') nextPage();
            if (e.key === 'ArrowLeft') prevPage();
        });

        // Touch swipe navigation for mobile
        let touchStartX = 0;
        document.addEventListener('touchstart', (e) => {
            touchStartX = e.changedTouches[0].screenX;
        });

        document.addEventListener('touchend', (e) => {
            const touchEndX = e.changedTouches[0].screenX;
            if (touchEndX < touchStartX - 50) {
                nextPage();
            } else if (touchEndX > touchStartX + 50) {
                prevPage();
            }
        });

        // Initial confetti
        createConfetti();
    </script>
</body>
</html>


