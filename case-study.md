# Case Study: AI Social Media Automation Machine V1

## Project Summary

This project is an AI-powered social media automation system built with Make.com, OpenAI, Cloudinary, Facebook Pages, Instagram for Business, and LinkedIn.

The automation takes new RSS feed articles and turns them into platform-specific social media posts for Facebook, Instagram, and LinkedIn. It also generates an AI image for Instagram, uploads it to Cloudinary, and publishes the final post automatically.

---

## The Problem

Creating content for multiple social media platforms manually is time-consuming.

A single article or update usually needs to be rewritten differently for each platform:

* Facebook needs a short and engaging post.
* Instagram needs a caption, hashtags, and a visual.
* LinkedIn needs a more professional and insight-driven post.

Doing this manually takes time, creates repetitive work, and can slow down content publishing.

---

## The Goal

The goal of this project was to build an automated workflow that can:

1. Detect a new article from an RSS feed.
2. Analyze the article using AI.
3. Generate different content versions for each social platform.
4. Create an AI-generated image for Instagram.
5. Upload the generated image to a public image host.
6. Publish the content automatically to Facebook, Instagram, and LinkedIn.

---

## The Solution

The workflow was built in Make.com using a router-based architecture.

The RSS module watches for new feed items. Once a new article is detected, the article title, description, summary, and URL are sent to OpenAI for content analysis.

After that, a Router splits the workflow into three platform-specific branches:

### 1. Facebook Branch

The Facebook branch generates a short and engaging Facebook post and publishes it to a Facebook Page.

### 2. Instagram Branch

The Instagram branch generates an Instagram caption, creates an AI image using OpenAI, uploads the generated image to Cloudinary through an HTTP API request, and publishes the final image post to Instagram.

### 3. LinkedIn Branch

The LinkedIn branch generates a professional LinkedIn post with a strong hook, useful insights, and a soft call-to-action.

---

## Workflow Architecture

```text
RSS Feed
→ OpenAI Content Analysis
→ Router
   → Facebook Post Generator → Facebook Page Publishing
   → Instagram Caption Generator → AI Image Generation → Cloudinary Upload → Instagram Publishing
   → LinkedIn Post Generator → LinkedIn Publishing
```

---

## Tools Used

* Make.com
* OpenAI / ChatGPT
* RSS Feed
* Cloudinary
* HTTP API
* Facebook Pages
* Instagram for Business
* LinkedIn

---

## Key Automation Features

* RSS feed monitoring
* AI content analysis
* Platform-specific post generation
* AI-generated image creation
* Cloudinary image hosting
* Instagram image publishing
* Facebook Page publishing
* LinkedIn publishing
* Router-based workflow structure

---

## Challenges Faced

One of the main challenges was Instagram publishing.

Instagram requires a public image URL, while OpenAI image generation returns the image as file data. To solve this, the workflow uploads the generated image to Cloudinary first, then uses the public Cloudinary image URL in the Instagram publishing module.

Another challenge was making sure each platform receives content in the correct style instead of using the same text everywhere.

---

## Result

The final automation successfully published AI-generated content to:

* Facebook
* Instagram
* LinkedIn

The system can now take an RSS article and automatically turn it into multi-platform social media content.

---

## Business Value

This type of automation can help:

* Content creators publish faster.
* Small businesses reduce manual content work.
* Marketing teams repurpose articles across platforms.
* Agencies build scalable content systems for clients.
* Freelancers offer AI-powered social media automation services.

---

## Future Improvements

Future versions may include:

* Google Sheets logging
* Telegram success notifications
* Error handling
* Duplicate post prevention
* Approval workflow before publishing
* YouTube video-to-social-content repurposing
* Notion content calendar integration

---

## What I Learned

This project helped me practice:

* Make.com scenario design
* OpenAI prompt engineering
* API integration
* Router-based workflow architecture
* Cloudinary image hosting
* Social media automation
* Portfolio project documentation

