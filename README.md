# Raj's Art Portfolio 🎨

A modern, responsive, and dark-themed portfolio website designed to showcase pencil, charcoal, and digital artworks. Features a masonry gallery grid, a full-screen image lightbox, and category filtering.

## 📁 Project Structure

- `index.html` — The main structure and content of the website.
- `style.css` — All the styling, layout, animations, and dark theme colors.
- `script.js` — The logic for the custom cursor, gallery filtering, and the lightbox image viewer.
- `SketchUp_/` — The folder containing all your original artwork images.
- `server.ps1` — A simple local server script to test the website on your computer.

---

## 🖼️ How to Manage Your Artworks

All artworks are displayed in the **Gallery Section** of `index.html`. 

### 1. Adding a New Artwork

To add a new sketch or drawing to the website, follow these two steps:

**Step A: Add the image file**
Move your new image file (e.g., `new-drawing.jpg`) into the `SketchUp_/` folder.

**Step B: Add the HTML code**
Open `index.html`, scroll down to the gallery section (look for `<div class="gallery-grid" id="gallery-grid">`), and add the following block of code where you want the image to appear:

```html
<div class="gallery-item" data-category="portrait" data-title="Your Artwork Title" data-medium="Pencil on Paper">
    <img src="SketchUp_/new-drawing.jpg" alt="Description of the drawing" loading="lazy">
    <div class="gallery-overlay">
        <span class="gallery-category">Portrait</span>
        <h3>Your Artwork Title</h3>
        <p>Pencil on Paper</p>
    </div>
</div>
```

**Important Attributes to Update:**
- `data-category=""` — This is required for the filters to work. Choose exactly one of these: `portrait`, `landscape`, `mythology`, `anime`, `wildlife`, or `study`.
- `data-title=""` and `data-medium=""` — These dictate what text shows up when the image is opened in the full-screen lightbox.
- `src=""` — Make sure this perfectly matches the filename of your image inside the folder.
- Inside `<div class="gallery-overlay">` — Update the text here so it displays correctly when a user hovers over the image in the grid.

### 2. Removing an Artwork
To remove an artwork, simply open `index.html`, find the `<div class="gallery-item"> ... </div>` block for that specific drawing, and delete that entire block of code. You can also delete the image file from the `SketchUp_/` folder to save space.

### 3. Updating Categories / Filters
If you want to add a new filter category (e.g., "Digital"):
1. Find the `<div class="filter-bar">` section in `index.html`.
2. Add a new button: `<button class="filter-btn" data-filter="digital">Digital Art</button>`
3. When adding artworks for this category, make sure you set `data-category="digital"`.

---

## 📝 Updating Website Text and Info

- **About Section:** Search for `<section id="about" ...>` in `index.html` to update your bio and the stats (e.g., "24+ Artworks").
- **Featured Images:** In the About section, there are 3 featured images displayed in a stack. You can change them by updating the image `src` inside the `<div class="about-image-stack">`.
- **Contact Form:** The form is powered by Web3Forms. If you ever need to change the email address it sends to, you need to generate a new Access Key on the Web3Forms website and replace the value in `<input type="hidden" name="access_key" value="...">`.

---

## 💻 Testing the Website Locally

Browsers restrict some features (like the lightbox) if you just double-click the `index.html` file. To view the site properly on your computer:

1. Right-click on `server.ps1` and select **Run with PowerShell**.
2. Keep the blue window open.
3. Open your browser and go to: `http://localhost:8080`
4. When you are done testing, you can close the PowerShell window.

---

## 🚀 Publishing Updates to the Live Site

Because this site is hosted on GitHub Pages, whenever you add new art or change text, you need to push those changes to GitHub.

Open your terminal or command prompt in the `art_website` folder and run these three commands in order:

```bash
git add .
git commit -m "Added new artwork"
git push origin main
```

*(Note: If you renamed your repository to `rajbhole717-code.github.io` as discussed, your local git might need the remote URL updated once. If it pushes successfully, you're good!)*

Wait about 1–2 minutes, refresh your live website, and your new art will be there!
