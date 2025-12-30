https://fonts.googleapis.com/css2?family=Poppins:wght@400;600;700&display=swap<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Happy Birthday!</title>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Poppins:wght@400;600;700&display=swap');
        body {
            margin: 0;
            font-family: 'Poppins', sans-serif;
            background: linear-gradient(135deg, #fce4ec, #e3f2fd, #e8f5e9);
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            color: #444;
            overflow: hidden;
        }
        .container {
            width: 90%;
            max-width: 400px;
            /* Changed background to be slightly more opaque for better contrast */
            background: #fffffff5; 
            border-radius: 25px; /* Slightly more rounded */
            padding: 25px;
            text-align: center;
            box-shadow: 0 15px 40px rgba(0,0,0,0.15); /* More prominent shadow */
            backdrop-filter: blur(5px);
            animation: fadeIn 1s ease-out; /* New: Container fade in */
        }
        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(20px); }
            to { opacity: 1; transform: translateY(0); }
        }
        .hidden {
            display: none;
        }
        .cake {
            font-size: 85px; /* Slightly bigger */
            animation: float 2s infinite ease-in-out;
        }
        @keyframes float {
            0%, 100% { transform: translateY(0) rotate(0deg); }
            50% { transform: translateY(-12px) rotate(-1deg); } /* Added slight rotation */
        }
        .candle {
            font-size: 70px; /* Bigger candle */
            cursor: pointer;
            margin-top: 15px;
            transition: transform 0.3s;
            animation: pulse 1.5s infinite; /* New: Candle pulse effect */
        }
        @keyframes pulse {
            0%, 100% { filter: drop-shadow(0 0 5px orange); }
            50% { filter: drop-shadow(0 0 10px yellow); }
        }
        .candle:hover {
            transform: scale(1.1);
        }
        .btn {
            margin-top: 20px;
            padding: 12px 25px; /* Larger button */
            border: none;
            border-radius: 30px;
            background: #ffc4e1; /* Lighter pink button */
            color: #333;
            font-size: 18px;
            cursor: pointer;
            transition: all 0.3s;
            font-weight: 700;
        }
        .btn:hover {
            background: #f48fb1;
            box-shadow: 0 5px 15px rgba(244, 143, 177, 0.4);
            transform: translateY(-2px);
        }
        .card {
            max-height: 60vh;
            overflow-y: auto;
            text-align: left;
            font-size: 15px;
            line-height: 1.7;
            padding: 15px;
            border-radius: 15px;
            background: #ffebee; /* Very light pink background for card */
            box-shadow: inset 0 0 8px rgba(0,0,0,0.1);
            border: 1px solid #f8bbd0;
        }
        .love {
            font-size: 60px; /* Much bigger "I Love You" */
            color: #e91e63;
            text-align: center;
            animation: heartbeat 1.5s infinite;
            font-weight: 700;
            margin: 20px 0;
            text-shadow: 2px 2px 5px rgba(0,0,0,0.1);
        }
        @keyframes heartbeat {
            0%, 100% { transform: scale(1); }
            50% { transform: scale(1.15); } /* Stronger beat */
        }
        
    </style>
    <script src="https://cdn.jsdelivr.net/npm/canvas-confetti@1.9.3/dist/confetti.browser.min.js"></script>
</head>
<body>
    <div class="container">
        <div id="step1">
            <div class="cake">🎂</div>
            <h2>Aaj kisi khaas ka birthday hai ✨</h2>
            <button class="btn" onclick="nextStep(2)">Next</button>
        </div>

        <div id="step2" class="hidden">
            <div class="candle" onclick="blowCandle()">🕯️</div>
            <p>Candle par tap karo aur blow karo 💨</p>
        </div>

        <div id="step3" class="hidden">
            <h3>💌 My Letter For You</h3>
            <div class="card">
                <p> Aaj ka din mere liye bohot special hai, kyun ke aaj wo shakhs paida hua jis ne meri zindagi ko aur bhi khoobsurat bana diya. Tum sirf mere boyfriend nahi ho, tum meri strength ho, meri smile ki wajah ho, aur meri har dua ka hissa ho. </p>
                <p> Tumhara hona mujhe yeh ehsaas dilata hai ke pyaar sirf lafzon ka naam nahi, balkay care, respect aur samajhne ka bhi hota hai. Tum meri baat bina kahe samajh lete ho, aur mushkil waqt mein bhi mera saath nibhaate ho — is ke liye main hamesha shukar guzar rahungi. </p>
                <p> Main dua karti hoon ke Allah tumhein hamesha khush rakhe, tumhare har sapne ko poora kare, aur tumhein har buri nazar se mehfooz rakhe. Tumhari zindagi mein success, sukoon aur bohot saari muskurahatein hon — aur un muskurahaton ki wajah main bhi banoon 💫 </p>
                <p> On your birthday, I want to take a moment to appreciate the person you are and the journey you are on. You have a way of facing life with quiet strength and determination, even when things are not easy. I admire how you stay focused on your goals, how you learn from your mistakes, and how you never stop trying to become better than yesterday. </p>
                <p> This year, I hope life opens new doors for you — opportunities that challenge you, experiences that help you grow, and moments that remind you of your true worth. No matter where life takes you, I hope you always believe in yourself the way I believe in you. </p>
            </div>
            <button class="btn" onclick="nextStep(4)">Next</button>
        </div>

        <div id="step4" class="hidden">
            <div class="love">I ❤️ You</div>
            <p>Happy Birthday, My Person 🎀</p>
            <button class="btn" onclick="restart()">Restart</button>
        </div>
    </div>
    <div id="confetti"></div>


    <script>
        function nextStep(step) {
            // Hide all steps
            document.getElementById('step1').classList.add('hidden');
            document.getElementById('step2').classList.add('hidden');
            document.getElementById('step3').classList.add('hidden');
            document.getElementById('step4').classList.add('hidden');

            // Show the current step with a fade-in effect
            const nextElement = document.getElementById('step' + step);
            if (nextElement) {
                // Remove the hidden class to show it
                nextElement.classList.remove('hidden'); 
            }

            if (step === 4) {
                // Confetti animation on the final step
                confetti({
                    particleCount: 150, // More confetti!
                    spread: 90,
                    origin: { y: 0.6 }
                });
            }
        }

        function blowCandle() {
            const candle = document.querySelector('.candle');
            // Quick transition to blow
            candle.textContent = '💨';

            // Add an extra little visual shake for impact
            candle.style.animation = 'none';
            candle.offsetHeight; // Trigger reflow
            candle.style.animation = 'shake 0.2s ease-in-out';

            setTimeout(() => {
                candle.textContent = '🕯️'; // Change back 
                candle.style.animation = 'pulse 1.5s infinite'; // Resume pulse (or remove if you prefer no animation after blow)
                nextStep(3);
            }, 500);
        }
        
        // New animation for the shake effect
        const style = document.createElement('style');
        style.textContent = `
            @keyframes shake {
                0% { transform: translateX(0); }
                25% { transform: translateX(-5px); }
                50% { transform: translateX(5px); }
                75% { transform: translateX(-5px); }
                100% { transform: translateX(0); }
            }
        `;
        document.head.appendChild(style);

        function restart() {
            nextStep(1);
        }

        window.onload = () => {
            document.getElementById('step1').classList.remove('hidden');
        };
    </script>
</body>
</html>
