# 🎨 Customization Guide

This guide will help you personalize your portfolio website with your own information.

## 📝 Step-by-Step Customization

### 1. Basic Information

#### Update Your Name
**Files to edit:**
- `src/components/Navigation.tsx` (line 25)
- `src/components/Hero.tsx` (line 13)
- `src/components/Footer.tsx` (line 27)
- `index.html` (line 6, 8, 10)

**What to change:**
Replace "Your Name" with your actual name.

#### Update Your Title & Description
**File:** `src/components/Hero.tsx` (lines 16-19)
**What to change:**
```tsx
<p className="text-xl sm:text-2xl lg:text-3xl text-muted-foreground mb-8 max-w-3xl mx-auto">
  {/* Replace this with your actual title */}
  Senior Full Stack Developer & UI/UX Designer
  <br />
  <span className="text-cosmic-primary">Crafting digital experiences that inspire</span>
</p>
```

### 2. Contact Information

#### Social Media Links
**Files to edit:**
- `src/components/Hero.tsx` (lines 31-47)
- `src/components/Footer.tsx` (lines 8-20)
- `src/components/Contact.tsx` (lines 68-82)

**What to change:**
```tsx
// Update these URLs with your actual profiles
<a href="https://github.com/yourusername" ... >
<a href="https://linkedin.com/in/yourprofile" ... >
<a href="mailto:your.email@example.com" ... >
```

#### Contact Details
**File:** `src/components/Contact.tsx` (lines 52-66)
**What to change:**
```tsx
const contactInfo = [
  {
    icon: Mail,
    label: "Email",
    value: "your.email@example.com",
    link: "mailto:your.email@example.com"
  },
  {
    icon: Phone,
    label: "Phone", 
    value: "+1 (555) 123-4567",
    link: "tel:+15551234567"
  },
  {
    icon: MapPin,
    label: "Location",
    value: "Your City, State",
    link: null
  }
];
```

### 3. About Section

#### Personal Story
**File:** `src/components/About.tsx` (lines 32-45)
**What to change:**
Replace the placeholder text with your actual background and philosophy.

#### Skills
**File:** `src/components/About.tsx` (lines 7-9)
**What to change:**
```tsx
const skills = [
  // Replace with your actual skills
  "JavaScript", "TypeScript", "React", "Next.js", "Python", 
  "TailwindCSS", "AWS", "Docker", "etc."
];
```

### 4. Experience Section

**File:** `src/components/Experience.tsx` (lines 8-46)
**What to change:**
Replace the entire experiences array with your actual work history:

```tsx
const experiences = [
  {
    title: "Your Job Title",
    company: "Company Name",
    location: "City, State/Remote", 
    period: "Start Year - End Year/Present",
    description: [
      "Your key achievement or responsibility",
      "Another important accomplishment",
      "Third bullet point about your role"
    ],
    technologies: ["Tech1", "Tech2", "Tech3"]
  },
  // Add more experiences...
];
```

### 5. Projects Section

**File:** `src/components/Projects.tsx` (lines 8-35)
**What to change:**

```tsx
const projects = [
  {
    title: "Your Project Name",
    description: "Brief description of what your project does and the problem it solves.",
    image: "/path-to-your-project-image.jpg", // Add image to public folder
    technologies: ["React", "Node.js", "PostgreSQL"], // Your tech stack
    liveUrl: "https://your-project-live-url.com",
    githubUrl: "https://github.com/yourusername/project-repo",
    featured: true // Set to true for main projects
  },
  // Add more projects...
];
```

### 6. Resume Section

#### Education
**File:** `src/components/Resume.tsx` (lines 8-13)
**What to change:**
```tsx
const education = [
  {
    degree: "Your Degree",
    school: "Your University",
    period: "Start Year - End Year", 
    details: "Relevant coursework, GPA, honors, etc."
  }
];
```

#### Certifications
**File:** `src/components/Resume.tsx` (lines 15-19)
**What to change:**
```tsx
const certifications = [
  "Your Certification 1",
  "Your Certification 2", 
  "Your Certification 3"
];
```

#### Resume File
1. **Add your resume PDF** to the `public/` folder
2. **Update download links** in `src/components/Resume.tsx` (lines 48-58):
```tsx
<a 
  href="/your-resume-filename.pdf"  // Update this path
  download="YourName-Resume.pdf"    // Update this filename
  ...
>
```

### 7. GitHub Pages Deployment

#### Repository Name Setup
**File:** `vite.config.ts` (line 7)
**What to change:**
```tsx
base: mode === 'production' ? '/your-actual-repo-name/' : '/',
```
Replace `your-repo-name` with your actual GitHub repository name.

#### GitHub Actions
The deployment workflow is already set up in `.github/workflows/deploy.yml`. Just push to your main branch and it will auto-deploy!

### 8. Form Integration

#### Contact Form Backend
**File:** `src/components/Contact.tsx` (line 117)

**Option 1: Formspree**
```tsx
const handleSubmit = async (e: React.FormEvent<HTMLFormElement>) => {
  e.preventDefault();
  const form = e.target as HTMLFormElement;
  const formData = new FormData(form);
  
  try {
    const response = await fetch('https://formspree.io/f/YOUR_FORM_ID', {
      method: 'POST',
      body: formData,
      headers: {
        Accept: 'application/json',
      },
    });
    
    if (response.ok) {
      toast({
        title: "Message sent!",
        description: "Thank you for your message. I'll get back to you soon!",
      });
      form.reset();
    }
  } catch (error) {
    toast({
      title: "Error",
      description: "There was a problem sending your message.",
      variant: "destructive",
    });
  }
};
```

### 9. Styling Customization

#### Colors & Theme
**File:** `src/index.css` (lines 10-30)
**What to change:**
Update the HSL color values to match your brand:
```css
:root {
  /* Update these colors to your brand colors */
  --cosmic-primary: 258 90% 66%;    /* Purple */
  --cosmic-secondary: 203 100% 70%; /* Blue */  
  --cosmic-accent: 45 93% 62%;      /* Orange */
  --cosmic-purple: 280 83% 73%;     /* Light Purple */
}
```

### 10. SEO & Meta Tags

**File:** `index.html`
**What to update:**
- Page title (line 6)
- Meta description (line 7) 
- Author name (line 8)
- Open Graph tags (lines 10-11)

### 11. Final Steps

1. **Test locally:** Run `npm run dev` to see your changes
2. **Add your resume:** Place PDF file in `public/` folder
3. **Update project images:** Add screenshots to showcase your work
4. **Push to GitHub:** Commit and push all changes
5. **Enable GitHub Pages:** Go to Settings > Pages > GitHub Actions
6. **Custom domain (optional):** Add CNAME file to public folder

## 🎯 Quick Checklist

- [ ] Updated name everywhere
- [ ] Added contact information  
- [ ] Updated social media links
- [ ] Added work experience
- [ ] Added education details
- [ ] Listed projects with images
- [ ] Added resume PDF file
- [ ] Updated repository name in vite.config.ts
- [ ] Tested contact form
- [ ] Customized colors (optional)

## 🚀 Ready to Deploy!

Once you've completed these customizations, your portfolio will be ready to deploy to GitHub Pages. The workflow is already configured - just push your changes and watch your site go live!

Need help? Check the main README for detailed deployment instructions.