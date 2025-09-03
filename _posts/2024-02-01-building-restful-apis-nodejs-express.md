---
title: "Building RESTful APIs with Node.js and Express"
date: 2024-02-01
categories: [Node.js, Backend]
tags: [nodejs, express, api, backend, tutorial]
excerpt: "Learn how to build robust and scalable RESTful APIs using Node.js and Express.js with best practices."
featured_image: "/assets/images/nodejs-api.jpg"
---

Building RESTful APIs is a fundamental skill for modern web developers. In this comprehensive guide, we'll create a complete API using Node.js and Express.js, covering everything from basic setup to advanced features like authentication and error handling.

## What is a RESTful API?

REST (Representational State Transfer) is an architectural style for designing networked applications. A RESTful API follows REST principles and uses HTTP methods to perform CRUD operations on resources.

### REST Principles

- **Stateless**: Each request contains all necessary information
- **Client-Server**: Clear separation of concerns
- **Cacheable**: Responses can be cached to improve performance
- **Uniform Interface**: Consistent way to interact with resources

## Setting Up the Project

Let's start by creating a new Node.js project:

```bash
mkdir blog-api
cd blog-api
npm init -y
npm install express mongoose dotenv bcryptjs jsonwebtoken
npm install -D nodemon
```

Create the basic project structure:

```
blog-api/
├── controllers/
├── middleware/
├── models/
├── routes/
├── config/
├── .env
├── .gitignore
└── server.js
```

## Basic Express Server

First, let's create our main server file:

```javascript
// server.js
const express = require('express');
const mongoose = require('mongoose');
require('dotenv').config();

const app = express();
const PORT = process.env.PORT || 3000;

// Middleware
app.use(express.json());
app.use(express.urlencoded({ extended: true }));

// Routes
app.use('/api/auth', require('./routes/auth'));
app.use('/api/posts', require('./routes/posts'));

// Error handling middleware
app.use((err, req, res, next) => {
  console.error(err.stack);
  res.status(500).json({ message: 'Something went wrong!' });
});

// Connect to MongoDB
mongoose.connect(process.env.MONGODB_URI, {
  useNewUrlParser: true,
  useUnifiedTopology: true,
})
.then(() => console.log('Connected to MongoDB'))
.catch(err => console.error('MongoDB connection error:', err));

app.listen(PORT, () => {
  console.log(`Server running on port ${PORT}`);
});
```

## Creating Models

Let's define our data models using Mongoose:

```javascript
// models/User.js
const mongoose = require('mongoose');
const bcrypt = require('bcryptjs');

const userSchema = new mongoose.Schema({
  username: {
    type: String,
    required: true,
    unique: true,
    trim: true,
    minlength: 3,
    maxlength: 20
  },
  email: {
    type: String,
    required: true,
    unique: true,
    lowercase: true,
    match: [/^\w+([.-]?\w+)*@\w+([.-]?\w+)*(\.\w{2,3})+$/, 'Please enter a valid email']
  },
  password: {
    type: String,
    required: true,
    minlength: 6
  },
  role: {
    type: String,
    enum: ['user', 'admin'],
    default: 'user'
  }
}, {
  timestamps: true
});

// Hash password before saving
userSchema.pre('save', async function(next) {
  if (!this.isModified('password')) return next();
  
  this.password = await bcrypt.hash(this.password, 12);
  next();
});

// Compare password method
userSchema.methods.comparePassword = async function(candidatePassword) {
  return await bcrypt.compare(candidatePassword, this.password);
};

module.exports = mongoose.model('User', userSchema);
```

```javascript
// models/Post.js
const mongoose = require('mongoose');

const postSchema = new mongoose.Schema({
  title: {
    type: String,
    required: true,
    trim: true,
    maxlength: 100
  },
  content: {
    type: String,
    required: true
  },
  author: {
    type: mongoose.Schema.Types.ObjectId,
    ref: 'User',
    required: true
  },
  tags: [{
    type: String,
    trim: true
  }],
  published: {
    type: Boolean,
    default: false
  },
  publishedAt: {
    type: Date
  }
}, {
  timestamps: true
});

// Auto-set publishedAt when published is true
postSchema.pre('save', function(next) {
  if (this.published && !this.publishedAt) {
    this.publishedAt = new Date();
  }
  next();
});

module.exports = mongoose.model('Post', postSchema);
```

## Authentication Middleware

Create middleware for authentication:

```javascript
// middleware/auth.js
const jwt = require('jsonwebtoken');
const User = require('../models/User');

const auth = async (req, res, next) => {
  try {
    const token = req.header('Authorization')?.replace('Bearer ', '');
    
    if (!token) {
      return res.status(401).json({ message: 'No token provided' });
    }

    const decoded = jwt.verify(token, process.env.JWT_SECRET);
    const user = await User.findById(decoded.userId).select('-password');
    
    if (!user) {
      return res.status(401).json({ message: 'Token is not valid' });
    }

    req.user = user;
    next();
  } catch (error) {
    res.status(401).json({ message: 'Token is not valid' });
  }
};

module.exports = auth;
```

## Controllers

Implement the business logic in controllers:

