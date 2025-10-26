<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Piyush's Animated README</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            background: linear-gradient(135deg, #0d1117 0%, #161b22 100%);
            color: #c9d1d9;
            font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', 'Noto Sans', Helvetica, Arial, sans-serif;
            overflow-x: hidden;
            position: relative;
            min-height: 100vh;
        }

        #particles-container {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
            z-index: 1;
            overflow: hidden;
        }

        .particle {
            position: absolute;
            color: #58a6ff;
            font-family: 'Courier New', monospace;
            font-size: 20px;
            opacity: 0.6;
            animation: fall linear infinite;
        }

        @keyframes fall {
            to {
                transform: translateY(100vh) rotate(360deg);
                opacity: 0;
            }
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 40px 20px;
            position: relative;
            z-index: 2;
        }

        .header {
            text-align: center;
            margin-bottom: 60px;
            animation: fadeInDown 1s ease-out;
        }

        .wave {
            display: inline-block;
            animation: wave 2s ease-in-out infinite;
        }

        @keyframes wave {
            0%, 100% { transform: rotate(0deg); }
            10%, 30% { transform: rotate(14deg); }
            20% { transform: rotate(-8deg); }
            40% { transform: rotate(-4deg); }
            50% { transform: rotate(10deg); }
        }

        .header h1 {
            font-size: 3em;
            margin: 20px 0;
            background: linear-gradient(90deg, #58a6ff, #79c0ff, #a5d6ff);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        .typing-container {
            display: inline-block;
            position: relative;
        }

        .typing-text {
            overflow: hidden;
            border-right: 3px solid #58a6ff;
            white-space: nowrap;
            animation: typing 4s steps(60) infinite, blink 0.75s step-end infinite;
            font-size: 1.2em;
            color: #8b949e;
        }

        @keyframes typing {
            0%, 90%, 100% { width: 0; }
            30%, 60% { width: 100%; }
        }

        @keyframes blink {
            50% { border-color: transparent; }
        }

        @keyframes fadeInDown {
            from {
                opacity: 0;
                transform: translateY(-30px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        .profile-img {
            float: right;
            margin: 0 0 20px 40px;
            border-radius: 15px;
            box-shadow: 0 8px 32px rgba(88, 166, 255, 0.3);
            transition: transform 0.3s ease, box-shadow 0.3s ease;
            animation: floatAnimation 3s ease-in-out infinite;
        }

        @keyframes floatAnimation {
            0%, 100% { transform: translateY(0px); }
            50% { transform: translateY(-20px); }
        }

        .profile-img:hover {
            transform: scale(1.05) translateY(-10px);
            box-shadow: 0 12px 48px rgba(88, 166, 255, 0.5);
        }

        .badges {
            display: flex;
            gap: 10px;
            flex-wrap: wrap;
            margin: 20px 0;
            animation: fadeIn 1.5s ease-out;
        }

        @keyframes fadeIn {
            from { opacity: 0; }
            to { opacity: 1; }
        }

        .section {
            background: rgba(22, 27, 34, 0.6);
            backdrop-filter: blur(10px);
            border: 1px solid #30363d;
            border-radius: 12px;
            padding: 30px;
            margin: 30px 0;
            animation: slideInUp 0.8s ease-out;
            transition: transform 0.3s ease, box-shadow 0.3s ease;
        }

        .section:hover {
            transform: translateY(-5px);
            box-shadow: 0 8px 24px rgba(88, 166, 255, 0.2);
            border-color: #58a6ff;
        }

        @keyframes slideInUp {
            from {
                opacity: 0;
                transform: translateY(30px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        .section h2 {
            color: #58a6ff;
            margin-bottom: 20px;
            font-size: 1.8em;
            position: relative;
            display: inline-block;
        }

        .section h2::after {
            content: '';
            position: absolute;
            bottom: -5px;
            left: 0;
            width: 0;
            height: 3px;
            background: linear-gradient(90deg, #58a6ff, #a5d6ff);
            transition: width 0.5s ease;
        }

        .section:hover h2::after {
            width: 100%;
        }

        table {
            width: 100%;
            border-collapse: collapse;
            margin: 20px 0;
        }

        th, td {
            padding: 15px;
            text-align: left;
            border-bottom: 1px solid #30363d;
        }

        th {
            color: #58a6ff;
            font-weight: 601;
        }

        tr {
            transition: background 0.3s ease;
        }

        tr:hover {
            background: rgba(88, 166, 255, 0.1);
        }

        .tech-badges {
            display: flex;
            flex-wrap: wrap;
            gap: 15px;
            justify-content: center;
            margin: 30px 0;
        }

        .tech-badges img {
            transition: transform 0.3s ease, filter 0.3s ease;
            animation: popIn 0.5s ease-out backwards;
        }

        .tech-badges img:nth-child(1) { animation-delay: 0.1s; }
        .tech-badges img:nth-child(2) { animation-delay: 0.2s; }
        .tech-badges img:nth-child(3) { animation-delay: 0.3s; }
        .tech-badges img:nth-child(4) { animation-delay: 0.4s; }
        .tech-badges img:nth-child(5) { animation-delay: 0.5s; }
        .tech-badges img:nth-child(6) { animation-delay: 0.6s; }
        .tech-badges img:nth-child(7) { animation-delay: 0.7s; }
        .tech-badges img:nth-child(8) { animation-delay: 0.8s; }
        .tech-badges img:nth-child(9) { animation-delay: 0.9s; }

        @keyframes popIn {
            from {
                transform: scale(0);
                opacity: 0;
            }
            to {
                transform: scale(1);
                opacity: 1;
            }
        }

        .tech-badges img:hover {
            transform: scale(1.15) rotate(5deg);
            filter: brightness(1.3) drop-shadow(0 0 10px rgba(88, 166, 255, 0.5));
        }

        .stats-container {
            display: flex;
            justify-content: space-around;
            flex-wrap: wrap;
            gap: 20px;
            margin: 30px 0;
        }

        .stats-container img {
            border-radius: 8px;
            box-shadow: 0 4px 16px rgba(0, 0, 0, 0.3);
            transition: transform 0.3s ease, box-shadow 0.3s ease;
        }

        .stats-container img:hover {
            transform: scale(1.05);
            box-shadow: 0 8px 24px rgba(88, 166, 255, 0.4);
        }

        .connect-btn {
            display: inline-block;
            padding: 12px 30px;
            background: linear-gradient(135deg, #58a6ff, #1f6feb);
            color: white;
            text-decoration: none;
            border-radius: 8px;
            font-weight: 600;
            transition: all 0.3s ease;
            box-shadow: 0 4px 15px rgba(88, 166, 255, 0.3);
            animation: pulse 2s ease-in-out infinite;
        }

        @keyframes pulse {
            0%, 100% { transform: scale(1); }
            50% { transform: scale(1.05); box-shadow: 0 6px 20px rgba(88, 166, 255, 0.5); }
        }

        .connect-btn:hover {
            background: linear-gradient(135deg, #79c0ff, #58a6ff);
            transform: translateY(-3px);
            box-shadow: 0 8px 25px rgba(88, 166, 255, 0.6);
            animation: none;
        }

        hr {
            border: none;
            height: 2px;
            background: linear-gradient(90deg, transparent, #30363d, transparent);
            margin: 40px 0;
        }

        @media (max-width: 768px) {
            .profile-img {
                float: none;
                display: block;
                margin: 20px auto;
            }

            .header h1 {
                font-size: 2em;
            }

            .section {
                padding: 20px;
            }
        }
    </style>
</head>
<body>
    <div id="particles-container"></div>

    <div class="container">
        <div class="header">
            <h1><span class="wave">👋</span> Hey there! I'm Piyush</h1>
            <div class="typing-container">
                <h3 class="typing-text">A computer science student passionate about AI/ML & software development from India</h3>
            </div>
        </div>

        <img class="profile-img" alt="coding" width="400" src="https://raw.githubusercontent.com/rajpratyush/rajpratyush/master/me_1.gif" />

        <div class="badges">
            <img src="https://komarev.com/ghpvc/?username=piyush-nextgen&label=Profile%20views&color=0e75b6&style=flat" alt="piyush-nextgen" />
            <img src="https://img.shields.io/github/followers/piyush-nextgen?label=Followers&style=social" alt="GitHub Followers" />
            <img src="https://img.shields.io/github/stars/piyush-nextgen?label=Stars&style=social" alt="GitHub Stars" />
        </div>

        <hr>

        <div class="section">
            <h2>🌐 Connect with me</h2>
            <p>
                <a class="connect-btn" href="https://www.linkedin.com/in/piyush-baraskar-994ab6337" target="_blank">
                    Let's Connect on LinkedIn
                </a>
            </p>
        </div>

        <hr>

        <div class="section">
            <h2>⚡ Technical Skills</h2>
            <table>
                <tr>
                    <th>Category</th>
                    <th>Tools/Technologies</th>
                </tr>
                <tr>
                    <td>Programming</td>
                    <td>C++, Python <em>(learning DSA)</em></td>
                </tr>
                <tr>
                    <td>Tools & IDEs</td>
                    <td>VS Code, PyCharm</td>
                </tr>
                <tr>
                    <td>Version Control</td>
                    <td>Git, GitHub</td>
                </tr>
                <tr>
                    <td>Community</td>
                    <td>Stack Overflow, Geeksforgeeks, Discord, LeetCode</td>
                </tr>
                <tr>
                    <td>CS Fundamentals</td>
                    <td>OOP, Data Structures <em>(learning)</em></td>
                </tr>
                <tr>
                    <td>Future Stack (AI/ML)</td>
                    <td>Flask, NumPy, Pandas, TensorFlow <em>(planned)</em></td>
                </tr>
            </table>
        </div>

        <hr>

        <div class="section">
            <h2>🛠️ Tech Stack</h2>
            <div class="tech-badges">
                <img src="https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white" alt="Python" />
                <img src="https://img.shields.io/badge/C++-00599C?style=for-the-badge&logo=cplusplus&logoColor=white" alt="C++" />
                <img src="https://img.shields.io/badge/Stack%20Overflow-FE7A16?style=for-the-badge&logo=stackoverflow&logoColor=white" alt="Stack Overflow" />
                <img src="https://img.shields.io/badge/VS%20Code-007ACC?style=for-the-badge&logo=visualstudiocode&logoColor=white" alt="VS Code" />
                <img src="https://img.shields.io/badge/PyCharm-000000?style=for-the-badge&logo=pycharm&logoColor=white" alt="PyCharm" />
                <img src="https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=github&logoColor=white" alt="GitHub" />
                <img src="https://img.shields.io/badge/Windows-0078D6?style=for-the-badge&logo=windows&logoColor=white" alt="Windows" />
                <img src="https://img.shields.io/badge/GeeksforGeeks-0F9D58?style=for-the-badge&logo=geeksforgeeks&logoColor=white" alt="GeeksforGeeks" />
                <img src="https://img.shields.io/badge/LeetCode-FFA116?style=for-the-badge&logo=leetcode&logoColor=white" alt="LeetCode" />
            </div>
        </div>

        <hr>

        <div class="section">
            <h2>📊 GitHub Stats</h2>
            <div class="stats-container">
                <img width="47%" src="https://github-readme-stats.vercel.app/api/top-langs?username=piyush-nextgen&show_icons=true&locale=en&layout=compact&count_private=true&theme=dark" alt="Top Languages" />
                <img width="47%" src="https://github-readme-stats.vercel.app/api?username=piyush-nextgen&show_icons=true&locale=en&count_private=true&include_all_commits=true&theme=dark" alt="GitHub Stats" />
            </div>
            <div class="stats-container">
                <img src="https://github-readme-streak-stats.herokuapp.com/?user=piyush-nextgen&theme=dark" alt="GitHub Streak" />
            </div>
        </div>

        <hr>

        <div class="section">
            <h2>📈 My GitHub Activity</h2>
            <div style="text-align: center;">
                <img style="width: 100%; max-width: 900px;" src="https://github-readme-activity-graph.vercel.app/graph?username=piyush-nextgen&theme=react-dark" alt="Activity Graph" />
            </div>
        </div>

        <div style="text-align: center; margin: 40px 0; font-size: 1.1em;">
            📫 Reach me via <a href="https://www.linkedin.com/in/piyush-baraskar-994ab6337" style="color: #58a6ff; text-decoration: none;">LinkedIn</a>
        </div>
    </div>

    <script>
        // Falling code particles
        const symbols = ['{', '}', '<', '>', '/', '*', '+', '-', '=', ';', '(', ')', '[', ']', '0', '1'];
        const container = document.getElementById('particles-container');

        function createParticle() {
            const particle = document.createElement('div');
            particle.className = 'particle';
            particle.textContent = symbols[Math.floor(Math.random() * symbols.length)];
            particle.style.left = Math.random() * 100 + '%';
            particle.style.animationDuration = (Math.random() * 3 + 4) + 's';
            particle.style.animationDelay = Math.random() * 2 + 's';
            particle.style.fontSize = (Math.random() * 10 + 15) + 'px';
            container.appendChild(particle);

            setTimeout(() => {
                particle.remove();
            }, 7000);
        }

        // Create particles periodically
        setInterval(createParticle, 300);

        // Create initial batch
        for (let i = 0; i < 15; i++) {
            setTimeout(createParticle, i * 200);
        }
    </script>
</body>
</html>