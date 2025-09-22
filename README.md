# LA Lights Band Website

A nostalgic website for **LA Lights**, an indie rock band from Baton Rouge, Louisiana that was active from 2005 to 2006. This Jekyll-powered static site serves as an online archive showcasing the band's brief but memorable journey through the local music scene.

## 🎸 About LA Lights

LA Lights formed in the mid-2000s as a group of friends practicing covers in a hospital supply warehouse. The band's story began with a Hurricane Katrina relief concert in August 2005, which marked their first public performance. After playing shows throughout the Gulf South region, they recorded their original material with local producer Rhett Mouton, resulting in the *Break My Fall EP*.

**Band Members:**
- **Jeremy Dailey** — Drums
- **Josh Ferrara** — Electric Guitar
- **Josh Gourgues** — Synth/Guitar
- **Josiah Granier** — Lead Vocals
- **Chris Jones** — Bass
- **Kolby Kember** — Electric Guitar

## 🚀 Live Site

The website is deployed and accessible at: **[https://lalightsband.com](https://lalightsband.com)**

## 📋 Features

### Site Sections
- **Header/Hero** - Band introduction with animated scroll indicator
- **The Story** - Detailed band history and member information
- **Our Music** - Embedded audio content including:
  - *Break My Fall EP* (SoundCloud playlist)
  - Live recordings from Christ Jam Festival
  - Basement Acoustic Sessions
  - YouTube video embed
- **Contact** - Social media links (SoundCloud)

### Technical Features
- **Responsive Design** - Mobile-friendly layout using Bootstrap
- **Smooth Scrolling Navigation** - jQuery-powered page scrolling
- **Dynamic Navbar** - Collapses on scroll with smooth transitions
- **Embedded Media** - SoundCloud players and YouTube integration
- **Custom Domain** - Configured for lalightsband.com

## 🛠 Technical Stack

### Core Technologies
- **Jekyll** - Static site generator
- **HTML5** - Semantic markup
- **CSS3** - Custom styling with Bootstrap framework
- **JavaScript** - Interactive features (jQuery)

### Dependencies & Assets
- **Bootstrap 3.3.7** - Responsive CSS framework
- **Font Awesome 4.7.0** - Icon library
- **jQuery 1.11.3** - JavaScript library
- **jQuery Easing** - Animation plugin for smooth scrolling

### Build Configuration
- **Markdown Parser**: Kramdown
- **Permalinks**: Pretty URLs
- **Custom Domain**: lalightsband.com (via CNAME)

## 📁 Project Structure

```
/workspace/
├── _config.yml          # Jekyll configuration
├── _includes/           # Reusable HTML components
│   ├── contact.html    # Contact/social section
│   ├── footer.html     # Site footer
│   ├── head.html       # HTML head with meta tags
│   ├── header.html     # Hero section
│   ├── js.html         # JavaScript includes
│   ├── map.html        # Map component (unused)
│   ├── music.html      # Music section with embeds
│   ├── nav.html        # Navigation bar
│   └── story.html      # Band story/history
├── _layouts/
│   └── default.html    # Main page layout
├── css/                # Stylesheets
│   ├── bootstrap.min.css
│   ├── grayscale.css   # Custom theme styles
│   └── font-awesome/   # Icon fonts and styles
├── js/                 # JavaScript files
│   ├── bootstrap.js
│   ├── grayscale.js    # Custom interactions
│   ├── jquery.js
│   └── jquery.easing.min.js
├── img/                # Images and assets
├── index.html          # Main page
├── CNAME              # Custom domain configuration
└── .gitignore         # Git ignore rules
```

## 🚀 Deployment

### GitHub Pages Deployment

This site is configured for automatic deployment via GitHub Pages:

1. **Repository Setup**: Host this code in a GitHub repository
2. **Pages Configuration**: Enable GitHub Pages in repository settings
3. **Custom Domain**: Add `lalightsband.com` as custom domain in Pages settings
4. **CNAME File**: The `CNAME` file in the root directory points to the custom domain

### Manual Deployment Options

#### Using Jekyll Locally
```bash
# Install Jekyll (requires Ruby and Bundler)
gem install bundler jekyll

# Install dependencies
bundle install

# Serve locally
bundle exec jekyll serve

# Build for production
bundle exec jekyll build
```

#### Using GitHub Actions (Recommended)
Create `.github/workflows/jekyll.yml`:
```yaml
name: Build and deploy Jekyll site to GitHub Pages

on:
  push:
    branches:
      - main
  workflow_dispatch:

permissions:
  contents: read
  pages: write
  id-token: write

concurrency:
  group: "pages"
  cancel-in-progress: false

jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout
        uses: actions/checkout@v4
      - name: Setup Ruby
        uses: ruby/setup-ruby@v1
        with:
          ruby-version: '3.1'
          bundler-cache: true
      - name: Build with Jekyll
        run: bundle exec jekyll build
      - name: Upload artifact
        uses: actions/upload-pages-artifact@v3
        with:
          path: ./_site

  deploy:
    environment:
      name: github-pages
      url: ${{ steps.deployment.outputs.page_url }}
    runs-on: ubuntu-latest
    needs: build
    steps:
      - name: Deploy to GitHub Pages
        id: deployment
        uses: actions/deploy-pages@v4
```

## 🎨 Design & Styling

### Theme
- **Base Color Scheme**: Black background (#000000) with white text
- **Accent Color**: Teal links (#219ab3)
- **Typography**:
  - Headers: Montserrat (uppercase, bold, letter-spaced)
  - Body: Lora serif font
- **Layout**: Bootstrap grid system with custom grayscale theme

### Interactive Elements
- **Smooth Scrolling**: 1500ms easeInOutExpo animation between sections
- **Navbar Collapse**: Responsive navigation that collapses on mobile
- **Hover Effects**: CSS transitions on links and buttons
- **Media Embeds**: Responsive SoundCloud and YouTube players

## 📱 Responsive Design

The site is fully responsive with breakpoints for:
- **Mobile**: < 767px
- **Tablet**: 768px - 991px
- **Desktop**: 992px+

## 🔧 Customization

### Site Configuration
Edit `_config.yml` to modify:
- Site title and description
- Social media links
- Color scheme
- Base URL settings

### Content Updates
- **Band Story**: Edit `_includes/story.html`
- **Music Section**: Update SoundCloud playlist URLs in `_includes/music.html`
- **Contact Info**: Modify social links in `_config.yml`

### Styling
- **Custom CSS**: Modify `css/grayscale.css`
- **Bootstrap Variables**: Override in SCSS files if needed
- **Theme Colors**: Update color variables in `_config.yml`

## 📄 License & Credits

### Original Theme
This site uses the **Grayscale theme** from Start Bootstrap, licensed under the Apache License v2.0.

### Assets
- **Bootstrap**: MIT License
- **Font Awesome**: SIL OFL 1.1 License
- **jQuery**: MIT License

### Content
All band photos, recordings, and biographical information are property of the respective band members and used with permission for this archival website.

## 🆘 Support

For questions about the website or technical issues:
- **Email**: joshferrara@gmail.com
- **SoundCloud**: [LA Lights Band](https://soundcloud.com/la-lights-band/albums)

## 📈 Future Enhancements

Potential improvements for the site:
- [ ] Add photo gallery section
- [ ] Include show dates archive
- [ ] Add band member bios with photos
- [ ] Implement contact form
- [ ] Add blog/news section
- [ ] Include merchandise links
- [ ] Add social media integration beyond SoundCloud

---

*Built with ❤️ for the Baton Rouge music scene, 2005-2006*