```javascript
// controllers/authController.js
const User = require('../models/User');
const jwt = require('jsonwebtoken');

const generateToken = (userId) => {
  return jwt.sign({ userId }, process.env.JWT_SECRET, { expiresIn: '7d' });
};

exports.register = async (req, res) => {
  try {
    const { username, email, password } = req.body;

    // Check if user exists
    const existingUser = await User.findOne({
      $or: [{ email }, { username }]
    });

    if (existingUser) {
      return res.status(400).json({ 
        message: 'User with this email or username already exists' 
      });
    }

    // Create user
    const user = new User({ username, email, password });
    await user.save();

    // Generate token
    const token = generateToken(user._id);

    res.status(201).json({
      message: 'User registered successfully',
      token,
      user: {
        id: user._id,
        username: user.username,
        email: user.email,
        role: user.role
      }
    });
  } catch (error) {
    res.status(400).json({ message: error.message });
  }
};

exports.login = async (req, res) => {
  try {
    const { email, password } = req.body;

    // Find user
    const user = await User.findOne({ email });
    if (!user) {
      return res.status(400).json({ message: 'Invalid credentials' });
    }

    // Check password
    const isMatch = await user.comparePassword(password);
    if (!isMatch) {
      return res.status(400).json({ message: 'Invalid credentials' });
    }

    // Generate token
    const token = generateToken(user._id);

    res.json({
      message: 'Login successful',
      token,
      user: {
        id: user._id,
        username: user.username,
        email: user.email,
        role: user.role
      }
    });
  } catch (error) {
    res.status(500).json({ message: error.message });
  }
};
```

## Routes

Define your API routes:

```javascript
// routes/posts.js
const express = require('express');
const router = express.Router();
const auth = require('../middleware/auth');
const Post = require('../models/Post');

// GET /api/posts - Get all published posts
router.get('/', async (req, res) => {
  try {
    const { page = 1, limit = 10, tags } = req.query;
    const query = { published: true };
    
    if (tags) {
      query.tags = { $in: tags.split(',') };
    }

    const posts = await Post.find(query)
      .populate('author', 'username')
      .sort({ publishedAt: -1 })
      .limit(limit * 1)
      .skip((page - 1) * limit);

    const total = await Post.countDocuments(query);

    res.json({
      posts,
      totalPages: Math.ceil(total / limit),
      currentPage: page,
      total
    });
  } catch (error) {
    res.status(500).json({ message: error.message });
  }
});

// POST /api/posts - Create new post (authenticated)
router.post('/', auth, async (req, res) => {
  try {
    const { title, content, tags, published } = req.body;
    
    const post = new Post({
      title,
      content,
      author: req.user._id,
      tags: tags || [],
      published: published || false
    });

    await post.save();
    await post.populate('author', 'username');

    res.status(201).json({
      message: 'Post created successfully',
      post
    });
  } catch (error) {
    res.status(400).json({ message: error.message });
  }
});

// PUT /api/posts/:id - Update post (authenticated, author only)
router.put('/:id', auth, async (req, res) => {
  try {
    const post = await Post.findById(req.params.id);
    
    if (!post) {
      return res.status(404).json({ message: 'Post not found' });
    }

    // Check if user is the author
    if (post.author.toString() !== req.user._id.toString()) {
      return res.status(403).json({ message: 'Not authorized' });
    }

    const updatedPost = await Post.findByIdAndUpdate(
      req.params.id,
      req.body,
      { new: true, runValidators: true }
    ).populate('author', 'username');

    res.json({
      message: 'Post updated successfully',
      post: updatedPost
    });
  } catch (error) {
    res.status(400).json({ message: error.message });
  }
});

module.exports = router;
```

## Error Handling and Validation

Implement proper error handling and input validation:

```javascript
// middleware/validation.js
const { body, validationResult } = require('express-validator');

exports.validatePost = [
  body('title')
    .trim()
    .isLength({ min: 1, max: 100 })
    .withMessage('Title must be between 1 and 100 characters'),
  body('content')
    .trim()
    .isLength({ min: 1 })
    .withMessage('Content is required'),
  (req, res, next) => {
    const errors = validationResult(req);
    if (!errors.isEmpty()) {
      return res.status(400).json({
        message: 'Validation error',
        errors: errors.array()
      });
    }
    next();
  }
];
```

## Testing the API

You can test your API using tools like Postman or curl:

```bash
# Register a new user
curl -X POST http://localhost:3000/api/auth/register \
  -H "Content-Type: application/json" \
  -d '{"username":"john","email":"john@example.com","password":"password123"}'

# Login
curl -X POST http://localhost:3000/api/auth/login \
  -H "Content-Type: application/json" \
  -d '{"email":"john@example.com","password":"password123"}'

# Create a post (with token)
curl -X POST http://localhost:3000/api/posts \
  -H "Content-Type: application/json" \
  -H "Authorization: Bearer YOUR_TOKEN" \
  -d '{"title":"My First Post","content":"This is the content","published":true}'
```

## Best Practices

1. **Use proper HTTP status codes**
2. **Implement rate limiting**
3. **Add request logging**
4. **Use environment variables for configuration**
5. **Implement proper error handling**
6. **Add input validation and sanitization**
7. **Use HTTPS in production**
8. **Implement API documentation (Swagger/OpenAPI)**

## Conclusion

Building RESTful APIs with Node.js and Express provides a solid foundation for modern web applications. Focus on security, proper error handling, and following REST conventions to create maintainable and scalable APIs.

This example covers the basics, but real-world applications would benefit from additional features like rate limiting, caching, comprehensive testing, and API documentation.
