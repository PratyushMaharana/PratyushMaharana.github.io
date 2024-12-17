# PratyushMaharana.github.io
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>THE NEXT AGI</title>
    <style>
        /* General Styles */
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
            background: #121212; /* Dark background */
            color: #ffffff; /* Light text color */
            line-height: 1.6;
        }

        /* Header Section */
        header {
            background: #1f1f1f;
            color: #00ffcc; /* Futuristic neon color */
            padding: 1rem 0;
            text-align: center;
        }

        header h1 {
            margin: 0;
        }

        header nav ul {
            list-style: none;
            padding: 0;
        }

        header nav ul li {
            display: inline;
            margin: 0 10px;
        }

        header nav ul li a {
            color: #00ffcc;
            text-decoration: none;
        }

        /* Section Styles */
        section {
            padding: 20px;
            margin: 20px;
            background: #1f1f1f; /* Slightly lighter dark for contrast */
            border-radius: 10px;
            box-shadow: 0 4px 15px rgba(0, 255, 204, 0.2); /* Futuristic glow */
        }

        /* Tesseract Animation Section */
        .tesseract {
            display: flex;
            justify-content: center;
            align-items: center;
            height: 300px;
            perspective: 1000px;
        }

        .tesseract-box {
            width: 100px;
            height: 100px;
            position: relative;
            transform-style: preserve-3d;
            animation: rotate 8s infinite linear;
        }

        .tesseract-box div {
            position: absolute;
            width: 100%;
            height: 100%;
            background: rgba(0, 255, 204, 0.2);
            border: 2px solid #00ffcc;
            box-shadow: 0 0 10px #00ffcc, 0 0 20px #00ffcc;
        }

        .tesseract-box .front { transform: rotateY(0deg) translateZ(50px); }
        .tesseract-box .back { transform: rotateY(180deg) translateZ(50px); }
        .tesseract-box .left { transform: rotateY(-90deg) translateZ(50px); }
        .tesseract-box .right { transform: rotateY(90deg) translateZ(50px); }
        .tesseract-box .top { transform: rotateX(90deg) translateZ(50px); }
        .tesseract-box .bottom { transform: rotateX(-90deg) translateZ(50px); }

        @keyframes rotate {
            0% { transform: rotateX(0deg) rotateY(0deg); }
            50% { transform: rotateX(180deg) rotateY(180deg); }
            100% { transform: rotateX(360deg) rotateY(360deg); }
        }

        /* Footer Section */
        footer {
            text-align: center;
            padding: 10px 0;
            background: #1f1f1f;
            color: #00ffcc;
        }
    </style>
</head>
<body>
    <header>
        <h1>Welcome to THE NEXT AGI</h1>
        <nav>
            <ul>
                <li><a href="#about">About</a></li>
                <li><a href="#projects">Projects</a></li>
                <li><a href="#contact">Contact</a></li>
            </ul>
        </nav>
    </header>

    <section id="about">
        <h2>About Me</h2>
        <p>Making AGI as I am in high school learning programming languages and cybersecurity. My main goal is to create my own Artificial General Intelligence (AGI) someday.</p>
        <div class="tesseract">
            <div class="tesseract-box">
                <div class="front"></div>
                <div class="back"></div>
                <div class="left"></div>
                <div class="right"></div>
                <div class="top"></div>
                <div class="bottom"></div>
            </div>
        </div>
    </section>

    <section id="projects">
        <h2>Projects</h2>
        <ul id="repo-list">
            <!-- Repositories will be dynamically loaded here -->
        </ul>
    </section>

    <section id="contact">
        <h2>Contact</h2>
        <form>
            <label for="name">Name:</label>
            <input type="text" id="name" name="name" required>
            
            <label for="email">Email:</label>
            <input type="email" id="email" name="email" required>
            
            <label for="message">Message:</label>
            <textarea id="message" name="message" rows="4" required></textarea>
            
            <button type="submit">Send</button>
        </form>
    </section>

    <footer>
        <p>© 2024 THE NEXT AGI. All rights reserved.</p>
    </footer>

    <script>
        // Fetch and display GitHub repositories
        fetch('https://api.github.com/users/YOUR_GITHUB_USERNAME/repos')
            .then(response => response.json())
            .then(data => {
                const repoList = document.getElementById('repo-list');
                data.forEach(repo => {
                    const listItem = document.createElement('li');
                    const link = document.createElement('a');
                    link.href = repo.html_url;
                    link.target = '_blank';
                    link.textContent = repo.name;
                    listItem.appendChild(link);
                    repoList.appendChild(listItem);
                });
            })
            .catch(error => console.error('Error fetching repositories:', error));
    </script>
</body>
</html>
