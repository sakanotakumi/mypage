---
layout: page
title: Contact
description: Get in touch with me for collaborations, questions, or just to say hello.
---

<div class="contact-intro">
    <p class="lead">
        I'm always interested in hearing about new opportunities, interesting projects, 
        or just connecting with fellow developers. Feel free to reach out!
    </p>
</div>

<div class="contact-grid">
    <div class="contact-form-section">
        <h2>Send me a message</h2>
        <form class="contact-form" action="https://formspree.io/f/your-form-id" method="POST">
            <div class="form-group">
                <label for="name">Name</label>
                <input type="text" id="name" name="name" required>
            </div>
            
            <div class="form-group">
                <label for="email">Email</label>
                <input type="email" id="email" name="email" required>
            </div>
            
            <div class="form-group">
                <label for="subject">Subject</label>
                <input type="text" id="subject" name="subject" required>
            </div>
            
            <div class="form-group">
                <label for="message">Message</label>
                <textarea id="message" name="message" rows="6" required></textarea>
            </div>
            
            <button type="submit" class="btn btn-primary">Send Message</button>
        </form>
    </div>
    
    <div class="contact-info-section">
        <h2>Get in touch</h2>
        
        <div class="contact-methods">
            <div class="contact-method">
                <i class="fas fa-envelope"></i>
                <div>
                    <h3>Email</h3>
                    <p><a href="mailto:your.email@example.com">your.email@example.com</a></p>
                </div>
            </div>
            
            <div class="contact-method">
                <i class="fas fa-map-marker-alt"></i>
                <div>
                    <h3>Location</h3>
                    <p>Your City, Country</p>
                </div>
            </div>
            
            <div class="contact-method">
                <i class="fas fa-clock"></i>
                <div>
                    <h3>Response Time</h3>
                    <p>Usually within 24 hours</p>
                </div>
            </div>
        </div>
        
        <div class="social-connect">
            <h3>Connect with me</h3>
            <div class="social-links">
                {% for social in site.social %}
                <a href="{{ social.url }}" target="_blank" class="social-link" aria-label="{{ social.title }}">
                    <i class="{{ social.icon }}"></i>
                    <span>{{ social.title }}</span>
                </a>
                {% endfor %}
            </div>
        </div>
        
        <div class="availability">
            <h3>Availability</h3>
            <p>
                I'm currently open to new opportunities and interesting projects. 
                Whether you're looking for a collaborator, have a question about my work, 
                or just want to connect, I'd love to hear from you.
            </p>
        </div>
    </div>
</div>
