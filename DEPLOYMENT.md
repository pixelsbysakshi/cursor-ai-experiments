# 🚀 Deployment Guide - Sakshi Parashar Portfolio

This guide will help you deploy your portfolio to various hosting platforms. Choose the method that best suits your needs.

## 📋 Pre-Deployment Checklist

- [ ] Update personal information in `index.html`
- [ ] Replace placeholder image in `Assets/sakshi_hero.png`
- [ ] Update social media links with actual URLs
- [ ] Test contact form functionality
- [ ] Verify all links work correctly
- [ ] Test on mobile devices

## 🌐 Deployment Options

### Option 1: GitHub Pages (FREE)
**Best for:** Personal portfolios, simple static sites

1. **Create GitHub Repository**
   ```bash
   git init
   git add .
   git commit -m "Initial commit"
   git branch -M main
   git remote add origin https://github.com/USERNAME/portfolio.git
   git push -u origin main
   ```

2. **Enable GitHub Pages**
   - Go to your repository on GitHub
   - Click `Settings` → `Pages`
   - Select source: `Deploy from a branch`
   - Choose branch: `main`
   - Click `Save`

3. **Access Your Site**
   - Your site will be live at: `https://USERNAME.github.io/portfolio`
   - It may take a few minutes to deploy

### Option 2: Netlify (FREE)
**Best for:** Easy deployments, form handling, custom domains

1. **Deploy via GitHub**
   - Go to [netlify.com](https://netlify.com)
   - Click "New site from Git"
   - Connect your GitHub account
   - Select your portfolio repository
   - Netlify will auto-detect settings from `netlify.toml`
   - Click "Deploy site"

2. **Custom Domain (Optional)**
   - Go to Site settings → Domain management
   - Add custom domain
   - Follow DNS setup instructions

3. **Form Handling**
   - Netlify automatically handles form submissions
   - View submissions in Netlify dashboard

### Option 3: Vercel (FREE)
**Best for:** Fast global CDN, excellent performance

1. **Deploy via GitHub**
   - Go to [vercel.com](https://vercel.com)
   - Click "New Project"
   - Import your GitHub repository
   - Vercel will auto-detect settings from `vercel.json`
   - Click "Deploy"

2. **Custom Domain**
   - Go to Project settings → Domains
   - Add your custom domain
   - Follow DNS configuration

### Option 4: Firebase Hosting (FREE)
**Best for:** Google integration, analytics

1. **Install Firebase CLI**
   ```bash
   npm install -g firebase-tools
   ```

2. **Initialize Firebase**
   ```bash
   firebase login
   firebase init hosting
   ```

3. **Deploy**
   ```bash
   firebase deploy
   ```

## 🛠 Local Development

Test your site locally before deployment:

```bash
# Method 1: Using npm (recommended)
npm install
npm start

# Method 2: Using Python
python -m http.server 8000

# Method 3: Using PHP
php -S localhost:8000

# Method 4: Using Node.js http-server
npx http-server . -p 3000 -o
```

## 🔧 Configuration Files Explained

### `netlify.toml`
- Build settings for Netlify
- Security headers
- Cache optimization
- Redirects for SPA routing

### `vercel.json`
- Build configuration for Vercel
- Route handling
- Security headers

### `package.json`
- Project metadata
- Scripts for development
- Dependencies management

## 📊 Analytics Setup

### Google Analytics
Add to `<head>` section before closing tag:
```html
<!-- Google Analytics -->
<script async src="https://www.googletagmanager.com/gtag/js?id=GA_MEASUREMENT_ID"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag('js', new Date());
  gtag('config', 'GA_MEASUREMENT_ID');
</script>
```

### Hotjar (User Behavior)
```html
<!-- Hotjar Tracking Code -->
<script>
    (function(h,o,t,j,a,r){
        h.hj=h.hj||function(){(h.hj.q=h.hj.q||[]).push(arguments)};
        h._hjSettings={hjid:YOUR_HOTJAR_ID,hjsv:6};
        a=o.getElementsByTagName('head')[0];
        r=o.createElement('script');r.async=1;
        r.src=t+h._hjSettings.hjid+j+h._hjSettings.hjsv;
        a.appendChild(r);
    })(window,document,'https://static.hotjar.com/c/hotjar-','.js?sv=');
</script>
```

## 🚀 Performance Optimization

### Image Optimization
- Use WebP format for better compression
- Implement lazy loading
- Optimize image sizes for different devices

### SEO Enhancements
- Add structured data (JSON-LD)
- Create XML sitemap
- Optimize page loading speed
- Add meta descriptions for all pages

## 🔒 Security Best Practices

### Content Security Policy
Add to `<head>`:
```html
<meta http-equiv="Content-Security-Policy" content="default-src 'self'; script-src 'self' 'unsafe-inline' https://cdnjs.cloudflare.com; style-src 'self' 'unsafe-inline' https://fonts.googleapis.com https://cdnjs.cloudflare.com; font-src 'self' https://fonts.gstatic.com; img-src 'self' data: https:;">
```

### HTTPS
- All modern hosting platforms provide free SSL
- Always use HTTPS for production sites
- Update all links to use https://

## 📧 Contact Form Integration

### Netlify Forms (Free)
Already configured! Forms automatically work on Netlify.

### Formspree (Alternative)
```html
<form action="https://formspree.io/f/YOUR_FORM_ID" method="POST">
  <!-- Your form fields -->
</form>
```

### EmailJS (Client-side)
```javascript
// Add EmailJS integration for client-side email sending
emailjs.send("service_id", "template_id", templateParams)
```

## 🎯 Custom Domain Setup

### Purchase Domain
- Namecheap, GoDaddy, Google Domains
- Choose a professional domain name
- Consider .com, .design, .dev extensions

### DNS Configuration
1. **For Netlify:**
   - Add CNAME record: `www` → `YOUR_SITE.netlify.app`
   - Add A record: `@` → `75.2.60.5`

2. **For Vercel:**
   - Add CNAME record: `www` → `cname.vercel-dns.com`
   - Add A record: `@` → `76.76.19.61`

3. **For GitHub Pages:**
   - Add CNAME record: `www` → `USERNAME.github.io`
   - Add A records for GitHub Pages IPs

## 🚨 Troubleshooting

### Common Issues

1. **Site not loading**
   - Check if all files are uploaded
   - Verify index.html is in root directory
   - Check browser console for errors

2. **Images not showing**
   - Verify image paths are correct
   - Check if images are uploaded to Assets folder
   - Use relative paths (./Assets/image.png)

3. **Contact form not working**
   - Ensure form action is configured
   - Check if hosting platform supports forms
   - Verify form field names

4. **Mobile layout issues**
   - Test on actual devices
   - Use browser developer tools
   - Check responsive breakpoints

### Getting Help
- Check hosting platform documentation
- Use browser developer tools
- Test in incognito mode
- Clear browser cache

---

🎉 **Congratulations!** Your portfolio is now live and ready to showcase your amazing UX design work!