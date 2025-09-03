---
layout: page
title: Curriculum Vitae
description: Detailed overview of my professional experience, skills, and achievements.
---

<div class="cv-header">
    <div class="cv-contact">
        <h1>[Your Full Name]</h1>
        <div class="contact-info">
            <p><i class="fas fa-envelope"></i> your.email@example.com</p>
            <p><i class="fas fa-phone"></i> +1 (555) 123-4567</p>
            <p><i class="fas fa-map-marker-alt"></i> Your City, Country</p>
            <p><i class="fab fa-linkedin"></i> linkedin.com/in/yourusername</p>
            <p><i class="fab fa-github"></i> github.com/yourusername</p>
        </div>
    </div>
    <div class="cv-download">
        <a href="/assets/files/cv.pdf" class="btn btn-primary" download>
            <i class="fas fa-download"></i> Download PDF
        </a>
    </div>
</div>

<section class="cv-section">
    <h2>Professional Summary</h2>
    <p>
        Experienced software developer with {{ 'now' | date: "%Y" | minus: 2020 }}+ years of expertise in full-stack 
        web development, specializing in modern JavaScript frameworks, cloud technologies, and agile methodologies. 
        Proven track record of delivering scalable applications and leading technical initiatives. 
        Passionate about clean code, user experience, and continuous learning.
    </p>
</section>

<section class="cv-section">
    <h2>Technical Skills</h2>
    <div class="skills-grid">
        <div class="skill-category">
            <h3>Programming Languages</h3>
            <ul>
                <li>JavaScript (ES6+)</li>
                <li>TypeScript</li>
                <li>Python</li>
                <li>Java</li>
                <li>HTML5/CSS3</li>
            </ul>
        </div>
        
        <div class="skill-category">
            <h3>Frontend Technologies</h3>
            <ul>
                <li>React.js / Next.js</li>
                <li>Vue.js / Nuxt.js</li>
                <li>Angular</li>
                <li>SASS/SCSS</li>
                <li>Tailwind CSS</li>
            </ul>
        </div>
        
        <div class="skill-category">
            <h3>Backend Technologies</h3>
            <ul>
                <li>Node.js / Express.js</li>
                <li>Python / Django</li>
                <li>RESTful APIs</li>
                <li>GraphQL</li>
                <li>Microservices</li>
            </ul>
        </div>
        
        <div class="skill-category">
            <h3>Database & Cloud</h3>
            <ul>
                <li>PostgreSQL / MySQL</li>
                <li>MongoDB</li>
                <li>Redis</li>
                <li>AWS / GCP</li>
                <li>Docker / Kubernetes</li>
            </ul>
        </div>
    </div>
</section>

<section class="cv-section">
    <h2>Professional Experience</h2>
    
    <div class="experience-item">
        <div class="experience-header">
            <h3>Senior Software Developer</h3>
            <span class="company">Tech Company Inc.</span>
            <span class="period">Jan 2022 - Present</span>
        </div>
        <div class="experience-location">Remote / New York, NY</div>
        <ul class="experience-details">
            <li>Led development of customer-facing web applications serving 100K+ users using React, TypeScript, and Node.js</li>
            <li>Architected and implemented microservices infrastructure resulting in 40% improvement in system scalability</li>
            <li>Mentored team of 4 junior developers and established code review processes improving code quality by 30%</li>
            <li>Collaborated with product managers and designers to deliver user-centered solutions on time and within budget</li>
            <li>Technologies: React, TypeScript, Node.js, PostgreSQL, AWS, Docker</li>
        </ul>
    </div>
    
    <div class="experience-item">
        <div class="experience-header">
            <h3>Full-Stack Developer</h3>
            <span class="company">Startup Solutions Ltd.</span>
            <span class="period">Mar 2020 - Dec 2021</span>
        </div>
        <div class="experience-location">San Francisco, CA</div>
        <ul class="experience-details">
            <li>Developed and maintained multiple web applications using modern JavaScript frameworks</li>
            <li>Built RESTful APIs and integrated third-party services for e-commerce platform</li>
            <li>Implemented automated testing strategies reducing bug reports by 50%</li>
            <li>Optimized application performance resulting in 60% faster load times</li>
            <li>Technologies: Vue.js, Node.js, MongoDB, Express.js, Jest</li>
        </ul>
    </div>
    
    <div class="experience-item">
        <div class="experience-header">
            <h3>Junior Developer</h3>
            <span class="company">Digital Agency Co.</span>
            <span class="period">Jun 2018 - Feb 2020</span>
        </div>
        <div class="experience-location">Boston, MA</div>
        <ul class="experience-details">
            <li>Developed responsive websites for various clients using HTML, CSS, and JavaScript</li>
            <li>Collaborated with design team to implement pixel-perfect user interfaces</li>
            <li>Participated in agile development process and daily standups</li>
            <li>Gained experience in version control, deployment, and project management tools</li>
            <li>Technologies: HTML, CSS, JavaScript, PHP, WordPress</li>
        </ul>
    </div>
</section>

<section class="cv-section">
    <h2>Education</h2>
    
    <div class="education-item">
        <div class="education-header">
            <h3>Bachelor of Science in Computer Science</h3>
            <span class="institution">University of Technology</span>
            <span class="period">2014 - 2018</span>
        </div>
        <p>Relevant Coursework: Data Structures, Algorithms, Software Engineering, Database Systems, Web Development</p>
        <p>GPA: 3.8/4.0</p>
    </div>
</section>

<section class="cv-section">
    <h2>Certifications</h2>
    <ul class="certifications-list">
        <li>AWS Certified Developer - Associate (2021)</li>
        <li>Google Cloud Professional Developer (2022)</li>
        <li>MongoDB Certified Developer (2020)</li>
    </ul>
</section>

<section class="cv-section">
    <h2>Projects & Achievements</h2>
    <ul class="achievements-list">
        <li>Led migration of legacy system to modern architecture, reducing maintenance costs by 45%</li>
        <li>Open source contributor with 500+ GitHub stars across various projects</li>
        <li>Speaker at tech conferences and meetups on modern web development practices</li>
        <li>Completed advanced courses in System Design and Cloud Architecture</li>
    </ul>
</section>
