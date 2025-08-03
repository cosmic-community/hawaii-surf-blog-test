# Hawaii Surf Blog

![Hawaii Surf Blog](https://imgix.cosmicjs.com/749a6fb0-7078-11f0-a051-23c10f41277a-photo-1502933691298-84fc14542831-1754232308122.jpg?w=1200&h=300&fit=crop&auto=format,compress)

A modern surf blog website built with Next.js and powered by Cosmic CMS. Features authentic Hawaiian surf content including daily surf reports, spot guides, and gear reviews from local experts.

## Features

- 🌊 **Dynamic Surf Content** - Real-time surf reports, spot guides, and gear reviews
- 🏄‍♂️ **Author Profiles** - Detailed pages for local surf experts and photographers  
- 🏷️ **Category Organization** - Browse content by Surf Reports, Surf Spots, and Gear Reviews
- 📱 **Responsive Design** - Optimized for all devices with mobile-first approach
- ⚡ **Performance Optimized** - Server-side rendering with Next.js 15
- 🖼️ **Image Optimization** - Automatic image processing with imgix
- 🎨 **Modern UI** - Clean design inspired by Hawaiian surf culture
- 🔍 **SEO Ready** - Optimized meta tags and structured data

## Clone this Bucket and Code Repository

Want to create your own version of this project with all the content and structure? Clone this Cosmic bucket and code repository to get started instantly:

[![Clone this Bucket and Code Repository](https://img.shields.io/badge/Clone%20this%20Bucket-29abe2?style=for-the-badge&logo=cosmic&logoColor=white)](https://app.cosmic-staging.com/projects/new?clone_bucket=688f758eb5e4a42c017a283a&clone_repository=688f909670106502cd8408ca)

## Prompts

This application was built using the following prompts to generate the content structure and code:

### Content Model Prompt

> "Create a content model for a Hawaii surf blog with posts, authors, and categories"

### Code Generation Prompt

> Build a Next.js website that uses my existing objects in this bucket

The app has been tailored to work with your existing Cosmic content structure and includes all the features requested above.

## Technologies Used

- **Next.js 15** - React framework with App Router
- **TypeScript** - Type-safe development
- **Tailwind CSS** - Utility-first CSS framework
- **Cosmic CMS** - Headless content management
- **Bun** - Fast package manager and runtime

## Getting Started

### Prerequisites

- Node.js 18+ or Bun
- A Cosmic account with the Hawaii Surf Blog bucket

### Installation

1. Clone this repository:
```bash
git clone <repository-url>
cd hawaii-surf-blog
```

2. Install dependencies:
```bash
bun install
```

3. Set up environment variables:
```bash
cp .env.example .env.local
```

Add your Cosmic credentials to `.env.local`:
```
COSMIC_BUCKET_SLUG=your-bucket-slug
COSMIC_READ_KEY=your-read-key
COSMIC_WRITE_KEY=your-write-key
```

4. Run the development server:
```bash
bun dev
```

Open [http://localhost:3000](http://localhost:3000) to view the application.

## Cosmic SDK Examples

### Fetching Surf Posts
```typescript
import { cosmic } from '@/lib/cosmic'

// Get all surf posts with author and category data
const posts = await cosmic.objects
  .find({ type: 'surf-posts' })
  .props(['id', 'title', 'slug', 'metadata'])
  .depth(1)

// Get a single post by slug
const post = await cosmic.objects
  .findOne({ 
    type: 'surf-posts', 
    slug: 'epic-session-at-pipeline-today' 
  })
  .depth(1)
```

### Filtering by Category
```typescript
// Get posts by category
const surfReports = await cosmic.objects
  .find({ 
    type: 'surf-posts',
    'metadata.category': categoryId 
  })
  .depth(1)
```

## Cosmic CMS Integration

This application integrates with your Cosmic bucket structure:

- **Surf Posts** - Blog posts with surf conditions, ratings, and spot information
- **Authors** - Surf experts and photographers with profiles and experience
- **Categories** - Content organization (Surf Reports, Surf Spots, Gear Reviews)

Each content type includes rich metadata for detailed surf information including wave height, wind conditions, surf ratings, and location data.

## Deployment

### Deploy to Vercel

1. Connect your repository to Vercel
2. Add environment variables in the Vercel dashboard
3. Deploy automatically on every push to main

### Deploy to Netlify

1. Connect your repository to Netlify
2. Set build command: `bun run build`
3. Set publish directory: `.next`
4. Add environment variables in Netlify dashboard

### Environment Variables for Production

Set these in your deployment platform:
- `COSMIC_BUCKET_SLUG`
- `COSMIC_READ_KEY`
- `COSMIC_WRITE_KEY`
<!-- README_END -->