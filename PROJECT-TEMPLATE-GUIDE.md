# How to Create New Project Pages

## Step 1: Copy the Template

1. Make a copy of `project-template.html`
2. Rename it to something like `project-name.html` (use lowercase, hyphens instead of spaces)
   - Example: `barn-renovation.html`, `residential-addition.html`, etc.

## Step 2: Edit the Content

Open your new project file and replace:

1. **Page Title** (line 6):
   ```html
   <title>Project Name — Still Works Architecture</title>
   ```
   Change to your actual project name

2. **Project Heading** (line 29):
   ```html
   <h1>Project Name</h1>
   ```

3. **Description** (lines 31-35):
   Replace the placeholder paragraphs with your project description

4. **Project Details** (lines 37-39):
   Update Location, Year, and Status

5. **Images** (lines 44-50):
   ```html
   <img src="images/project1-image1.jpg" alt="Project image 1">
   <img src="images/project1-image2.jpg" alt="Project image 2">
   ```
   - Replace with paths to your actual images
   - Add or remove `<img>` tags as needed for your project
   - Organize images in subfolders: `images/barn-renovation/photo1.jpg`

## Step 3: Add Images

1. Create a subfolder in your `images/` directory for the project
   Example: `images/barn-renovation/`

2. Add your project images to this folder

3. Update the image paths in your HTML:
   ```html
   <img src="images/barn-renovation/exterior-view.jpg" alt="Exterior view">
   <img src="images/barn-renovation/interior-detail.jpg" alt="Interior detail">
   ```

## Step 4: Link from Work Page

Open `work.html` and update the project list:

```html
<li><a href="barn-renovation.html" data-image="images/barn-renovation/preview.jpg">Barn Renovation</a></li>
```

The `data-image` should point to a preview/hero image for the hover effect on the work page.

## How the Scrolling Works

The right column of images:
- Stays fixed in position as you scroll the page
- Scrolls independently when you hover over it and use your mouse wheel
- All images are stacked vertically
- Images maintain 70% opacity (matching other images on the site)

## Tips

- Keep image file sizes reasonable (under 500KB each) for fast loading
- Use consistent image widths for a clean look
- Portrait and landscape images both work fine
- Add as many images as you want - the gallery will scroll
- Images appear in the order you list them in the HTML

## Quick Workflow

For each new project:
1. Copy `project-template.html` → rename to `project-name.html`
2. Edit text content (title, description, details)
3. Add images to `images/project-name/` folder
4. Update image paths in the HTML
5. Add project to `work.html` with preview image
6. Push to GitHub: `git add . && git commit -m "Added new project" && git push`
