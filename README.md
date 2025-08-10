<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Abhishek Rohatagi - Data Analytics Portfolio</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            line-height: 1.6;
            transition: all 0.8s ease;
            min-height: 100vh;
            overflow-x: hidden;
        }
        
        /* Background Themes */
        .theme-gradient {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
        }
        
        .theme-ocean {
            background: linear-gradient(135deg, #667db6 0%, #0082c8 35%, #0082c8 100%);
        }
        
        .theme-sunset {
            background: linear-gradient(135deg, #ff9a9e 0%, #fecfef 50%, #fecfef 100%);
        }
        
        .theme-forest {
            background: linear-gradient(135deg, #2c5530 0%, #38a3a5 100%);
        }
        
        .theme-dark {
            background: linear-gradient(135deg, #232526 0%, #414345 100%);
        }
        
        .theme-matrix {
            background: linear-gradient(135deg, #0f3460 0%, #0e4b99 100%);
        }
        
        .theme-neon {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            position: relative;
        }
        
        .theme-neon::before {
            content: '';
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: url('data:image/svg+xml,<svg width="60" height="60" viewBox="0 0 60 60" xmlns="http://www.w3.org/2000/svg"><g fill="none" fill-rule="evenodd"><g fill="%2300ffff" fill-opacity="0.1"><circle cx="30" cy="30" r="2"/></g></svg>') repeat;
            animation: matrix 20s linear infinite;
            pointer-events: none;
        }
        
        @keyframes matrix {
            0% { transform: translateY(-100%); }
            100% { transform: translateY(100vh); }
        }
        
        /* Theme Button */
        .theme-selector {
            position: fixed;
            top: 20px;
            right: 20px;
            z-index: 1000;
        }
        
        .theme-btn {
            background: rgba(255, 255, 255, 0.1);
            backdrop-filter: blur(10px);
            border: 1px solid rgba(255, 255, 255, 0.2);
            color: white;
            padding: 12px 20px;
            border-radius: 50px;
            cursor: pointer;
            font-size: 14px;
            font-weight: 600;
            transition: all 0.3s ease;
            box-shadow: 0 8px 32px rgba(0, 0, 0, 0.1);
        }
        
        .theme-btn:hover {
            background: rgba(255, 255, 255, 0.2);
            transform: translateY(-2px);
            box-shadow: 0 12px 40px rgba(0, 0, 0, 0.2);
        }
        
        /* Container */
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 20px;
            position: relative;
            z-index: 1;
        }
        
        /* Header Section */
        .header {
            text-align: center;
            color: white;
            margin-bottom: 50px;
            padding: 60px 0;
        }
        
        .header h1 {
            font-size: 3.5rem;
            font-weight: 700;
            margin-bottom: 20px;
            text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.3);
            animation: fadeInUp 1s ease;
        }
        
        .header .subtitle {
            font-size: 1.4rem;
            margin-bottom: 30px;
            opacity: 0.9;
            animation: fadeInUp 1s ease 0.3s both;
        }
        
        .social-links {
            display: flex;
            justify-content: center;
            gap: 20px;
            animation: fadeInUp 1s ease 0.6s both;
        }
        
        .social-btn {
            background: rgba(255, 255, 255, 0.1);
            backdrop-filter: blur(10px);
            color: white;
            padding: 12px 24px;
            text-decoration: none;
            border-radius: 30px;
            border: 1px solid rgba(255, 255, 255, 0.2);
            transition: all 0.3s ease;
            font-weight: 600;
        }
        
        .social-btn:hover {
            background: rgba(255, 255, 255, 0.2);
            transform: translateY(-3px);
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.2);
        }
        
        /* Cards */
        .card {
            background: rgba(255, 255, 255, 0.1);
            backdrop-filter: blur(15px);
            border-radius: 20px;
            padding: 30px;
            margin-bottom: 30px;
            border: 1px solid rgba(255, 255, 255, 0.2);
            box-shadow: 0 8px 32px rgba(0, 0, 0, 0.1);
            transition: all 0.3s ease;
            color: white;
        }
        
        .card:hover {
            transform: translateY(-10px);
            box-shadow: 0 20px 60px rgba(0, 0, 0, 0.2);
        }
        
        .card h2 {
            font-size: 2rem;
            margin-bottom: 20px;
            display: flex;
            align-items: center;
            gap: 10px;
        }
        
        /* About Section */
        .about-content {
            display: grid;
            grid-template-columns: 1fr 300px;
            gap: 30px;
            align-items: center;
        }
        
        .about-text p {
            margin-bottom: 15px;
            font-size: 1.1rem;
            opacity: 0.9;
        }
        
        .profile-img {
            width: 250px;
            height: 250px;
            border-radius: 50%;
            background: linear-gradient(45deg, #00d4ff, #ff0080);
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 4rem;
            margin: 0 auto;
            animation: pulse 2s infinite;
        }
        
        /* Skills Grid */
        .skills-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 20px;
            margin-top: 20px;
        }
        
        .skill-category {
            background: rgba(255, 255, 255, 0.05);
            padding: 20px;
            border-radius: 15px;
            border: 1px solid rgba(255, 255, 255, 0.1);
        }
        
        .skill-category h3 {
            margin-bottom: 15px;
            color: #00d4ff;
            font-size: 1.2rem;
        }
        
        .skill-item {
            background: rgba(255, 255, 255, 0.1);
            padding: 8px 16px;
            margin: 8px;
            border-radius: 25px;
            display: inline-block;
            font-size: 0.9rem;
            border: 1px solid rgba(255, 255, 255, 0.2);
            transition: all 0.3s ease;
        }
        
        .skill-item:hover {
            background: rgba(0, 212, 255, 0.3);
            transform: scale(1.05);
        }
        
        /* Projects Grid */
        .projects-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
            gap: 25px;
            margin-top: 20px;
        }
        
        .project-card {
            background: rgba(255, 255, 255, 0.05);
            padding: 25px;
            border-radius: 15px;
            border: 1px solid rgba(255, 255, 255, 0.1);
            transition: all 0.3s ease;
            position: relative;
            overflow: hidden;
        }
        
        .project-card:hover {
            background: rgba(255, 255, 255, 0.1);
            transform: translateY(-5px);
        }
        
        .project-card h3 {
            color: #00d4ff;
            margin-bottom: 10px;
            font-size: 1.3rem;
        }
        
        .project-tech {
            color: #ff6b6b;
            font-weight: 600;
            margin-bottom: 10px;
            font-size: 0.9rem;
        }
        
        .project-desc {
            opacity: 0.9;
            line-height: 1.6;
        }
        
        /* Stats */
        .stats-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 20px;
            margin-top: 20px;
        }
        
        .stat-item {
            text-align: center;
            background: rgba(255, 255, 255, 0.05);
            padding: 20px;
            border-radius: 15px;
            border: 1px solid rgba(255, 255, 255, 0.1);
        }
        
        .stat-number {
            font-size: 2.5rem;
            font-weight: 700;
            color: #00d4ff;
            display: block;
        }
        
        .stat-label {
            opacity: 0.8;
            font-size: 0.9rem;
            margin-top: 5px;
        }
        
        /* Education */
        .education-item {
            background: rgba(255, 255, 255, 0.05);
            padding: 20px;
            border-radius: 15px;
            border: 1px solid rgba(255, 255, 255, 0.1);
            margin-bottom: 15px;
        }
        
        .education-item h3 {
            color: #00d4ff;
            margin-bottom: 5px;
        }
        
        .education-details {
            opacity: 0.9;
            font-size: 0.95rem;
        }
        
        /* Animations */
        @keyframes fadeInUp {
            from {
                opacity: 0;
                transform: translateY(30px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }
        
        @keyframes pulse {
            0%, 100% { transform: scale(1); }
            50% { transform: scale(1.05); }
        }
        
        /* Responsive */
        @media (max-width: 768px) {
            .header h1 {
                font-size: 2.5rem;
            }
            
            .about-content {
                grid-template-columns: 1fr;
                text-align: center;
            }
            
            .projects-grid {
                grid-template-columns: 1fr;
            }
            
            .social-links {
                flex-wrap: wrap;
            }
            
            .theme-selector {
                top: 10px;
                right: 10px;
            }
        }
    </style>
</head>
<body class="theme-gradient">
    <div class="theme-selector">
        <button class="theme-btn" onclick="changeTheme()">🎨 Change Theme</button>
    </div>
    
    <div class="container">
        <!-- Header -->
        <div class="header">
            <h1>Hi, I'm Abhishek Rohatagi 👋</h1>
            <p class="subtitle">Data Analytics Enthusiast | Turning Data into Insights 💡</p>
            <div class="social-links">
                <a href="https://www.linkedin.com/in/abhishek-rohatagi-bb17801ab/" class="social-btn">LinkedIn</a>
                <a href="mailto:abhishek251314@gmail.com" class="social-btn">Email</a>
                <a href="https://abhishek-rohtagi.my.canva.site/abhishek-rohatagi-portfolio-website" class="social-btn">Portfolio</a>
                <a href="tel:+919027213870" class="social-btn">Phone</a>
            </div>
        </div>
        
        <!-- About Me -->
        <div class="card">
            <h2>🎯 About Me</h2>
            <div class="about-content">
                <div class="about-text">
                    <p><strong>Engineering graduate</strong> with a strong analytical foundation</p>
                    <p><strong>Data Analytics enthusiast</strong> passionate about extracting insights</p>
                    <p>🚀 Proficient in <strong>Python, SQL, Power BI</strong> and visualization tools</p>
                    <p>💡 Love turning complex data into <strong>actionable business solutions</strong></p>
                    <p>📍 Based in <strong>Muzaffarnagar, Uttar Pradesh</strong></p>
                    <p>🎯 Currently seeking opportunities in <strong>Data Analytics & BI</strong></p>
                </div>
                <div class="profile-img">
                    👨‍💻
                </div>
            </div>
        </div>
        
        <!-- Tech Stack -->
        <div class="card">
            <h2>🔧 Tech Stack & Tools</h2>
            <div class="skills-grid">
                <div class="skill-category">
                    <h3>Data Analysis & BI</h3>
                    <span class="skill-item">Power BI</span>
                    <span class="skill-item">Tableau</span>
                    <span class="skill-item">Excel</span>
                    <span class="skill-item">Google Sheets</span>
                </div>
                <div class="skill-category">
                    <h3>Programming</h3>
                    <span class="skill-item">Python</span>
                    <span class="skill-item">SQL</span>
                    <span class="skill-item">R</span>
                </div>
                <div class="skill-category">
                    <h3>Data Science & ML</h3>
                    <span class="skill-item">Pandas</span>
                    <span class="skill-item">NumPy</span>
                    <span class="skill-item">Scikit-Learn</span>
                    <span class="skill-item">Matplotlib</span>
                </div>
                <div class="skill-category">
                    <h3>Databases & Tools</h3>
                    <span class="skill-item">MySQL</span>
                    <span class="skill-item">PostgreSQL</span>
                    <span class="skill-item">Git</span>
                    <span class="skill-item">Jupyter</span>
                </div>
            </div>
        </div>
        
        <!-- Featured Projects -->
        <div class="card">
            <h2>🚀 Featured Projects</h2>
            <div class="projects-grid">
                <div class="project-card">
                    <h3>📊 HR Analytics Dashboard</h3>
                    <p class="project-tech">Power BI • Interactive Dashboard • Data Visualization</p>
                    <p class="project-desc">3-page interactive HR dashboard with employee demographics, retirement analytics, and satisfaction metrics featuring drill-through capabilities.</p>
                </div>
                <div class="project-card">
                    <h3>🗄️ SQL Infrastructure Analysis</h3>
                    <p class="project-tech">SQL • Data Analysis • Executive Dashboard</p>
                    <p class="project-desc">Complex SQL analytics project analyzing infrastructure data, uncovering delays and vendor insights using advanced SQL techniques.</p>
                </div>
                <div class="project-card">
                    <h3>🧠 Customer Segmentation ML</h3>
                    <p class="project-tech">Python • Machine Learning • Clustering</p>
                    <p class="project-desc">Unsupervised learning project using K-Means, Hierarchical Clustering, and DBSCAN for customer behavior segmentation.</p>
                </div>
            </div>
        </div>
        
        <!-- GitHub Stats -->
        <div class="card">
            <h2>📊 GitHub Analytics</h2>
            <div class="stats-grid">
                <div class="stat-item">
                    <span class="stat-number">50+</span>
                    <span class="stat-label">Repositories</span>
                </div>
                <div class="stat-item">
                    <span class="stat-number">500+</span>
                    <span class="stat-label">Commits</span>
                </div>
                <div class="stat-item">
                    <span class="stat-number">15+</span>
                    <span class="stat-label">Projects</span>
                </div>
                <div class="stat-item">
                    <span class="stat-number">8.59</span>
                    <span class="stat-label">CGPA</span>
                </div>
            </div>
        </div>
        
        <!-- Education -->
        <div class="card">
            <h2>🎓 Education & Certifications</h2>
            <div class="education-item">
                <h3>B.Tech Mechanical Engineering</h3>
                <p class="education-details"><strong>Graphic Era Deemed to be University</strong> | Jul 2018 – Jun 2022 | <strong>CGPA: 8.59</strong></p>
            </div>
            <div class="education-item">
                <h3>Intermediate (Science)</h3>
                <p class="education-details"><strong>D.A.V. Inter College, Jansath</strong> | Jul 2016 – Jun 2017 | <strong>84.2%</strong></p>
            </div>
            <div class="skills-grid" style="margin-top: 20px;">
                <div class="skill-category">
                    <h3>📜 Certifications</h3>
                    <span class="skill-item">Python for ML & Data Science</span>
                    <span class="skill-item">Business Strategy Specialization</span>
                    <span class="skill-item">Data Analysis with Python</span>
                    <span class="skill-item">SQL for Data Science</span>
                </div>
                <div class="skill-category">
                    <h3>🌐 Languages</h3>
                    <span class="skill-item">English - Professional</span>
                    <span class="skill-item">Hindi - Native</span>
                </div>
            </div>
        </div>
        
        <!-- Call to Action -->
        <div class="card" style="text-align: center;">
            <h2>💡 Let's Connect!</h2>
            <p style="font-size: 1.2rem; margin-bottom: 20px; opacity: 0.9;">
                "Currently seeking opportunities in Data Analytics, Business Intelligence, and Data Science"
            </p>
            <div class="social-links">
                <a href="https://www.linkedin.com/in/abhishek-rohatagi-bb17801ab/" class="social-btn">🔗 Connect on LinkedIn</a>
                <a href="mailto:abhishek251314@gmail.com" class="social-btn">📧 Send Email</a>
                <a href="https://abhishek-rohtagi.my.canva.site/abhishek-rohatagi-portfolio-website" class="social-btn">🌐 View Portfolio</a>
            </div>
        </div>
    </div>
    
    <script>
        const themes = [
            'theme-gradient',
            'theme-ocean', 
            'theme-sunset',
            'theme-forest',
            'theme-dark',
            'theme-matrix',
            'theme-neon'
        ];
        
        let currentTheme = 0;
        
        function changeTheme() {
            // Remove current theme
            document.body.classList.remove(themes[currentTheme]);
            
            // Move to next theme
            currentTheme = (currentTheme + 1) % themes.length;
            
            // Add new theme
            document.body.classList.add(themes[currentTheme]);
            
            // Add a nice transition effect
            document.body.style.transform = 'scale(0.98)';
            setTimeout(() => {
                document.body.style.transform = 'scale(1)';
            }, 200);
        }
        
        // Add scroll animations
        const observer = new IntersectionObserver((entries) => {
            entries.forEach((entry) => {
                if (entry.isIntersecting) {
                    entry.target.style.animation = 'fadeInUp 0.6s ease forwards';
                }
            });
        }, { threshold: 0.1 });
        
        document.querySelectorAll('.card').forEach((card) => {
            observer.observe(card);
        });
        
        // Add some interactive particles (optional)
        function createParticle() {
            const particle = document.createElement('div');
            particle.style.position = 'fixed';
            particle.style.width = '4px';
            particle.style.height = '4px';
            particle.style.background = 'rgba(255, 255, 255, 0.5)';
            particle.style.borderRadius = '50%';
            particle.style.pointerEvents = 'none';
            particle.style.zIndex = '999';
            particle.style.left = Math.random() * window.innerWidth + 'px';
            particle.style.top = '100vh';
            particle.style.animation = 'float 8s linear infinite';
            
            document.body.appendChild(particle);
            
            setTimeout(() => {
                particle.remove();
            }, 8000);
        }
        
        // Add floating animation
        const style = document.createElement('style');
        style.textContent = `
            @keyframes float {
                to {
                    transform: translateY(-100vh);
                    opacity: 0;
                }
            }
        `;
        document.head.appendChild(style);
        
        // Create particles periodically
        setInterval(createParticle, 300);
        
        // Add hover effects to skill items
        document.querySelectorAll('.skill-item').forEach(item => {
            item.addEventListener('mouseenter', function() {
                this.style.boxShadow = '0 5px 15px rgba(0, 212, 255, 0.3)';
            });
            
            item.addEventListener('mouseleave', function() {
                this.style.boxShadow = 'none';
            });
        });
    </script>
</body>
</html>
