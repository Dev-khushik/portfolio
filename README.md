<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>My Portfolio</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        :root {
            --primary: #1ab5e4;
            --secondary: #1e40af;
            --dark: #1e293b;
            --light: #f6f6f7;
            --gray: #547199;
            --success: #10b981;
            --error: #ef4444;
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }

        body {
            background-color: var(--light);
            color: var(--dark);
            line-height: 1.6;
        }

        nav {
            position: fixed;
            top: 0;
            left: 0;
            right: 0;
            background-color: var(--light);
            box-shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.1);
            z-index: 1000;
            padding: 1rem 2rem;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 1rem;
        }

        .nav-container {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .logo {
            font-size: 1.5rem;
            font-weight: 700;
            color: var(--primary);
            text-decoration: none;
        }

        .nav-links {
            display: flex;
            gap: 2rem;
        }

        .nav-links a {
            color: var(--dark);
            text-decoration: none;
            font-weight: 500;
            transition: color 0.3s;
        }

        .nav-links a:hover {
            color: var(--primary);
        }

        .hamburger {
            display: none;
            cursor: pointer;
        }

        .hero {
            height: 100vh;
            display: flex;
            align-items: center;
            padding-top: 80px;
        }

        .hero-content {
            display: flex;
            align-items: center;
            gap: 3rem;
        }

        .hero-text {
            flex: 1;
        }

        .hero-image {
            flex: 1;
            border-radius: 20px;
            overflow: hidden;
            box-shadow: 0 10px 15px -3px rgba(0, 0, 0, 0.1);
        }

        .hero-image img {
            width: 100%;
            height: auto;
            display: block;
        }

        .hero-title {
            font-size: 3rem;
            margin-bottom: 1rem;
            line-height: 1.2;
        }

        .hero-subtitle {
            font-size: 1.5rem;
            color: var(--primary);
            margin-bottom: 1.5rem;
        }

        .hero-description {
            margin-bottom: 2rem;
            color: var(--gray);
            max-width: 600px;
        }

        .btn {
            display: inline-block;
            padding: 0.75rem 1.5rem;
            background-color: var(--primary);
            color: white;
            border: none;
            border-radius: 5px;
            text-decoration: none;
            font-weight: 600;
            transition: all 0.3s;
            cursor: pointer;
            margin-right: 1rem;
            margin-bottom: 1rem;
        }

        .btn:hover {
            background-color: var(--secondary);
            transform: translateY(-2px);
            box-shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.1);
        }

        .btn-outline {
            background-color: transparent;
            border: 2px solid var(--primary);
            color: var(--primary);
        }

        .btn-outline:hover {
            background-color: var(--primary);
            color: white;
        }

        section {
            padding: 6rem 0;
        }

        .section-title {
            text-align: center;
            font-size: 2.5rem;
            margin-bottom: 3rem;
            position: relative;
        }

        .section-title::after {
            content: '';
            position: absolute;
            bottom: -10px;
            left: 50%;
            transform: translateX(-50%);
            width: 80px;
            height: 4px;
            background-color: var(--primary);
        }

        .about-content {
            display: flex;
            align-items: center;
            gap: 3rem;
        }

        .about-image {
            flex: 1;
            border-radius: 20px;
            overflow: hidden;
            box-shadow: 0 10px 15px -3px rgba(0, 0, 0, 0.1);
        }

        .about-image img {
            width: 100%;
            height: auto;
            display: block;
        }

        .about-text {
            flex: 1;
        }

        .skills-container {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
            gap: 2rem;
            margin-top: 3rem;
        }

        .skill-card {
            background-color: white;
            padding: 2rem;
            border-radius: 10px;
            box-shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.1);
            text-align: center;
            transition: transform 0.3s;
        }

        .skill-card:hover {
            transform: translateY(-5px);
        }

        .skill-icon {
            font-size: 2rem;
            color: var(--primary);
            margin-bottom: 1rem;
        }

        .projects-container {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
            gap: 2rem;
            margin-top: 3rem;
        }

        .project-card {
            background-color: white;
            border-radius: 10px;
            overflow: hidden;
            box-shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.1);
            transition: transform 0.3s;
        }

        .project-card:hover {
            transform: translateY(-5px);
        }

        .project-image {
            height: 200px;
            overflow: hidden;
        }

        .project-image img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: transform 0.5s;
        }

        .project-card:hover .project-image img {
            transform: scale(1.05);
        }

        .project-content {
            padding: 1.5rem;
        }

        .project-title {
            font-size: 1.25rem;
            margin-bottom: 0.5rem;
        }

        .project-description {
            color: var(--gray);
            margin-bottom: 1rem;
        }

        .project-tags {
            display: flex;
            flex-wrap: wrap;
            gap: 0.5rem;
            margin-bottom: 1rem;
        }

        .tag {
            background-color: #e0e7ff;
            color: var(--primary);
            padding: 0.25rem 0.75rem;
            border-radius: 50px;
            font-size: 0.75rem;
            font-weight: 600;
        }

        .project-links {
            display: flex;
            gap: 1rem;
        }

        .contact-container {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 3rem;
            margin-top: 3rem;
        }

        .contact-info {
            background-color: white;
            padding: 2rem;
            border-radius: 10px;
            box-shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.1);
        }

        .contact-info h3 {
            margin-bottom: 1.5rem;
            color: var(--primary);
        }

        .contact-item {
            display: flex;
            align-items: center;
            gap: 1rem;
            margin-bottom: 1rem;
        }

        .contact-icon {
            width: 40px;
            height: 40px;
            background-color: #e0e7ff;
            color: var(--primary);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1rem;
        }

        .contact-form {
            background-color: white;
            padding: 2rem;
            border-radius: 10px;
            box-shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.1);
        }

        .form-group {
            margin-bottom: 1.5rem;
        }

        .form-group label {
            display: block;
            margin-bottom: 0.5rem;
            font-weight: 600;
        }

        .form-control {
            width: 100%;
            padding: 0.75rem;
            border: 1px solid #dddddd;
            border-radius: 5px;
            font-size: 1rem;
        }

        .form-control:focus {
            outline: none;
            border-color: var(--primary);
        }

        textarea.form-control {
            min-height: 150px;
            resize: vertical;
        }

        footer {
            background-color: var(--dark);
            color: white;
            padding: 2rem 0;
            text-align: center;
        }

        .social-links {
            display: flex;
            justify-content: center;
            gap: 1.5rem;
            margin-bottom: 1.5rem;
        }

        .social-link {
            width: 40px;
            height: 40px;
            background-color: #334155;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            text-decoration: none;
            transition: all 0.3s;
        }

        .social-link:hover {
            background-color: var(--primary);
            transform: translateY(-3px);
        }

        .back-to-top {
            position: fixed;
            bottom: 2rem;
            right: 2rem;
            width: 50px;
            height: 50px;
            background-color: var(--primary);
            color: white;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            opacity: 0;
            visibility: hidden;
            transition: all 0.3s;
            z-index: 99;
            cursor: pointer;
            text-decoration: none;
        }

        .back-to-top.active {
            opacity: 1;
            visibility: visible;
        }

        @media (max-width: 992px) {
            .hero-content {
                flex-direction: column;
            }

            .about-content {
                flex-direction: column;
            }
        }

        @media (max-width: 768px) {
            .hamburger {
                display: block;
            }

            .nav-links {
                position: fixed;
                top: 70px;
                left: -100%;
                width: 100%;
                height: calc(100vh - 70px);
                background-color: var(--light);
                flex-direction: column;
                align-items: center;
                justify-content: center;
                gap: 3rem;
                transition: all 0.5s;
            }

            .nav-links.active {
                left: 0;
            }

            .hero-title {
                font-size: 2.5rem;
            }

            .hero-subtitle {
                font-size: 1.25rem;
            }

            .section-title {
                font-size: 2rem;
            }
        }
    </style>
