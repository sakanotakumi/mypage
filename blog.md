---
layout: page
title: Blog
description: Thoughts, tutorials, and insights on technology and development.
---

<div class="blog-intro">
    <p class="lead">
        Welcome to my blog where I share my thoughts on technology, programming tutorials, 
        and insights from my journey as a developer. I believe in learning in public and 
        contributing to the developer community.
    </p>
</div>

<div class="blog-categories">
    <h3>Categories</h3>
    <div class="categories-list">
        <a href="#" class="category-tag">All Posts</a>
        <a href="#" class="category-tag">JavaScript</a>
        <a href="#" class="category-tag">React</a>
        <a href="#" class="category-tag">Node.js</a>
        <a href="#" class="category-tag">Tutorials</a>
        <a href="#" class="category-tag">Career</a>
    </div>
</div>

<div class="posts-grid">
    {% for post in site.posts %}
        <article class="post-card">
            {% if post.featured_image %}
            <div class="post-image">
                <img src="{{ post.featured_image }}" alt="{{ post.title }}">
            </div>
            {% endif %}
            
            <div class="post-content">
                <div class="post-meta">
                    <time datetime="{{ post.date | date_to_xmlschema }}">
                        {{ post.date | date: "%B %d, %Y" }}
                    </time>
                    {% if post.categories.size > 0 %}
                        <span class="post-category">{{ post.categories | first }}</span>
                    {% endif %}
                </div>
                
                <h2><a href="{{ post.url | relative_url }}">{{ post.title }}</a></h2>
                <p>{{ post.excerpt | strip_html | truncatewords: 25 }}</p>
                
                {% if post.tags.size > 0 %}
                <div class="post-tags">
                    {% for tag in post.tags limit:3 %}
                    <span class="tag">{{ tag }}</span>
                    {% endfor %}
                </div>
                {% endif %}
                
                <a href="{{ post.url | relative_url }}" class="read-more">Read more →</a>
            </div>
        </article>
    {% endfor %}
</div>

{% if site.posts.size == 0 %}
<div class="no-posts">
    <h3>No posts yet</h3>
    <p>Stay tuned for upcoming articles and tutorials!</p>
</div>
{% endif %}
