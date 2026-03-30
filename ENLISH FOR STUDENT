<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>EduApp - English Lesson</title>
    <style>
        :root {
            --primary: #2563eb;
            --success: #16a34a;
            --danger: #dc2626;
            --bg: #f8fafc;
            --text: #1e293b;
        }
        
        * { margin: 0; padding: 0; box-sizing: border-box; }
        
        body { 
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif; 
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: var(--text);
            line-height: 1.6;
            padding: 20px;
            min-height: 100vh;
        }
        
        .container { 
            max-width: 750px; 
            margin: auto; 
            background: white; 
            padding: 40px; 
            border-radius: 15px; 
            box-shadow: 0 10px 40px rgba(0,0,0,0.2);
        }
        
        h1 { 
            color: var(--primary); 
            border-bottom: 3px solid var(--primary); 
            padding-bottom: 15px; 
            margin-bottom: 10px;
            font-size: 2.5em;
        }
        
        .progress-bar {
            width: 100%;
            height: 8px;
            background: #e2e8f0;
            border-radius: 10px;
            margin-bottom: 30px;
            overflow: hidden;
        }
        
        .progress-fill {
            height: 100%;
            background: linear-gradient(90deg, var(--primary), var(--success));
            width: 0%;
            transition: width 0.3s ease;
        }
        
        .stats {
            display: flex;
            justify-content: space-around;
            margin-bottom: 30px;
            text-align: center;
        }
        
        .stat-box {
            flex: 1;
            padding: 15px;
            background: #f1f5f9;
            border-radius: 8px;
            margin: 0 5px;
        }
        
        .stat-label { font-size: 0.9em; color: #64748b; text-transform: uppercase; }
        .stat-value { font-size: 1.8em; font-weight: bold; color: var(--primary); }
        
        .lesson-box { 
            background: linear-gradient(135deg, #eff6ff 0%, #dbeafe 100%);
            padding: 20px; 
            border-left: 5px solid var(--primary); 
            margin-bottom: 30px;
            border-radius: 8px;
        }
        
        .lesson-box h3 { color: var(--primary); margin-bottom: 10px; }
        .lesson-box ul { margin-left: 20px; }
        .lesson-box li { margin-bottom: 8px; }
        
        .quiz-section { margin-top: 30px; }
        .quiz-section h3 { color: var(--primary); margin-bottom: 20px; }
        
        .question-container {
            background: #f9fafb;
            padding: 20px;
            margin-bottom: 20px;
            border-radius: 10px;
            border-left: 4px solid var(--primary);
        }
        
        .question { 
            font-weight: 700; 
            margin-bottom: 15px; 
            display: block;
            font-size: 1.1em;
        }
        
        .options {
            display: flex;
            flex-direction: column;
            gap: 10px;
        }
        
        .option-label {
            display: flex;
            align-items: center;
            padding: 10px;
            background: white;
            border: 2px solid #e2e8f0;
            border-radius: 6px;
            cursor: pointer;
            transition: all 0.3s ease;
        }
        
        .option-label:hover {
            background: #f0f9ff;
            border-color: var(--primary);
        }
        
        input[type="radio"] {
            margin-right: 10px;
            cursor: pointer;
            width: 18px;
            height: 18px;
        }
        
        .button-group {
            display: flex;
            gap: 10px;
            margin-top: 30px;
        }
        
        button { 
            flex: 1;
            background: var(--primary); 
            color: white; 
            border: none; 
            padding: 14px 28px; 
            border-radius: 8px; 
            cursor: pointer; 
            font-size: 16px;
            font-weight: 600;
            transition: all 0.3s ease;
        }
        
        button:hover { 
            background: #1d4ed8;
            transform: translateY(-2px);
            box-shadow: 0 5px 15px rgba(37, 99, 235, 0.3);
        }
        
        button:active { transform: translateY(0); }
        
        .reset-btn {
            background: #6b7280;
        }
        
        .reset-btn:hover {
            background: #4b5563;
        }
        
        #result { 
            margin-top: 30px; 
            padding: 25px; 
            display: none; 
            text-align: center; 
            border-radius: 10px; 
            font-weight: bold;
            font-size: 1.2em;
            animation: slideIn 0.4s ease;
        }
        
        @keyframes slideIn {
            from {
                opacity: 0;
                transform: translateY(-10px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }
        
        .success { 
            background: linear-gradient(135deg, #dcfce7 0%, #bbf7d0 100%);
            color: #166534;
            border: 2px solid var(--success);
        }
        
        .retry { 
            background: linear-gradient(135deg, #fee2e2 0%, #fecaca 100%);
            color: #991b1b;
            border: 2px solid var(--danger);
        }
        
        .feedback {
            margin-top: 20px;
            padding: 15px;
            background: rgba(255,255,255,0.3);
            border-radius: 8px;
            font-size: 0.95em;
        }
        
        .hidden { display: none !important; }
    </style>
</head>
<body>

<div class="container">
    <h1>🎓 EduApp: English Learning</h1>
    
    <div class="progress-bar">
        <div class="progress-fill" id="progressFill"></div>
    </div>
    
    <div class="stats">
        <div class="stat-box">
            <div class="stat-label">Score</div>
            <div class="stat-value" id="score">0</div>
        </div>
        <div class="stat-box">
            <div class="stat-label">Attempts</div>
            <div class="stat-value" id="attempts">0</div>
        </div>
        <div class="stat-box">
            <div class="stat-label">Best Score</div>
            <div class="stat-value" id="bestScore">0</div>
        </div>
    </div>

    <div class="lesson-box">
        <h3>📚 Step 1: The Present Simple (Habits)</h3>
        <p>In English, we use the <b>Present Simple</b> for daily routines and general truths.</p>
        <ul>
            <li><b>I / You / We / They</b> + Base Verb (ex: I <i>play</i>, you <i>work</i>)</li>
            <li><b>He / She / It</b> + Verb + S (ex: He <i>plays</i>, she <i>works</i>)</li>
        </ul>
        <p style="margin-top: 10px; color: #475569;"><i>💡 Tip: After third person singular (he, she, it), always add 's' to the verb!</i></p>
    </div>

    <div class="quiz-section">
        <h3>✍️ Step 2: Quick Quiz</h3>
        
        <div class="question-container">
            <span class="question">1. Sarah ___ coffee every morning.</span>
            <div class="options">
                <label class="option-label">
                    <input type="radio" name="q1" value="wrong">
                    <span>drink</span>
                </label>
                <label class="option-label">
                    <input type="radio" name="q1" value="correct">
                    <span>drinks</span>
                </label>
            </div>
        </div>

        <div class="question-container">
            <span class="question">2. We ___ to the gym on Saturdays.</span>
            <div class="options">
                <label class="option-label">
                    <input type="radio" name="q2" value="correct">
                    <span>go</span>
                </label>
                <label class="option-label">
                    <input type="radio" name="q2" value="wrong">
                    <span>goes</span>
                </label>
            </div>
        </div>

        <div class="question-container">
            <span class="question">3. Do you ___ English?</span>
            <div class="options">
                <label class="option-label">
                    <input type="radio" name="q3" value="correct">
                    <span>speak</span>
                </label>
                <label class="option-label">
                    <input type="radio" name="q3" value="wrong">
                    <span>speaks</span>
                </label>
            </div>
        </div>

        <div class="button-group">
            <button onclick="checkScore()">📤 Submit My Answers</button>
            <button class="reset-btn" onclick="resetQuiz()">🔄 Reset Quiz</button>
        </div>
    </div>

    <div id="result"></div>
</div>

<script>
    // Initialize stats from localStorage
    function initializeStats() {
        const savedStats = JSON.parse(localStorage.getItem('quizStats')) || {
            attempts: 0,
            bestScore: 0,
            currentScore: 0
        };
        
        document.getElementById('attempts').textContent = savedStats.attempts;
        document.getElementById('bestScore').textContent = savedStats.bestScore;
        return savedStats;
    }
    
    let stats = initializeStats();
    
    function checkScore() {
        let score = 0;
        const total = 3;
        const answers = document.querySelectorAll('input[type="radio"]:checked');

        if (answers.length < total) {
            alert("⚠️ Please answer all questions first!");
            return;
        }

        answers.forEach(answer => {
            if (answer.value === "correct") {
                score++;
            }
        });

        // Update stats
        stats.attempts++;
        stats.currentScore = score;
        
        if (score > stats.bestScore) {
            stats.bestScore = score;
        }
        
        localStorage.setItem('quizStats', JSON.stringify(stats));
        
        // Update UI
        document.getElementById('score').textContent = score;
        document.getElementById('attempts').textContent = stats.attempts;
        document.getElementById('bestScore').textContent = stats.bestScore;
        
        // Update progress bar
        const progress = (score / total) * 100;
        document.getElementById('progressFill').style.width = progress + '%';

        const resultDiv = document.getElementById('result');
        resultDiv.style.display = 'block';
        
        let emoji = "";
        let message = "";
        let feedback = "";
        
        if (score === total) {
            resultDiv.className = "success";
            emoji = "🎉";
            message = `Perfect! Your score is ${score}/${total}. You are a pro!`;
            feedback = "Excellent work! You've mastered the Present Simple. Keep it up!";
        } else if (score === 2) {
            resultDiv.className = "retry";
            emoji = "👍";
            message = `Good! You got ${score}/${total}. Almost there!`;
            feedback = "You're on the right track. Review the rules and try again!";
        } else if (score === 1) {
            resultDiv.className = "retry";
            emoji = "📖";
            message = `You got ${score}/${total}. Keep practicing!`;
            feedback = "Don't give up! Read the lesson again and try once more.";
        } else {
            resultDiv.className = "retry";
            emoji = "💪";
            message = `You got ${score}/${total}. Try again!`;
            feedback = "Review the Present Simple rules carefully and attempt the quiz again!";
        }
        
        resultDiv.innerHTML = `
            <div>${emoji}</div>
            <div style="margin: 15px 0;">${message}</div>
            <div class="feedback">${feedback}</div>
        `;
    }
    
    function resetQuiz() {
        // Clear all radio buttons
        document.querySelectorAll('input[type="radio"]').forEach(radio => {
            radio.checked = false;
        });
        
        // Hide result
        document.getElementById('result').style.display = 'none';
        
        // Reset progress bar
        document.getElementById('progressFill').style.width = '0%';
        
        // Reset current score display
        document.getElementById('score').textContent = '0';
        
        alert("✅ Quiz reset! Ready for a new attempt?");
    }
</script>

</body>
</html>
