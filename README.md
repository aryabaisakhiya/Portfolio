# Ex01 Portfolio
## Date:

## AIM
To create a Portfolio using HTML and CSS.

## ALGORITHM
### STEP 1
Create an HTML file (index.html)

### STEP 2
Create a CSS file (style.css)

### STEP 3
Include a navigation bar with links to different sections.

### STEP 4
Add structured sections for introduction, about, projects, and contact details.

### STEP 5
Define global styles for fonts, colors, and layout.

### STEP 6
Style the header, navigation bar, and sections.

### STEP 7
Use Flexbox or CSS Grid for layout design.

### STEP 8
Add hover effects and transitions for interactivity.

### STEP 9
Add Images and Media.

### STEP 10
Use optimized images for a professional look.

### STEP 11
Open the HTML file in a browser to check layout and functionality.

### STEP 12
Fix styling issues and refine content placement.

### STEP 13
Deploy the Portfolio.

### STEP 14
Upload to GitHub Pages for free hosting.

## PROGRAM
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Arya Porfolio</title>
    <style>
        /* Neubrutalism CSS Variables */
        :root {
            --bg: #f9f4e6;
            --primary: #1a1a1a;
            --secondary: #e83f3f;
            --accent: #3a86ff;
            --highlight: #f9cb40;
            --shadow: 8px 8px 0px var(--primary);
            --border-thick: 4px solid var(--primary);
            --border-thin: 2px solid var(--primary);
        }
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        body {
            font-family: 'Space Grotesk', sans-serif;
            background-color: var(--bg);
            color: var(--primary);
            line-height: 1.6;
            padding: 0;
            margin: 0;
            overflow-x: hidden;
        }
        
        @font-face {
            font-family: 'Space Grotesk';
            src: url('https://fonts.googleapis.com/css2?family=Space+Grotesk:wght@400;700&display=swap');
        }



        h1, h2, h3, h4 {
            font-weight: 800;
            letter-spacing: -0.05em;
            line-height: 1.1;
        }

        h1 {
            font-size: 4rem;
            margin-bottom: 1rem;
        }

        h2 {
            font-size: 2.5rem;
            margin-bottom: 2rem;
            position: relative;
            display: inline-block;
        }

        h2:after {
            content: '';
            position: absolute;
            bottom: -5px;
            left: 0;
            width: 100%;
            height: 8px;
            background-color: var(--highlight);
            z-index: -1;
        }

        h3 {
            font-size: 1.8rem;
            margin-bottom: 1rem;
        }

        p {
            font-size: 1.1rem;
            margin-bottom: 1.5rem;
            max-width: 65ch;
        }

        a {
            color: var(--primary);
            text-decoration: none;
            font-weight: bold;
            position: relative;
        }

        a:hover {
            color: var(--secondary);
        }

        .btn {
            display: inline-block;
            padding: 0.8rem 1.5rem;
            background-color: var(--primary);
            color: var(--bg);
            border: var(--border-thick);
            box-shadow: var(--shadow);
            font-weight: bold;
            text-transform: uppercase;
            letter-spacing: 0.1em;
            cursor: pointer;
            transition: all 0.2s ease;
            margin: 0.5rem 0;
        }

        .btn:hover {
            transform: translate(2px, 2px);
            box-shadow: 4px 4px 0px var(--primary);
            color: var(--bg);
            background-color: var(--secondary);
        }

        .btn-secondary {
            background-color: var(--bg);
            color: var(--primary);
        }

        .btn-secondary:hover {
            background-color: var(--highlight);
        }
        .container {
            width: 90%;
            max-width: 1200px;
            margin: 0 auto;
            padding: 2rem 0;
        }
        section {
            padding: 4rem 0;
            position: relative;
        }
        header {
            top: 0;
            background-color: var(--bg);
            z-index: 100;
            border-bottom: var(--border-thick);
        }
        nav {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .nav-links {
            display: flex;
            gap: 1.5rem;
        }

        .nav-links a {
            text-transform: uppercase;
            font-weight: 800;
            letter-spacing: 0.1em;
            font-size: 0.9rem;
            padding: 0.5rem 1rem;
            position: relative;
        }
        .nav-links a:before {
            content: '';
            position: absolute;
            bottom: 0;
            left: 0;
            width: 100%;
            height: 2px;
            background-color: var(--secondary);
            transform: scaleX(0);
            transform-origin: right;
            transition: transform 0.3s ease;
        }
        .nav-links a:hover:before {
            transform: scaleX(1);
            transform-origin: left;
        }

        .nav-links a.active {
            background-color: var(--highlight);
            border: var(--border-thin);
            box-shadow: 4px 4px 0px var(--primary);
        }
        #hero {
            min-height: 80vh;
            display: flex;
            align-items: center;
            border-bottom: var(--border-thick);
        }
        .hero-container {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 3rem;
            align-items: center;
        }
        .hero-content {
            display: flex;
            flex-direction: column;
            gap: 1rem;
        }

        .hero-highlight {
            display: inline-block;
            padding: 0.5rem 1rem;
            background-color: var(--highlight);
            border: var(--border-thick);
            box-shadow: var(--shadow);
            font-weight: bold;
            margin-bottom: 1rem;
            width: fit-content;
        }

        .hero-btns {
            display: flex;
            gap: 1rem;
            margin-top: 1rem;
        }

        .hero-image {
            width: 300px;
            height: 300px;
            border: var(--border-thick);
            box-shadow: var(--shadow);
            background-color: var(--highlight);
            border-radius: 50%;
            overflow: hidden;
            position: relative;
            display: flex;
            align-items: center;
            justify-content: center;
            margin: 0 auto; 
        }

        .hero-image img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            border-radius: 50%; 
        }
        #about {
            margin: 4rem 0;
        }

        .about-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
        }

        .about-card {
            background-color: white;
            border: var(--border-thick);
            box-shadow: var(--shadow);
            padding: 2rem;
            transition: all 0.3s ease;
        }

        .about-card:hover {
            transform: translate(5px, 5px);
            box-shadow: 3px 3px 0px var(--primary);
        }

        .about-card h3 {
            display: flex;
            align-items: center;
            gap: 0.5rem;
            margin-bottom: 1.5rem;
        }

        .about-card h3 span {
            font-size: 1.5rem;
        }

        .about-list {
            list-style: none;
        }

        .about-list li {
            padding: 0.8rem 0;
            border-bottom: var(--border-thin);
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .about-list li:last-child {
            border-bottom: none;
        }

        .skill-level {
            width: 100px;
            height: 10px;
            background-color: var(--bg);
            border: var(--border-thin);
            position: relative;
        }

        .skill-level-fill {
            position: absolute;
            top: 0;
            left: 0;
            height: 100%;
            background-color: var(--primary);
        }

        .education-item {
            margin-bottom: 1.5rem;
        }

        .education-item h4 {
            font-size: 1.2rem;
            margin-bottom: 0.3rem;
        }

        .education-item p {
            font-size: 0.9rem;
            color: var(--primary);
            opacity: 0.8;
            margin-bottom: 0.5rem;
        }

        .hobbies-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(120px, 1fr));
            gap: 1rem;
        }

        .hobby-item {
            padding: 1rem;
            background-color: var(--highlight);
            border: var(--border-thin);
            text-align: center;
            font-weight: bold;
            transition: all 0.2s ease;
        }

        .hobby-item:hover {
            transform: translateY(-5px);
            background-color: var(--secondary);
            color: white;
        }

        /* Projects Section */
        #projects {
            padding: 5rem 0;
            border-bottom: var(--border-thick);
        }

        #projects h2:after {
            background-color: var(--accent);
        }

        .projects-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
            gap: 2rem;
            margin-top: 3rem;
        }

        .project-card {
            background-color: white;
            border: var(--border-thick);
            box-shadow: var(--shadow);
            transition: all 0.3s ease;
            padding: 2rem;
            display: flex;
            flex-direction: column;
            min-height: 300px;
        }

        .project-card:hover {
            transform: translate(5px, 5px);
            box-shadow: 3px 3px 0px var(--primary);
        }

        .project-icon {
            font-size: 2.5rem;
            margin-bottom: 1.5rem;
            width: 60px;
            height: 60px;
            background-color: var(--highlight);
            display: flex;
            align-items: center;
            justify-content: center;
            border: var(--border-thin);
        }

        .project-content {
            flex-grow: 1;
        }

        .project-tags {
            display: flex;
            flex-wrap: wrap;
            gap: 0.5rem;
            margin: 1.5rem 0;
        }

        .tag {
            padding: 0.3rem 0.8rem;
            background-color: var(--primary);
            color: var(--bg);
            font-size: 0.8rem;
        }

        /* Contact Section */
        #contact {
            padding: 5rem 0;
        }

        .contact-container {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 3rem;
        }

        .contact-info {
            display: flex;
            flex-direction: column;
            gap: 1.5rem;
        }

        .contact-item {
            display: flex;
            align-items: center;
            gap: 1rem;
        }

        .contact-icon {
            width: 50px;
            height: 50px;
            background-color: var(--highlight);
            border: var(--border-thick);
            display: flex;
            align-items: center;
            justify-content: center;
            flex-shrink: 0;
        }

        .contact-form {
            background-color: white;
            border: var(--border-thick);
            box-shadow: var(--shadow);
            padding: 2rem;
        }

        .form-group {
            margin-bottom: 1.5rem;
        }

        label {
            display: block;
            margin-bottom: 0.5rem;
            font-weight: bold;
        }

        input, textarea {
            width: 100%;
            padding: 0.8rem;
            border: var(--border-thin);
            font-family: inherit;
            background-color: var(--bg);
        }

        textarea {
            min-height: 150px;
        }

        /* Footer */
        footer {
            background-color: var(--primary);
            color: var(--bg);
            padding: 1rem 0;
            border-top: var(--border-thick);
        }

        .footer-content {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .project-card h3 {
            position: relative;
            display: inline-block;
        }

        .project-card h3:after {
            content: '';
            position: absolute;
            bottom: -3px;
            left: 0;
            width: 0;
            height: 3px;
            background-color: var(--secondary);
            transition: width 0.3s ease;
        }

        .project-card:hover h3:after {
            width: 100%;
        }
    </style>
</head>
<body>
    <!-- Header -->
    <header>
        <div class="container">
            <nav>
                <div class="nav-links">
                    <a href="#about">About</a>
                    <a href="#projects">Projects</a>
                    <a href="#contact">Contact</a>
                </div>
            </nav>
        </div>
    </header>

    <!-- Hero Section with Image -->
    <section id="hero">
        <div class="container hero-container">
            <div class="hero-content">
                <span class="hero-highlight">AVAILABLE FOR WORK</span>
                <h1>Software & Frontend Developer</h1>
                <p>I am Arya Baisakhiya,i am driven by a passion
                    for learning, seeking new challenges and to expand my knowledge and
                    skills, with a strong willingness to learn, and collaborate effectively in a
                    team environment</p>
                <div class="hero-btns">
                    <a href="#projects" class="btn">View Work</a>
                    <a href="#contact" class="btn btn-secondary">Hire Me</a>
                </div>
            </div>
            <div class="hero-image floating">
                <!-- Replace with your actual image -->
                <img src="arya.jpg" alt="Arya - Designer & Developer">
            </div>
        </div>
    </section>

    <!-- About Section - Redesigned -->
    <section id="about">
        <div class="container">
            <h2>About Me</h2>
            <div class="about-grid">
                <!-- Skills Card -->
                <div class="about-card">
                    <h3><span>💻</span> Skills</h3>
                    <ul class="about-list">
                        <li>
                            <span>HTML/CSS</span>
                            <div class="skill-level">
                                <div class="skill-level-fill" style="width: 95%"></div>
                            </div>
                        </li>
                        <li>
                            <span>JavaScript</span>
                            <div class="skill-level">
                                <div class="skill-level-fill" style="width: 80%"></div>
                            </div>
                        </li>
                        <li>
                            <span>Figma</span>
                            <div class="skill-level">
                                <div class="skill-level-fill" style="width: 85%"></div>
                            </div>
                        </li>
                        <li>
                            <span>Java,C,python</span>
                            <div class="skill-level">
                                <div class="skill-level-fill" style="width: 80%"></div>
                            </div>
                        </li>
                        <li>
                            <span>ML Models</span>
                            <div class="skill-level">
                                <div class="skill-level-fill" style="width: 70%"></div>
                            </div>
                        </li>
                    </ul>
                </div>
                
                <!-- Education Card -->
                <div class="about-card">
                    <h3><span>🎓</span> Education</h3>
                    <div class="education-item">
                        <h4>B.E Computer Science Engineering</h4>
                        <p>Saveetha Engineering College| 2022-2026</p>
                    </div>
                    <div class="education-item">
                        <h4>Class XII</h4>
                        <p>Sri Sankara school | 2022</p>
                    </div>
                </div>
                
                <!-- Hobbies Card -->
                <div class="about-card">
                    <h3><span>⚡</span> Hobbies & Interests</h3>
                    <div class="hobbies-grid">
                        <div class="hobby-item">Sketching</div>
                        <div class="hobby-item">Traveling</div>
                        <div class="hobby-item">Painting</div>
                        <div class="hobby-item">Reading</div>
                        <div class="hobby-item">Photography</div>
                        <div class="hobby-item">Baking</div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Projects Section -->
    <section id="projects">
        <div class="container">
            <h2>Projects</h2>
            
            <div class="projects-grid">
                <!-- Project 1 -->
                <div class="project-card">
                    <div class="project-icon">🛒</div>
                    <div class="project-content">
                        <h3>eco-marketplace</h3>
                        <p>e-commerce platform designed to connect buyers and sellers in a way that promotes sustainability and waste reduction</p>
                        <div class="project-tags">
                            <span class="tag">React</span>
                            <span class="tag">CSS</span>
                            <span class="tag">Firebase</span>
                        </div>
                        <a href="#" class="btn">View →</a>
                    </div>
                </div>
                
                <!-- Project 2 -->
                <div class="project-card">
                    <div class="project-icon">🌈</div>
                    <div class="project-content">
                        <h3>Crowd Prediction Model</h3>
                        <p>ML model to predict crowd levels in public transport</p>
                        <div class="project-tags">
                            <span class="tag">Scikit-learn</span>
                            <span class="tag">Pandas</span>
                        </div>
                        <a href="#" class="btn">View Live →</a>
                    </div>
                </div>
                
                <!-- Project 3 -->
                <div class="project-card">
                    <div class="project-icon">🔤</div>
                    <div class="project-content">
                        <h3>Type Specimen</h3>
                        <p>An interactive showcase for a custom typeface, demonstrating its versatility through dynamic layout experiments.</p>
                        <div class="project-tags">
                            <span class="tag">Typography</span>
                            <span class="tag">CSS</span>
                            <span class="tag">JavaScript</span>
                        </div>
                        <a href="#" class="btn">Explore →</a>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Contact Section -->
    <section id="contact">
        <div class="container">
            <h2>Get In Touch</h2>
            
            <div class="contact-container">
                <div class="contact-info">
                    <div class="contact-item">
                        <div class="contact-icon">✉</div>
                        <div>
                            <h3>Email</h3>
                            <a href="mailto:aryabaisakhiya@gmail.com">aryabaisakhiya@gmail.com</a>
                        </div>
                    </div>
                    <div class="contact-item">
                        <div class="contact-icon">📱</div>
                        <div>
                            <h3>Phone</h3>
                            <a href="tel:+1234567890">+1 (234) 567-890</a>
                        </div>
                    </div>
                    <div class="contact-item">
                        <div class="contact-icon">📍</div>
                        <div>
                            <h3>Location</h3>
                            <p>Chennai,India</p>
                        </div>
                    </div>
                </div>
                
                <div class="contact-form">
                    <form>
                        <div class="form-group">
                            <label for="name">Name</label>
                            <input type="text" id="name" required>
                        </div>
                        <div class="form-group">
                            <label for="email">Email</label>
                            <input type="email" id="email" required>
                        </div>
                        <div class="form-group">
                            <label for="message">Message</label>
                            <textarea id="message" required></textarea>
                        </div>
                        <button type="submit" class="btn">Send Message</button>
                    </form>
                </div>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer>
        <div class="container">
            <div class="footer-content">
                <p>© 2025 Arya. All rights reserved.</p>
            </div>
        </div>
    </footer>
</body>
</html>
```

## OUTPUT
![image](https://github.com/user-attachments/assets/f7d0be6e-b7b7-45cc-ae8c-89fad83e82b1)

![image](https://github.com/user-attachments/assets/ac0c54e9-ad41-4a3d-91aa-3c5e62861d7b)

![image](https://github.com/user-attachments/assets/7804161a-6c73-49eb-9abf-40f1546d3d48)

![image](https://github.com/user-attachments/assets/9b66b6f7-8724-4c26-a41f-f715709d54d4)


## RESULT
The program for creating Portfolio using HTML and CSS is executed successfully.