</head>
<body>
    <nav>
        <div class="container nav-container">
            <a href="#" class="logo"> Portfolio</a>
            <div class="hamburger">
                <i class="fas fa-bars"></i>
            </div>
            <ul class="nav-links">
                <li><a href="#home">Home</a></li>
                <li><a href="#about">About</a></li>
                <li><a href="#skills">Skills</a></li>
                <li><a href="#projects">Projects</a></li>
                <li><a href="#contact">Contact</a></li>
            </ul>
        </div>
    </nav>

    <section id="home" class="hero">
        <div class="container">
            <div class="hero-content">
                <div class="hero-text">
                    <h1 class="hero-title">Hi, I'm <span style="color: var(--primary);">khushi </span></h1>
                    <h2 class="hero-subtitle">Frontend Developer</h2>
                    <p class="hero-description">
                        I create beautiful, responsive websites and edit photos & videos using AI and modern technologies. I'm passionate about design and creativity.
                    </p>
                    <div class="hero-actions">
                        <a href="#contact" class="btn">Contact Me</a>
                        <a href="#projects" class="btn btn-outline">View My Work</a>
                    </div>
                </div>
               <div class="hero-image">
               <img src="c:\Users\DELL\Pictures\photo\khushisnap.jpg"alt class ="My Profile Photo" onerror="src='c:\Users\DELL\Pictures\photo\khushisnap.jpg'">
                </div>
            </div>
        </div>
    </section>

    <section id="about" class="about">
        <div class="container">
            <h2 class="section-title">About Me</h2>
            <div class="about-content">
                <div class="hero-image">
                    <img src="c:\Users\DELL\Pictures\photo\khushisnap.jpg" alt="my snap"/>
                </div>
                <br class="about-text">
                    <h3 style="margin-bottom: 1rem;">Who I Am</h3>
                    <p style="margin-bottom: 1.5rem;">
                        Hi, I’m Khushi. I’ve completed my graduation in Bachelor of Computer Applications from DAV College, Jalandhar.I started my first side hustle affiliate marketing  when I was in 11th class. Later, I also explored 
                        photo and video editing, creating social media content, and doing some basic data entry work. These experiences helped me learn new skills, be more creative, and gain confidence.
                    </p>
                    <h3 style="margin-bottom: 1rem;">Certification </h3>
                    <p style="margin-bottom: 1.5rem;">
                    Marketing with Canva & AI in the Classroom – from Canva School
                    Professional Edge Program – by NIIT Foundation & Infosys Foundation (Scored 95%)
                    Critical Innovation Thinking – from DAV College, Jalandhar
                    Personality Development – from Prerna Tech Institute, Chandigarh
                    Frontend Development – from Prerna Tech Institute, Chandigarh
                    </p>
                    <div style="display: flex; flex-wrap: wrap; gap: 1rem;">
                        <span class="tag">Web Development</span>
                        <span class="tag">Photo Editing </span>
                        <span class="tag">Video Editing</span>
                        <span class="tag">Data Analytics</span>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <section id="skills" class="skills">
        <div class="container">
            <h2 class="section-title">My Skills</h2>
            <div class="skills-container">
                <div class="skill-card">
                    <div class="skill-icon">
                        <i class="fab fa-html5"></i>
                    </div>
                    <h3>HTML5</h3>
                    <p>with help of create a structure of web </p>
                </div>
                <div class="skill-card">
                    <div class="skill-icon">
                        <i class="fab fa-css3-alt"></i>
                    </div>
                    <h3>CSS3</h3>
                    <p>Flexbox, Grid, animations, responsive design</p>
                </div>
                <div class="skill-card">
                    <div class="skill-icon">
                        <i class="fab fa-js"></i>
                    </div>
                    <h3>JavaScript</h3>
                    <p>ES6+, modern syntax, DOM manipulation</p>
                </div>
                <div class="skill-card">
                    <div class="skill-icon">
                        <i class="fab fa-react"></i>
                    </div>
                    <h3>React</h3>
                    <p>Hooks, context API, performance optimization</p>
                </div>
                <div class="skill-card">
                    <div class="skill-icon">
                        <i class="fab fa-node-js"></i>
                    </div>
                    <h3>Bootstrap</h3>
                    <p>help to create a responsive websites</p>
                </div>
                <div class="skill-card">
                    <div class="skill-icon">
                        <i class="fas fa-database"></i>
                    </div>
                    <h3>Canva</h3>
                    <p> Thumbanil logo and banner design video/ photo editing</p>
                </div>
                <div class="skill-card">
                    <div class="skill-icon">
                        <i class="fab fa-git-alt"></i>
                    </div>
                    <h3>Git</h3>
                    <p>Version control, GitHub, collaborative workflows</p>
                </div>
                <div class="skill-card">
                    <div class="skill-icon">
                        <i class="fas fa-mobile-alt"></i>
                    </div>
                    <h3>USing ai tools</h3>
                    <p>photo & video editing and problem solving</p>
                </div>
            </div>
        </div>
    </section>

    <section id="projects" class="projects">
        <div class="container">
            <h2 class="section-title">My College Projects</h2>
            <div class="projects-container">
                </div>
                </div>
                <div class="project-card">
                    <div class="project-content">
                        <h3 class="project-title">Social Media Platform</h3>
                        <p class="project-description">
                            FLINK (The Social Media Platform)
                            Allowed users to log in and connect by liking, 
                            commenting, and sharing. Made a basic and fun social
                            media experience. using react js,node js,mongoDB.
                        </p>
                        <div class="project-tags">
                            <span class="tag">Html</span>
                            <span class="tag">Css</span>
                            <span class="tag">Node.js</span>
                            <span class="tag">Mongo DB</span>
                        </div>
                        <div class="project-links">
                            <a href="https://dainty-klepon-9c5fcf.netlify.app/" class="btn btn-outline">Link</a>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <section id="contact" class="contact">
        <div class="container">
            <h2 class="section-title">Get In Touch</h2>
            <div class="contact-container">
                <div class="contact-info">
                    <h3>Contact Information</h3>
                    <div class="contact-item">
                        <div class="contact-icon">
                            <i class="fas fa-envelope"></i>
                        </div>
                        <div>
                            <h4>Email</h4>
                            <p>webdevexpkhuhi@gmail.com</p>
                        </div>
                    </div>
                    <div class="contact-item">
                        <div class="contact-icon">
                            <i class="fas fa-phone-alt"></i>
                        </div>
                        <div>
                            <h4>Phone</h4>
                            <p>+91-7508893533</p>
                        </div>
                    </div>
                    <div class="contact-item">
                        <div class="contact-icon">
                            <i class="fas fa-map-marker-alt"></i>
                        </div>
                        <div>
                            <h4>Location</h4>
                            <p>Saharanpur,up </p>
                        </div>
                    </div>
                </div>
                <div class="contact-form">
                    <h3>Send Me a Message</h3>
                    <form id="form">
                        <div class="form-group">
                            <label for="name">Name</label>
                            <input type="text" id="name" class="form-control" required>
                        </div>
                        <div class="form-group">
                            <label for="email">Email</label>
                            <input type="email" id="email" class="form-control" required>
                        </div>
                        <div class="form-group">
                            <label for="subject">Subject</label>
                            <input type="text" id="subject" class="form-control" required>
                        </div>
                        <div class="form-group">
                            <label for="message">Message</label>
                            <textarea id="message" class="form-control" required></textarea>
                        </div>
                        <button type="submit" class="btn">Send Message</button>
                    </form>
                </div>
            </div>
        </div>
    </section>

    <footer>
        <div class="container">
            <div class="social-links">
                <a href="https://github.com/Dev-khushik" class="social-link"><i class="fab fa-github"></i></a>
                <a href="http://linkedin.com/in/webdevexpkhushi" class="social-link"><i class="fab fa-linkedin-in"></i></a>
                <a href="https://x.com/webdevexpkhushi?t=BS_ae4kU06TokGQBj7sPVw&s=08" class="social-link"><i class="fab fa-twitter"></i></a>
                <a href="https://www.instagram.com/rasika.euphoria/" class="social-link"><i class="fab fa-instagram"></i></a>
            </div>
            <p>&copy; 2025 Khushi K. All rights reserved.</p>
            <p>Designed with ❤️ by Me</p>
        </div>
    </footer>

    <a href="#home" class="back-to-top">
        <i class="fas fa-arrow-up"></i>
    </a>

    <script>
        // Mobile menu toggle
        const hamburger = document.querySelector('.hamburger');
        const navLinks = document.querySelector('.nav-links');

        hamburger.addEventListener('click', () => {
            navLinks.classList.toggle('active');
            hamburger.querySelector('i').classList.toggle('fa-times');
        });

        // Close mobile menu when clicking on a link
        document.querySelectorAll('.nav-links a').forEach(link => {
            link.addEventListener('click', () => {
                navLinks.classList.remove('active');
                hamburger.querySelector('i').classList.remove('fa-times');
            });
        });

        // Smooth scrolling for anchor links
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function(e) {
                e.preventDefault();
                
                const targetId = this.getAttribute('href');
                const targetElement = document.querySelector(targetId);
                
                if (targetElement) {
                    window.scrollTo({
                        top: targetElement.offsetTop - 70,
                        behavior: 'smooth'
                    });
                }
            });
        });

        // Back to top button
        const backToTop = document.querySelector('.back-to-top');
        
        window.addEventListener('scroll', () => {
            if (window.scrollY > 300) {
                backToTop.classList.add('active');
            } else {
                backToTop.classList.remove('active');
            }
        });

        // Form submission
        const form = document.getElementById('form');
        
        form.addEventListener('submit', (e) => {
            e.preventDefault();
            
            // Get form values
            const name = document.getElementById('name').value;
            const email = document.getElementById('email').value;
            const subject = document.getElementById('subject').value;
            const message = document.getElementById('message').value;
            
            // In a real application, you would send this data to a server
            console.log({ name, email, subject, message });
            
            // Show alert
            alert('Message sent successfully! I will get back to you soon.');
            
            // Reset form
            form.reset();
        });

        // Animation on scroll
        const animateOnScroll = () => {
            const elements = document.querySelectorAll('.skill-card, .project-card');
            
            elements.forEach(element => {
                const elementPosition = element.getBoundingClientRect().top;
                const screenPosition = window.innerHeight / 1.3;
                
                if (elementPosition < screenPosition) {
                    element.style.opacity = '1';
                    element.style.transform = 'translateY(0)';
                }
            });
        };

        // Set initial styles for animation
        document.querySelectorAll('.skill-card, .project-card').forEach(element => {
            element.style.opacity = '0';
            element.style.transform = 'translateY(20px)';
            element.style.transition = 'all 0.5s ease';
        });

        // Run on load and scroll
        window.addEventListener('load', animateOnScroll);
        window.addEventListener('scroll', animateOnScroll);
    </script>
</body>
</html>


