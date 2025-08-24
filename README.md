<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Deepak Kumar - Full Stack Developer</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            line-height: 1.6;
            color: #333;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            min-height: 100vh;
            padding: 20px;
        }
        
        .resume-container {
            max-width: 900px;
            margin: 0 auto;
            background: white;
            border-radius: 15px;
            box-shadow: 0 20px 60px rgba(0,0,0,0.1);
            overflow: hidden;
            animation: slideUp 0.8s ease-out;
        }
        
        @keyframes slideUp {
            from {
                opacity: 0;
                transform: translateY(30px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }
        
        .header {
            background: linear-gradient(135deg, #2c3e50 0%, #3498db 100%);
            color: white;
            padding: 40px;
            text-align: center;
            position: relative;
            overflow: hidden;
        }
        
        .header::before {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: repeating-linear-gradient(
                45deg,
                transparent,
                transparent 10px,
                rgba(255,255,255,0.05) 10px,
                rgba(255,255,255,0.05) 20px
            );
            animation: slide 20s linear infinite;
        }
        
        @keyframes slide {
            0% { transform: translate(-50%, -50%) rotate(0deg); }
            100% { transform: translate(-50%, -50%) rotate(360deg); }
        }
        
        .header-content {
            position: relative;
            z-index: 2;
        }
        
        .name {
            font-size: 3rem;
            font-weight: 700;
            margin-bottom: 10px;
            text-shadow: 2px 2px 4px rgba(0,0,0,0.3);
        }
        
        .title {
            font-size: 1.3rem;
            font-weight: 300;
            margin-bottom: 20px;
            opacity: 0.9;
        }
        
        .contact-info {
            display: flex;
            justify-content: center;
            gap: 30px;
            flex-wrap: wrap;
            margin-top: 20px;
        }
        
        .contact-item {
            display: flex;
            align-items: center;
            gap: 8px;
            background: rgba(255,255,255,0.1);
            padding: 8px 16px;
            border-radius: 20px;
            backdrop-filter: blur(10px);
            transition: transform 0.3s ease;
        }
        
        .contact-item:hover {
            transform: translateY(-2px);
            background: rgba(255,255,255,0.2);
        }
        
        .content {
            padding: 40px;
        }
        
        .section {
            margin-bottom: 40px;
            animation: fadeIn 0.8s ease-out;
        }
        
        @keyframes fadeIn {
            from { opacity: 0; transform: translateX(-20px); }
            to { opacity: 1; transform: translateX(0); }
        }
        
        .section-title {
            font-size: 1.8rem;
            color: #2c3e50;
            border-bottom: 3px solid #3498db;
            padding-bottom: 10px;
            margin-bottom: 25px;
            position: relative;
        }
        
        .section-title::after {
            content: '';
            position: absolute;
            bottom: -3px;
            left: 0;
            width: 50px;
            height: 3px;
            background: #e74c3c;
            border-radius: 2px;
        }
        
        .summary {
            font-size: 1.1rem;
            line-height: 1.8;
            color: #555;
            background: linear-gradient(135deg, #f8f9fa 0%, #e9ecef 100%);
            padding: 25px;
            border-radius: 10px;
            border-left: 5px solid #3498db;
            position: relative;
        }
        
        .summary::before {
            content: '"';
            font-size: 4rem;
            color: #3498db;
            position: absolute;
            top: -10px;
            left: 15px;
            opacity: 0.3;
        }
        
        .skills-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 25px;
            margin-top: 20px;
        }
        
        .skill-category {
            background: linear-gradient(135deg, #f1f3f4 0%, #e8eaed 100%);
            padding: 20px;
            border-radius: 15px;
            border: 1px solid #e0e0e0;
            transition: all 0.3s ease;
        }
        
        .skill-category:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 30px rgba(0,0,0,0.1);
        }
        
        .skill-category h4 {
            color: #2c3e50;
            margin-bottom: 15px;
            font-size: 1.2rem;
            display: flex;
            align-items: center;
            gap: 10px;
        }
        
        .skill-tags {
            display: flex;
            flex-wrap: wrap;
            gap: 8px;
        }
        
        .skill-tag {
            background: linear-gradient(135deg, #3498db, #2980b9);
            color: white;
            padding: 6px 12px;
            border-radius: 20px;
            font-size: 0.9rem;
            font-weight: 500;
            transition: all 0.3s ease;
        }
        
        .skill-tag:hover {
            transform: scale(1.05);
            box-shadow: 0 5px 15px rgba(52, 152, 219, 0.4);
        }
        
        .experience-item, .project-item {
            background: white;
            border: 1px solid #e0e0e0;
            border-radius: 15px;
            padding: 25px;
            margin-bottom: 25px;
            transition: all 0.3s ease;
            position: relative;
            overflow: hidden;
        }
        
        .experience-item::before, .project-item::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 4px;
            height: 100%;
            background: linear-gradient(45deg, #3498db, #e74c3c);
        }
        
        .experience-item:hover, .project-item:hover {
            transform: translateX(5px);
            box-shadow: 0 15px 40px rgba(0,0,0,0.1);
        }
        
        .project-title, .experience-title {
            font-size: 1.4rem;
            color: #2c3e50;
            margin-bottom: 5px;
            display: flex;
            justify-content: space-between;
            align-items: center;
            flex-wrap: wrap;
        }
        
        .project-link {
            color: #3498db;
            text-decoration: none;
            font-weight: 600;
            transition: color 0.3s ease;
        }
        
        .project-link:hover {
            color: #e74c3c;
        }
        
        .project-tech, .date-range {
            color: #7f8c8d;
            font-size: 0.95rem;
            margin-bottom: 15px;
            font-weight: 500;
        }
        
        .date-range {
            background: linear-gradient(135deg, #ff6b6b, #feca57);
            color: white;
            padding: 4px 12px;
            border-radius: 15px;
            font-size: 0.85rem;
            font-weight: 600;
        }
        
        .achievement-list {
            list-style: none;
            margin-top: 15px;
        }
        
        .achievement-list li {
            padding: 8px 0;
            padding-left: 25px;
            position: relative;
            color: #555;
            line-height: 1.6;
        }
        
        .achievement-list li::before {
            content: '▶';
            position: absolute;
            left: 0;
            color: #3498db;
            font-size: 0.8rem;
        }
        
        .education-item {
            background: linear-gradient(135deg, #74b9ff 0%, #0984e3 100%);
            color: white;
            padding: 25px;
            border-radius: 15px;
            margin-bottom: 15px;
            position: relative;
            overflow: hidden;
        }
        
        .education-item::after {
            content: '';
            position: absolute;
            top: -50%;
            right: -50%;
            width: 100px;
            height: 100px;
            background: rgba(255,255,255,0.1);
            border-radius: 50%;
            transform: rotate(45deg);
        }
        
        .degree {
            font-size: 1.3rem;
            font-weight: 600;
            margin-bottom: 5px;
        }
        
        .institution {
            font-size: 1.1rem;
            opacity: 0.9;
            margin-bottom: 10px;
        }
        
        .education-details {
            display: flex;
            justify-content: space-between;
            align-items: center;
            flex-wrap: wrap;
            gap: 10px;
        }
        
        .gpa {
            background: rgba(255,255,255,0.2);
            padding: 5px 15px;
            border-radius: 20px;
            font-weight: 600;
        }
        
        .certifications {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 20px;
        }
        
        .cert-item {
            background: linear-gradient(135deg, #00b894, #00a085);
            color: white;
            padding: 20px;
            border-radius: 10px;
            text-align: center;
            transition: transform 0.3s ease;
        }
        
        .cert-item:hover {
            transform: scale(1.02);
        }
        
        .additional-info {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 25px;
        }
        
        .info-card {
            background: linear-gradient(135deg, #fd79a8, #fdcb6e);
            color: white;
            padding: 20px;
            border-radius: 15px;
            text-align: center;
        }
        
        .info-card h4 {
            margin-bottom: 15px;
            font-size: 1.2rem;
        }
        
        @media (max-width: 768px) {
            .resume-container {
                margin: 10px;
                border-radius: 10px;
            }
            
            .header {
                padding: 30px 20px;
            }
            
            .name {
                font-size: 2rem;
            }
            
            .content {
                padding: 30px 20px;
            }
            
            .contact-info {
                flex-direction: column;
                align-items: center;
                gap: 15px;
            }
            
            .project-title, .experience-title {
                flex-direction: column;
                align-items: flex-start;
                gap: 10px;
            }
        }
        
        .print-button {
            position: fixed;
            bottom: 30px;
            right: 30px;
            background: linear-gradient(135deg, #3498db, #2980b9);
            color: white;
            border: none;
            padding: 15px 20px;
            border-radius: 50px;
            cursor: pointer;
            font-size: 1rem;
            font-weight: 600;
            box-shadow: 0 10px 30px rgba(52, 152, 219, 0.3);
            transition: all 0.3s ease;
            z-index: 1000;
        }
        
        .print-button:hover {
            transform: translateY(-2px);
            box-shadow: 0 15px 40px rgba(52, 152, 219, 0.4);
        }
        
        @media print {
            body {
                background: white;
                padding: 0;
            }
            
            .resume-container {
                box-shadow: none;
                border-radius: 0;
            }
            
            .print-button {
                display: none;
            }
            
            .header::before {
                display: none;
            }
        }
    </style>
</head>
<body>
    <div class="resume-container">
        <header class="header">
            <div class="header-content">
                <h1 class="name">DEEPAK KUMAR</h1>
                <p class="title">Full Stack Developer | Problem Solver | Innovation Enthusiast</p>
                <div class="contact-info">
                    <div class="contact-item">
                        <span>📧</span>
                        <span>deepakkumar8400@gmail.com</span>
                    </div>
                    <div class="contact-item">
                        <span>🔗</span>
                        <span>linkedin.com/in/deepak-kumar213243270</span>
                    </div>
                    <div class="contact-item">
                        <span>🐙</span>
                        <span>github.com/deepakkumar8400</span>
                    </div>
                    <div class="contact-item">
                        <span>🌐</span>
                        <span>Portfolio: deepwebsite.onrender.com</span>
                    </div>
                </div>
            </div>
        </header>

        <div class="content">
            <section class="section">
                <h2 class="section-title">Professional Summary</h2>
                <div class="summary">
                    Passionate Computer Science graduate with hands-on experience in full-stack development and data structures. Proven track record of solving 600+ coding challenges on platforms like LeetCode and GeeksforGeeks. Built scalable web applications with modern technologies including React, Node.js, and cloud platforms. Demonstrated expertise in developing secure, user-friendly solutions with strong problem-solving abilities and a commitment to continuous learning and innovation.
                </div>
            </section>

            <section class="section">
                <h2 class="section-title">Technical Skills</h2>
                <div class="skills-grid">
                    <div class="skill-category">
                        <h4>💻 Programming Languages</h4>
                        <div class="skill-tags">
                            <span class="skill-tag">Java</span>
                            <span class="skill-tag">JavaScript</span>
                            <span class="skill-tag">Python</span>
                            <span class="skill-tag">HTML5</span>
                            <span class="skill-tag">CSS3</span>
                        </div>
                    </div>
                    <div class="skill-category">
                        <h4>🚀 Frontend Technologies</h4>
                        <div class="skill-tags">
                            <span class="skill-tag">React.js</span>
                            <span class="skill-tag">Vue.js</span>
                            <span class="skill-tag">Bootstrap</span>
                            <span class="skill-tag">Responsive Design</span>
                        </div>
                    </div>
                    <div class="skill-category">
                        <h4>⚡ Backend & APIs</h4>
                        <div class="skill-tags">
                            <span class="skill-tag">Node.js</span>
                            <span class="skill-tag">Express.js</span>
                            <span class="skill-tag">RESTful APIs</span>
                            <span class="skill-tag">JWT Authentication</span>
                        </div>
                    </div>
                    <div class="skill-category">
                        <h4>🗄️ Databases</h4>
                        <div class="skill-tags">
                            <span class="skill-tag">MongoDB</span>
                            <span class="skill-tag">MySQL</span>
                            <span class="skill-tag">PostgreSQL</span>
                        </div>
                    </div>
                    <div class="skill-category">
                        <h4>🛠️ Tools & Technologies</h4>
                        <div class="skill-tags">
                            <span class="skill-tag">Git/GitHub</span>
                            <span class="skill-tag">VS Code</span>
                            <span class="skill-tag">Postman</span>
                            <span class="skill-tag">Docker</span>
                        </div>
                    </div>
                    <div class="skill-category">
                        <h4>📊 Core Computer Science</h4>
                        <div class="skill-tags">
                            <span class="skill-tag">Data Structures</span>
                            <span class="skill-tag">Algorithms</span>
                            <span class="skill-tag">OOP</span>
                            <span class="skill-tag">System Design</span>
                        </div>
                    </div>
                </div>
            </section>

            <section class="section">
                <h2 class="section-title">Key Projects</h2>
                
                <div class="project-item">
                    <div class="project-title">
                        <a href="https://github.com/deepakkumar8400" class="project-link">Online Banking System</a>
                        <span class="date-range">June 2025 – Present</span>
                    </div>
                    <div class="project-tech">Tech Stack: Node.js, Express.js, React.js, MongoDB, JWT Authentication</div>
                    <ul class="achievement-list">
                        <li>Developed a comprehensive banking platform with secure user authentication and JWT-based session management</li>
                        <li>Built RESTful APIs for fund transfers, balance inquiries, transaction processing, and account management</li>
                        <li>Designed responsive React frontend with real-time balance updates and transaction history</li>
                        <li>Implemented MongoDB database with optimized schemas ensuring ACID compliance for financial operations</li>
                        <li>Integrated security features including role-based access control and transaction audit trails</li>
                    </ul>
                </div>

                <div class="project-item">
                    <div class="project-title">
                        <a href="#" class="project-link">Healthcare Payment System</a>
                        <span class="date-range">Mar 2025 – May 2025</span>
                    </div>
                    <div class="project-tech">Tech Stack: MERN Stack, Stripe API, Socket.io</div>
                    <ul class="achievement-list">
                        <li>Developed full-stack healthcare management platform enabling patients to book appointments and manage medical records</li>
                        <li>Implemented secure payment gateway integration with Stripe for seamless financial transactions</li>
                        <li>Built doctor portal for appointment tracking, patient overview, and profile management</li>
                        <li>Created admin dashboard to manage appointments, doctor profiles, and system analytics with role-based operations</li>
                        <li>Designed responsive UI with real-time notifications and appointment scheduling system</li>
                    </ul>
                </div>

                <div class="project-item">
                    <div class="project-title">
                        <a href="#" class="project-link">Job Portal Platform</a>
                        <span class="date-range">Dec 2024 – Feb 2025</span>
                    </div>
                    <div class="project-tech">Tech Stack: MERN Stack, Cloudinary, JWT</div>
                    <ul class="achievement-list">
                        <li>Built comprehensive job portal with role-based dashboards for job seekers, employers, and administrators</li>
                        <li>Developed advanced job search and filtering system with location-based results and category sorting</li>
                        <li>Implemented resume upload system with Cloudinary integration and candidate profile management</li>
                        <li>Created intelligent job matching algorithm and application tracking system</li>
                        <li>Integrated real-time notifications for application status updates and new job postings</li>
                    </ul>
                </div>
            </section>

            <section class="section">
                <h2 class="section-title">Programming Excellence</h2>
                <div class="experience-item">
                    <div class="experience-title">
                        <span>Competitive Programming & Problem Solving</span>
                        <span class="date-range">2023 – Present</span>
                    </div>
                    <ul class="achievement-list">
                        <li><strong>600+ Problems Solved:</strong> Achieved exceptional performance on LeetCode and GeeksforGeeks platforms</li>
                        <li><strong>Advanced Algorithms:</strong> Mastered dynamic programming, graph algorithms, tree traversals, and optimization techniques</li>
                        <li><strong>Data Structure Expertise:</strong> Comprehensive knowledge of arrays, linked lists, stacks, queues, heaps, and hash tables</li>
                        <li><strong>Problem-Solving Speed:</strong> Developed efficient debugging skills and optimized solution approaches</li>
                        <li><strong>Code Quality:</strong> Focus on writing clean, scalable, and maintainable code following industry best practices</li>
                    </ul>
                </div>
            </section>

            <section class="section">
                <h2 class="section-title">Education</h2>
                <div class="education-item">
                    <div class="degree">B.Tech in Computer Science Engineering</div>
                    <div class="institution">Noida Institute of Engineering and Technology (NIET)</div>
                    <div class="education-details">
                        <span>Aug 2022 – May 2026</span>
                        <span class="gpa">CGPA: 7.5/10.0</span>
                    </div>
                </div>
                <div class="education-item">
                    <div class="degree">Intermediate (Class XII)</div>
                    <div class="institution">Jagdishwar Public School</div>
                    <div class="education-details">
                        <span>Jul 2020 – May 2022</span>
                        <span class="gpa">81%</span>
                    </div>
                </div>
                <div class="education-item">
                    <div class="degree">High School (Class X)</div>
                    <div class="institution">Jagdishwar Public School</div>
                    <div class="education-details">
                        <span>Jul 2018 – May 2019</span>
                        <span class="gpa">86%</span>
                    </div>
                </div>
            </section>

            <section class="section">
                <h2 class="section-title">Certifications & Professional Development</h2>
                <div class="certifications">
                    <div class="cert-item">
                        <strong>ReactJS Professional Certification</strong><br>
                        <small>Infosys Springboard | November 2024</small>
                    </div>
                    <div class="cert-item">
                        <strong>Professional Communication Skills</strong><br>
                        <small>Coursera | November 2023</small>
                    </div>
                    <div class="cert-item">
                        <strong>HTML, CSS, and JavaScript for Web Developers</strong><br>
                        <small>Coursera | August 2023</small>
                    </div>
                </div>
            </section>

            <section class="section">
                <h2 class="section-title">Additional Qualifications</h2>
                <div class="additional-info">
                    <div class="info-card">
                        <h4>🗣️ Languages</h4>
                        <p><strong>English:</strong> Professional Proficiency<br>
                        <strong>Hindi:</strong> Native Speaker</p>
                    </div>
                    <div class="info-card">
                        <h4>🎯 Soft Skills</h4>
                        <p>Analytical Thinking • Team Collaboration • Adaptability • Continuous Learning • Quick Problem Solving</p>
                    </div>
                    <div class="info-card">
                        <h4>🎨 Interests</h4>
                        <p>Reading Technical Books • Playing Cricket • Traveling • Social Interaction • Open Source Contribution</p>
                    </div>
                </div>
            </section>
        </div>
    </div>

    <button class="print-button" onclick="window.print()">📄 Print Resume</button>

    <script>
        // Add smooth scrolling and animations
        document.addEventListener('DOMContentLoaded', function() {
            // Animate skill tags on hover
            const skillTags = document.querySelectorAll('.skill-tag');
            skillTags.forEach(tag => {
                tag.addEventListener('mouseenter', function() {
                    this.style.transform = 'scale(1.1) rotate(2deg)';
                });
                tag.addEventListener('mouseleave', function() {
                    this.style.transform = 'scale(1) rotate(0deg)';
                });
            });

            // Add typing effect to name
            const nameElement = document.querySelector('.name');
            const originalText = nameElement.textContent;
            nameElement.textContent = '';
            
            let i = 0;
            function typeWriter() {
                if (i < originalText.length) {
                    nameElement.textContent += originalText.charAt(i);
                    i++;
                    setTimeout(typeWriter, 100);
                }
            }
            
            setTimeout(typeWriter, 500);

            // Add intersection observer for animations
            const observerOptions = {
                threshold: 0.1,
                rootMargin: '0px 0px -50px 0px'
            };

            const observer = new IntersectionObserver((entries) => {
                entries.forEach(entry => {
                    if (entry.isIntersecting) {
                        entry.target.style.opacity = '1';
                        entry.target.style.transform = 'translateY(0)';
                    }
                });
            }, observerOptions);

            // Observe all sections
            document.querySelectorAll('.section').forEach(section => {
                section.style.opacity = '0';
                section.style.transform = 'translateY(30px)';
                section.style.transition = 'opacity 0.6s ease, transform 0.6s ease';
                observer.observe(section);
            });
        });
    </script>
</body>
</html>
