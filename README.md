# Personal Portfolio & Blog

A modern, responsive Jekyll website template for personal portfolios and blogs, designed for GitHub Pages deployment.

## Features

- **Responsive Design**: Mobile-first approach with modern CSS Grid and Flexbox
- **CV/Resume Section**: Detailed professional experience and skills showcase
- **Portfolio Showcase**: Project gallery with filtering capabilities
- **Blog Functionality**: Jekyll-powered blog with categories and tags
- **Contact Form**: Ready-to-use contact form (integrates with Formspree)
- **SEO Optimized**: Built-in SEO meta tags and structured data
- **Fast Loading**: Optimized assets and minimal dependencies
- **GitHub Pages Ready**: Deploy directly to GitHub Pages

## Quick Start

1. **Fork this repository** or use it as a template
2. **Clone to your local machine**:
   ```bash
   git clone https://github.com/yourusername/mypage.git
   cd mypage
   ```

3. **Install dependencies**:
   ```bash
   bundle install
   ```

4. **Run locally**:
   ```bash
   bundle exec jekyll serve
   ```

5. **Visit** `http://localhost:4000` to see your site

## Customization

### Basic Configuration

Edit `_config.yml` to customize:

```yaml
title: Your Name - Portfolio & Blog
email: your.email@example.com
description: "Your description here"
url: "https://yourusername.github.io"
twitter_username: yourusername
github_username: yourusername
linkedin_username: yourusername
```

### Personal Information

1. **Profile Image**: Replace `/assets/images/profile.jpg` with your photo
2. **About Page**: Edit `about.md` with your information
3. **CV Page**: Update `cv.md` with your experience and skills
4. **Portfolio**: Add your projects in `portfolio.md`

### Adding Blog Posts

Create new posts in the `_posts` directory:

```markdown
---
title: "Your Post Title"
date: 2024-01-01
categories: [Category1, Category2]
tags: [tag1, tag2, tag3]
excerpt: "Short description of your post"
featured_image: "/assets/images/post-image.jpg"
---

Your post content here...
```

### Contact Form Setup

1. Sign up at [Formspree](https://formspree.io/)
2. Replace `your-form-id` in `contact.md` with your Formspree form ID
3. Update contact information in the same file

### Adding Projects

Add project images to `/assets/images/` and update the portfolio section in `portfolio.md`:

```markdown
<div class="portfolio-item" data-category="web">
    <div class="portfolio-image">
        <img src="/assets/images/your-project.jpg" alt="Project Name">
        <!-- ... -->
    </div>
    <!-- ... -->
</div>
```

## GitHub Pages Deployment

1. **Enable GitHub Pages** in your repository settings
2. **Set source** to "Deploy from a branch"
3. **Select branch** `main` and folder `/ (root)`
4. **Custom domain** (optional): Add your domain in settings

Your site will be available at `https://yourusername.github.io/repository-name`

## Folder Structure

```
mypage/
├── _layouts/          # HTML layouts
├── _posts/           # Blog posts
├── _config.yml       # Site configuration
├── assets/
│   ├── css/         # Stylesheets
│   ├── js/          # JavaScript files
│   └── images/      # Images and media
├── index.html       # Homepage
├── about.md         # About page
├── cv.md           # CV/Resume page
├── portfolio.md    # Portfolio page
├── blog.md         # Blog listing page
├── contact.md      # Contact page
└── Gemfile         # Ruby dependencies
```

## Technologies Used

- **Jekyll**: Static site generator
- **HTML5/CSS3**: Modern web standards
- **JavaScript**: Interactive functionality
- **Font Awesome**: Icons
- **Google Fonts**: Typography (Inter)
- **GitHub Pages**: Hosting

## Browser Support

- Chrome (latest)
- Firefox (latest)
- Safari (latest)
- Edge (latest)
- Mobile browsers

## License

This project is open source and available under the [MIT License](LICENSE).

## Contributing

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add some amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## Support

If you have any questions or need help customizing this template:

- [Open an issue](https://github.com/yourusername/mypage/issues)
- [Check the wiki](https://github.com/yourusername/mypage/wiki)
- Contact me via the website's contact form

## Acknowledgments

- Font Awesome for icons
- Google Fonts for typography
- Jekyll community for the amazing static site generator
- GitHub for free hosting with GitHub Pages

---

**Made with ❤️ for developers who want to showcase their work online.**
