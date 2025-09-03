---
layout: page
title: Portfolio
description: Showcase of my projects and technical work.
permalink: /portfolio/
---

<div class="portfolio-intro">
    <p class="lead">
        Here's a collection of projects I've worked on, showcasing different technologies 
        and solving various challenges. Each project represents a learning experience and 
        demonstrates my growth as a developer.
    </p>
</div>

<div class="portfolio-filter">
    <button class="filter-btn active" data-filter="all">All Projects</button>
    <button class="filter-btn" data-filter="web">Web Apps</button>
    <button class="filter-btn" data-filter="mobile">Mobile</button>
    <button class="filter-btn" data-filter="opensource">Open Source</button>
</div>

<div class="portfolio-grid">
    <div class="portfolio-item" data-category="web">
        <div class="portfolio-image">
            <img src="/assets/images/project1.jpg" alt="E-commerce Platform">
            <div class="portfolio-overlay">
                <div class="portfolio-links">
                    <a href="https://github.com/yourusername/ecommerce-platform" target="_blank" class="btn btn-sm">
                        <i class="fab fa-github"></i> Code
                    </a>
                    <a href="https://demo.example.com" target="_blank" class="btn btn-sm btn-primary">
                        <i class="fas fa-external-link-alt"></i> Demo
                    </a>
                </div>
            </div>
        </div>
        <div class="portfolio-content">
            <h3>E-commerce Platform</h3>
            <p>
                Full-stack e-commerce solution built with React, Node.js, and PostgreSQL. 
                Features include user authentication, payment processing, and admin dashboard.
            </p>
            <div class="portfolio-tech">
                <span class="tech-tag">React</span>
                <span class="tech-tag">Node.js</span>
                <span class="tech-tag">PostgreSQL</span>
                <span class="tech-tag">Stripe API</span>
            </div>
        </div>
    </div>

    <div class="portfolio-item" data-category="web">
        <div class="portfolio-image">
            <img src="/assets/images/project2.jpg" alt="Task Management App">
            <div class="portfolio-overlay">
                <div class="portfolio-links">
                    <a href="https://github.com/yourusername/task-manager" target="_blank" class="btn btn-sm">
                        <i class="fab fa-github"></i> Code
                    </a>
                    <a href="https://tasks.example.com" target="_blank" class="btn btn-sm btn-primary">
                        <i class="fas fa-external-link-alt"></i> Demo
                    </a>
                </div>
            </div>
        </div>
        <div class="portfolio-content">
            <h3>Task Management App</h3>
            <p>
                Collaborative task management application with real-time updates using WebSocket. 
                Built with Vue.js frontend and Express.js backend.
            </p>
            <div class="portfolio-tech">
                <span class="tech-tag">Vue.js</span>
                <span class="tech-tag">Express.js</span>
                <span class="tech-tag">Socket.io</span>
                <span class="tech-tag">MongoDB</span>
            </div>
        </div>
    </div>

    <div class="portfolio-item" data-category="mobile">
        <div class="portfolio-image">
            <img src="/assets/images/project3.jpg" alt="Weather App">
            <div class="portfolio-overlay">
                <div class="portfolio-links">
                    <a href="https://github.com/yourusername/weather-app" target="_blank" class="btn btn-sm">
                        <i class="fab fa-github"></i> Code
                    </a>
                    <a href="https://play.google.com/store" target="_blank" class="btn btn-sm btn-primary">
                        <i class="fab fa-google-play"></i> Download
                    </a>
                </div>
            </div>
        </div>
        <div class="portfolio-content">
            <h3>Weather Forecast App</h3>
            <p>
                Cross-platform mobile application providing detailed weather information 
                with beautiful animations and offline support.
            </p>
            <div class="portfolio-tech">
                <span class="tech-tag">React Native</span>
                <span class="tech-tag">Redux</span>
                <span class="tech-tag">Weather API</span>
                <span class="tech-tag">Async Storage</span>
            </div>
        </div>
    </div>

    <div class="portfolio-item" data-category="opensource">
        <div class="portfolio-image">
            <img src="/assets/images/project4.jpg" alt="UI Component Library">
            <div class="portfolio-overlay">
                <div class="portfolio-links">
                    <a href="https://github.com/yourusername/ui-components" target="_blank" class="btn btn-sm">
                        <i class="fab fa-github"></i> Code
                    </a>
                    <a href="https://storybook.example.com" target="_blank" class="btn btn-sm btn-primary">
                        <i class="fas fa-book"></i> Storybook
                    </a>
                </div>
            </div>
        </div>
        <div class="portfolio-content">
            <h3>UI Component Library</h3>
            <p>
                Reusable React component library with TypeScript support, comprehensive 
                documentation, and automated testing. Published on npm.
            </p>
            <div class="portfolio-tech">
                <span class="tech-tag">React</span>
                <span class="tech-tag">TypeScript</span>
                <span class="tech-tag">Storybook</span>
                <span class="tech-tag">Jest</span>
            </div>
        </div>
    </div>

    <div class="portfolio-item" data-category="web">
        <div class="portfolio-image">
            <img src="/assets/images/project5.jpg" alt="Blog CMS">
            <div class="portfolio-overlay">
                <div class="portfolio-links">
                    <a href="https://github.com/yourusername/blog-cms" target="_blank" class="btn btn-sm">
                        <i class="fab fa-github"></i> Code
                    </a>
                    <a href="https://cms.example.com" target="_blank" class="btn btn-sm btn-primary">
                        <i class="fas fa-external-link-alt"></i> Demo
                    </a>
                </div>
            </div>
        </div>
        <div class="portfolio-content">
            <h3>Headless CMS</h3>
            <p>
                Modern content management system built with Next.js and GraphQL. 
                Features rich text editing, media management, and API-first architecture.
            </p>
            <div class="portfolio-tech">
                <span class="tech-tag">Next.js</span>
                <span class="tech-tag">GraphQL</span>
                <span class="tech-tag">Prisma</span>
                <span class="tech-tag">AWS S3</span>
            </div>
        </div>
    </div>

    <div class="portfolio-item" data-category="opensource">
        <div class="portfolio-image">
            <img src="/assets/images/project6.jpg" alt="CLI Tool">
            <div class="portfolio-overlay">
                <div class="portfolio-links">
                    <a href="https://github.com/yourusername/dev-cli" target="_blank" class="btn btn-sm">
                        <i class="fab fa-github"></i> Code
                    </a>
                    <a href="https://www.npmjs.com/package/dev-cli" target="_blank" class="btn btn-sm btn-primary">
                        <i class="fab fa-npm"></i> npm
                    </a>
                </div>
            </div>
        </div>
        <div class="portfolio-content">
            <h3>Developer CLI Tool</h3>
            <p>
                Command-line tool for automating common development tasks. 
                Built with Node.js and published on npm with comprehensive documentation.
            </p>
            <div class="portfolio-tech">
                <span class="tech-tag">Node.js</span>
                <span class="tech-tag">Commander.js</span>
                <span class="tech-tag">Inquirer.js</span>
                <span class="tech-tag">Jest</span>
            </div>
        </div>
    </div>
</div>
