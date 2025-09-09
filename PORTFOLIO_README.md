# Personal Portfolio Website

A modern, responsive portfolio website built with React, TypeScript, and TailwindCSS featuring a cosmic-themed design with dark/light mode support.

## ✨ Features

- 🌓 **Dark/Light Mode Toggle** - Seamless theme switching with system preference detection
- 📱 **Fully Responsive** - Works perfectly on all devices and screen sizes
- 🎨 **Modern Design** - Apple-inspired clean aesthetics with cosmic theme
- ⚡ **Fast Performance** - Optimized for speed and smooth animations
- 🚀 **GitHub Pages Ready** - Easy deployment to GitHub Pages
- 🎯 **SEO Optimized** - Proper meta tags and semantic HTML

## 🏗️ Built With

- **React 18** - Modern React with hooks
- **TypeScript** - Type safety and better development experience
- **TailwindCSS** - Utility-first CSS framework
- **Vite** - Fast build tool and development server
- **Lucide React** - Beautiful icons
- **Next Themes** - Dark/light mode implementation
- **Shadcn/ui** - Accessible UI components

## 📁 Project Structure

```
src/
├── components/           # Reusable UI components
│   ├── ui/              # Shadcn/ui components
│   ├── Navigation.tsx   # Header navigation with theme toggle
│   ├── Hero.tsx         # Hero section with cosmic background
│   ├── About.tsx        # About me section
│   ├── Projects.tsx     # Portfolio projects showcase
│   ├── Experience.tsx   # Work experience timeline
│   ├── Resume.tsx       # Resume section with download
│   ├── Contact.tsx      # Contact form and information
│   └── Footer.tsx       # Footer with social links
├── assets/              # Static assets (images, etc.)
├── hooks/               # Custom React hooks
├── lib/                 # Utility functions
└── pages/               # Page components
```

## 🚀 Quick Start

### Prerequisites
- Node.js 16+ and npm/yarn

### Installation
1. Clone the repository
2. Install dependencies: `npm install`
3. Start development server: `npm run dev`
4. Open http://localhost:8080

### Customization Guide

#### 1. Personal Information
Replace placeholder content in these files with your information:

**Navigation.tsx:**
- Line 25: Replace "Your Name" with your actual name

**Hero.tsx:**
- Line 13: Add your name
- Line 16-19: Add your title and description
- Line 31-47: Update social media links

**About.tsx:**
- Line 32-38: Write your personal story
- Line 41-45: Add your approach/philosophy
- Line 7-9: Update your skills

**Experience.tsx:**
- Line 8-46: Replace with your actual work experience

**Resume.tsx:**
- Line 8-13: Add your education details
- Line 15-19: List your certifications
- Line 21-26: Highlight your achievements
- Line 48-58: Update resume download links

**Contact.tsx:**
- Line 52-66: Update your contact information
- Line 68-82: Update social media profiles
- Line 117: Implement form submission logic

**Footer.tsx:**
- Line 8-20: Update social links
- Line 27: Replace "Your Name"

#### 2. Resume File
- Add your resume PDF to the `public/` folder
- Update the download links in `Resume.tsx` (lines 48-58)

#### 3. Project Images
Replace placeholder project images in `Projects.tsx`:
- Add your project screenshots to `src/assets/`
- Import them and update the `image` property for each project

#### 4. Styling Customization
The design system is defined in:
- `src/index.css` - CSS variables and utility classes
- `tailwind.config.ts` - Theme configuration

## 📤 Deployment to GitHub Pages

### Method 1: Using GitHub Actions (Recommended)

1. **Enable GitHub Pages:**
   - Go to your repository Settings → Pages
   - Select "GitHub Actions" as the source

2. **Create Workflow File:**
   Create `.github/workflows/deploy.yml`:
   ```yaml
   name: Deploy to GitHub Pages
   
   on:
     push:
       branches: [ main ]
   
   permissions:
     contents: read
     pages: write
     id-token: write
   
   jobs:
     build-and-deploy:
       runs-on: ubuntu-latest
       steps:
         - uses: actions/checkout@v4
         
         - name: Setup Node.js
           uses: actions/setup-node@v4
           with:
             node-version: '18'
             cache: 'npm'
         
         - name: Install dependencies
           run: npm ci
         
         - name: Build
           run: npm run build
           
         - name: Setup Pages
           uses: actions/configure-pages@v4
           
         - name: Upload artifact
           uses: actions/upload-pages-artifact@v3
           with:
             path: ./dist
             
         - name: Deploy to GitHub Pages
           uses: actions/deploy-pages@v4
   ```

3. **Configure Vite for GitHub Pages:**
   Update `vite.config.ts`:
   ```typescript
   export default defineConfig(({ mode }) => ({
     base: mode === 'production' ? '/your-repo-name/' : '/',
     // ... rest of config
   }));
   ```

4. **Push Changes:**
   - Commit and push your changes
   - GitHub Actions will automatically build and deploy

### Method 2: Manual Deployment

1. **Build the project:**
   ```bash
   npm run build
   ```

2. **Deploy to gh-pages branch:**
   ```bash
   npm install -g gh-pages
   gh-pages -d dist
   ```

3. **Configure GitHub Pages:**
   - Go to Settings → Pages
   - Select "Deploy from a branch"
   - Choose "gh-pages" branch

## 🎨 Design System

The website uses a cosmic-themed design system with:

- **Colors:** Purple and blue gradients with cosmic accents
- **Typography:** System fonts (SF Pro on macOS, Segoe UI on Windows)
- **Components:** Glass morphism effects and smooth animations
- **Layout:** Apple-inspired spacing and clean aesthetics

## 📝 Form Integration

The contact form is ready for integration with:
- **Formspree** - Simple form backend
- **Netlify Forms** - If hosting on Netlify
- **Custom API** - Your own backend service

Update the form submission logic in `Contact.tsx` line 117.

## 🔧 Customization Tips

1. **Add More Sections:** Create new components and add them to `Index.tsx`
2. **Change Theme Colors:** Update CSS variables in `index.css`
3. **Add Animations:** Use the existing animation classes or create new ones
4. **Optimize Images:** Use WebP format and lazy loading for better performance
5. **Add Blog:** Create a blog section with markdown support

## 📱 Browser Support

- Chrome (last 2 versions)
- Firefox (last 2 versions)
- Safari (last 2 versions)
- Edge (last 2 versions)

## 📄 License

MIT License - feel free to use this template for your own portfolio!

## 🤝 Contributing

If you find any bugs or have suggestions for improvements, please feel free to open an issue or submit a pull request.

---

**Made with ❤️ using React, TypeScript, and TailwindCSS**