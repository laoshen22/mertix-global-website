# 🚀 Deployment Guide - MERTIX GLOBAL Website

This guide will help you publish your MERTIX GLOBAL website using a custom domain.

## 📋 Prerequisites

- GitHub account
- Custom domain name
- Domain registrar access

## 🌐 Publishing Options

### **Option 1: GitHub Pages (Recommended - Free)**

#### Step 1: Create GitHub Repository
1. Go to [GitHub.com](https://github.com)
2. Click "New repository"
3. Name it: `mertix-global-website`
4. Make it **Public** (required for free GitHub Pages)
5. Don't initialize with README (we already have files)

#### Step 2: Push to GitHub
```bash
# Add your GitHub repository as remote
git remote add origin https://github.com/YOUR_USERNAME/mertix-global-website.git

# Push to GitHub
git branch -M main
git push -u origin main
```

#### Step 3: Enable GitHub Pages
1. Go to your repository on GitHub
2. Click "Settings" tab
3. Scroll down to "Pages" section
4. Under "Source", select "Deploy from a branch"
5. Select "main" branch and "/ (root)" folder
6. Click "Save"

#### Step 4: Custom Domain Setup
1. In the same Pages settings, enter your custom domain
2. Check "Enforce HTTPS"
3. Click "Save"

#### Step 5: DNS Configuration
Add these DNS records at your domain registrar:

**For apex domain (example.com):**
```
Type: A
Name: @
Value: 185.199.108.153
TTL: 3600

Type: A
Name: @
Value: 185.199.109.153
TTL: 3600

Type: A
Name: @
Value: 185.199.110.153
TTL: 3600

Type: A
Name: @
Value: 185.199.111.153
TTL: 3600
```

**For www subdomain:**
```
Type: CNAME
Name: www
Value: YOUR_USERNAME.github.io
TTL: 3600
```

### **Option 2: Netlify (Free Tier)**

#### Step 1: Deploy to Netlify
1. Go to [Netlify.com](https://netlify.com)
2. Sign up/Login with GitHub
3. Click "New site from Git"
4. Choose your repository
5. Deploy settings:
   - Build command: (leave empty)
   - Publish directory: (leave empty - root)
6. Click "Deploy site"

#### Step 2: Custom Domain
1. Go to "Domain settings"
2. Click "Add custom domain"
3. Enter your domain
4. Follow DNS instructions provided

### **Option 3: Vercel (Free Tier)**

#### Step 1: Deploy to Vercel
1. Go to [Vercel.com](https://vercel.com)
2. Sign up/Login with GitHub
3. Click "New Project"
4. Import your repository
5. Deploy settings:
   - Framework Preset: Other
   - Build Command: (leave empty)
   - Output Directory: (leave empty)
6. Click "Deploy"

#### Step 2: Custom Domain
1. Go to "Settings" → "Domains"
2. Add your custom domain
3. Follow DNS instructions

## 🔧 DNS Configuration Guide

### **Common Domain Registrars:**

#### **GoDaddy:**
1. Login to GoDaddy
2. Go to "My Products" → "DNS"
3. Add the A records and CNAME as shown above

#### **Namecheap:**
1. Login to Namecheap
2. Go to "Domain List" → "Manage"
3. Go to "Advanced DNS"
4. Add the records as shown above

#### **Google Domains:**
1. Login to Google Domains
2. Select your domain
3. Go to "DNS" → "Manage custom records"
4. Add the records as shown above

## 📱 Testing Your Deployment

### **Before DNS Changes:**
- Your site will be available at: `https://YOUR_USERNAME.github.io/mertix-global-website`
- Test all functionality

### **After DNS Changes:**
- Wait 24-48 hours for DNS propagation
- Test your custom domain
- Check HTTPS is working

## 🔒 SSL/HTTPS Setup

### **GitHub Pages:**
- Automatic HTTPS for custom domains
- No additional setup required

### **Netlify/Vercel:**
- Automatic SSL certificates
- Force HTTPS in settings

## 📊 Analytics & Monitoring

### **Google Analytics:**
1. Create Google Analytics account
2. Add tracking code to `index.html` before `</head>`
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

### **Google Search Console:**
1. Add your domain to Google Search Console
2. Verify ownership
3. Submit sitemap

## 🚀 Performance Optimization

### **Image Optimization:**
- Use WebP format for images
- Compress images before uploading
- Consider lazy loading for images

### **Caching:**
- GitHub Pages: Automatic caching
- Netlify/Vercel: Built-in CDN

## 🔄 Continuous Deployment

### **Automatic Updates:**
- Push changes to GitHub
- GitHub Pages automatically updates
- Netlify/Vercel auto-deploys on push

## 📞 Support

### **Common Issues:**

1. **DNS Not Working:**
   - Wait 24-48 hours
   - Check DNS propagation with `dig` or online tools
   - Verify records are correct

2. **HTTPS Issues:**
   - Ensure HTTPS is enabled in settings
   - Check for mixed content warnings

3. **Custom Domain Not Working:**
   - Verify DNS records
   - Check domain registrar settings
   - Contact hosting provider support

## 🎯 Next Steps

1. **Choose your hosting platform** (GitHub Pages recommended)
2. **Set up your custom domain**
3. **Configure DNS records**
4. **Test thoroughly**
5. **Add analytics**
6. **Monitor performance**

---

**Need help?** Contact your domain registrar's support or the hosting platform's documentation.

**MERTIX GLOBAL PTE. LTD.** - Ready to go live! 🚀 