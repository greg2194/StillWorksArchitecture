# Still Works Architecture Website

This is the static website for Still Works Architecture, built with HTML, CSS, and JavaScript.

## Files Included

- `index.html` - Homepage with hero image
- `about.html` - About page with bio
- `work.html` - Work/Projects page with hover preview functionality
- `contact.html` - Contact information page
- `style.css` - Main stylesheet
- `README.md` - This file

## Project Images Folder

You'll need to create an `images` folder in the root directory and add your project images there. The Work page is currently set up with placeholder image paths:
- `images/project1.jpg`
- `images/project2.jpg`
- etc.

## Customizing the Work Page

To add your own projects:

1. Open `work.html` in a text editor
2. Find the projects list (around line 31)
3. Replace each project line with your own:
   ```html
   <li><a href="#" data-image="images/your-image.jpg">Your Project Name</a></li>
   ```
4. Make sure your image files are in the `images/` folder

You can also link each project to a dedicated page by replacing the `#` with a URL or page name.

## Setup Instructions for GitHub and Netlify

### Step 1: Create a GitHub Account (if you don't have one)

1. Go to [github.com](https://github.com)
2. Click "Sign up" and follow the prompts
3. Verify your email address

### Step 2: Create a New Repository

1. Log in to GitHub
2. Click the "+" icon in the top-right corner
3. Select "New repository"
4. Name it something like `stillworks-website`
5. Keep it **Public** (required for free Netlify hosting)
6. Do NOT initialize with README, .gitignore, or license
7. Click "Create repository"

### Step 3: Upload Your Files to GitHub

**Option A: Using GitHub's Web Interface (Easiest)**

1. On your new repository page, click "uploading an existing file"
2. Drag and drop ALL files from this folder:
   - index.html
   - about.html
   - work.html
   - contact.html
   - style.css
   - images folder (once you've created it and added your images)
3. Add a commit message like "Initial commit"
   - Scroll down to the bottom of the page
   - Under "Commit changes" type in "Initial commit" into the text box
4. Click "Commit changes"

**Option B: Using Git Command Line (Recommended for easier long-term maintenance)**

Git command line gives you more control and makes updates faster once you're comfortable with it. Here's a comprehensive guide:

**Initial Setup (One-time only):**

1. **Install Git**
   - Mac: Git usually comes pre-installed. Check by opening Terminal and typing `git --version`
     - If not installed, it will prompt you to install Xcode Command Line Tools
   - Windows: Download from [git-scm.com](https://git-scm.com)
   - Linux: `sudo apt-get install git` (Ubuntu/Debian) or `sudo yum install git` (Fedora)

2. **Configure Git (First time only)**
   ```bash
   # Set your name (this appears in commit history)
   git config --global user.name "Your Name"
   
   # Set your email (use the same email as your GitHub account)
   git config --global user.email "your.email@example.com"
   
   # Verify your settings
   git config --list
   ```

3. **Navigate to Your Project Folder**
   ```bash
   # On Mac/Linux, use 'cd' to change directory
   cd /path/to/your/project
   # Example: cd ~/Documents/stillworks-website
   
   # On Windows
   cd C:\path\to\your\project
   # Example: cd C:\Users\YourName\Documents\stillworks-website
   
   # Tip: You can drag a folder into Terminal (Mac) or Command Prompt (Windows)
   # and it will auto-fill the path
   ```

4. **Initialize Git Repository**
   ```bash
   # Initialize git in your project folder
   git init
   
   # Add all files to git tracking
   git add .
   
   # Create your first commit
   git commit -m "Initial commit"
   
   # Connect to your GitHub repository (replace YOUR-USERNAME and REPO-NAME)
   git remote add origin https://github.com/YOUR-USERNAME/stillworks-website.git
   
   # Set the default branch name to 'main'
   git branch -M main
   
   # Push your files to GitHub
   git push -u origin main
   ```
   
   **Note:** You may be prompted to authenticate with GitHub:
   - GitHub will ask you to sign in through your browser
   - Or you may need to create a Personal Access Token at [github.com/settings/tokens](https://github.com/settings/tokens)

**Daily Workflow: Making Updates**

Once set up, updating your site is simple. Here's the typical workflow:

```bash
# 1. Navigate to your project folder
cd /path/to/your/project

# 2. Check which files you've changed (optional but helpful)
git status

# 3. Add your changes
# Add all changed files:
git add .
# Or add specific files:
git add style.css work.html

# 4. Commit your changes with a descriptive message
git commit -m "Updated project list and fixed contact form"

# 5. Push to GitHub (which auto-deploys to Netlify)
git push
```

That's it! Your site will automatically update on Netlify within 1-2 minutes.

**Common Git Commands Explained:**

```bash
# Check status of your files (what's changed, what's staged)
git status

# See what changes you've made to files
git diff

# Add all changed files to staging
git add .

# Add specific file to staging
git add filename.html

# Commit staged changes
git commit -m "Your message describing what you changed"

# Push commits to GitHub
git push

# Pull latest changes from GitHub (if you edit on multiple computers)
git pull

# See your commit history
git log

# See simplified commit history
git log --oneline

# Undo changes to a file (before committing)
git checkout -- filename.html

# Create a new branch (for experimental changes)
git branch new-feature
git checkout new-feature
# Or do both at once:
git checkout -b new-feature

# Switch back to main branch
git checkout main

# Merge a branch into main
git checkout main
git merge new-feature
```

**Practical Examples:**

**Example 1: Updating project images**
```bash
cd ~/Documents/stillworks-website
# Add new images to the images/ folder
# Edit work.html to reference new images
git add .
git commit -m "Added 3 new projects to portfolio"
git push
```

**Example 2: Changing contact information**
```bash
cd ~/Documents/stillworks-website
# Edit contact.html with new phone number
git add contact.html
git commit -m "Updated phone number"
git push
```

**Example 3: Redesigning the about page**
```bash
cd ~/Documents/stillworks-website
# Edit about.html and style.css
git add about.html style.css
git commit -m "Redesigned about page layout"
git push
```

**Troubleshooting Common Issues:**

**Problem: "fatal: not a git repository"**
```bash
# Solution: You're not in your project folder. Navigate there first:
cd /path/to/your/project
```

**Problem: "Your branch is behind 'origin/main'"**
```bash
# Solution: Pull the latest changes first:
git pull
# Then make your changes and push
```

**Problem: Merge conflict**
```bash
# This happens if you edited files both locally and on GitHub
# Open the conflicted files (git will tell you which ones)
# Look for <<<<<<< HEAD markers and resolve conflicts manually
# Then:
git add .
git commit -m "Resolved merge conflict"
git push
```

**Problem: Accidentally committed the wrong files**
```bash
# Undo the last commit but keep your changes:
git reset --soft HEAD~1
# Make corrections, then commit again
```

**Best Practices:**

1. **Commit often** - Small, frequent commits are better than large ones
2. **Write clear commit messages** - "Updated about page" is better than "changes"
3. **Check status before committing** - `git status` shows what you're about to commit
4. **Pull before you start working** - If you work on multiple computers, always pull first
5. **Don't commit sensitive data** - API keys, passwords, etc. should never be committed

**Quick Reference Card:**

```
SETUP (once):
  git init                     → Start tracking a folder
  git remote add origin URL    → Connect to GitHub
  
DAILY USE:
  git status                   → What's changed?
  git add .                    → Stage all changes
  git commit -m "message"      → Save changes
  git push                     → Upload to GitHub
  
USEFUL:
  git diff                     → See specific changes
  git log                      → View history
  git pull                     → Download latest from GitHub
```

**Time Savings:**

- Web interface: Click, drag, type message, click, wait → ~2 minutes per update
- Command line: `git add . && git commit -m "message" && git push` → ~10 seconds

Once you're comfortable, you can update your entire site in a single line!

### Step 4: Set Up Netlify

1. Go to [netlify.com](https://netlify.com)
2. Click "Sign up" and choose "Sign up with GitHub"
3. Authorize Netlify to access your GitHub account
4. Once logged in, click "Add new site" → "Import an existing project"
5. Click "Deploy with GitHub"
6. Authorize Netlify if prompted
7. Select your `stillworks-website` repository
8. Leave the build settings as default (they should be empty)
9. Click "Deploy site"

### Step 5: Configure Your Custom Domain (Optional)

1. In Netlify, go to "Site settings" → "Domain management"
2. Click "Add custom domain"
3. Enter your domain (e.g., `stillworksarch.com`)
4. Follow Netlify's instructions to update your domain's DNS settings
5. Netlify will automatically provide SSL/HTTPS

### Step 6: Making Updates

Once you're set up with Git command line (recommended), updating is quick:

**Command Line (Fast!):**
```bash
# 1. Navigate to your project
cd /path/to/your/project

# 2. Make your edits to HTML/CSS files

# 3. Update site with three commands:
git add .
git commit -m "Description of changes"
git push

# Or do it all in one line:
git add . && git commit -m "Updated about page" && git push
```

Netlify detects the changes and redeploys automatically (~1 minute).

**GitHub Web Interface (Alternative):**

If you prefer not to use command line:

1. Edit your files locally (HTML, CSS, or images)
2. Go to your GitHub repository
3. Click "Add file" → "Upload files"
4. Drag your updated files
5. Add a commit message describing what you changed
6. Click "Commit changes"
7. Netlify will automatically detect the changes and redeploy your site (takes ~1 minute)

## Tips for Future Edits

### Adding New Projects
1. Add your project image to the `images/` folder
2. Open `work.html`
3. Add a new line in the projects list:
   ```html
   <li><a href="#" data-image="images/new-project.jpg">New Project Name</a></li>
   ```
4. Upload the updated `work.html` and new image to GitHub

### Changing Text
- Open the relevant HTML file (about.html, contact.html, etc.)
- Find the text you want to change
- Edit it directly
- Upload the updated file to GitHub

### Changing Colors
- Open `style.css`
- At the top, you'll see color variables:
  ```css
  --color-text: #1a1a1a;
  --color-background: #ffffff;
  --color-accent: #2a2a2a;
  ```
- Change these hex color codes to your preferred colors
- Upload the updated CSS to GitHub

## Need Help?

- **GitHub Docs**: [docs.github.com](https://docs.github.com)
- **Netlify Docs**: [docs.netlify.com](https://docs.netlify.com)
- **HTML/CSS Reference**: [developer.mozilla.org](https://developer.mozilla.org)

## Current Image Sources

All images are currently being served from your existing Squarespace site. For better performance and to avoid dependency on Squarespace:

1. Download all images from your Squarespace site
2. Add them to your `images/` folder
3. Update the image paths in your HTML files to point to your local images
