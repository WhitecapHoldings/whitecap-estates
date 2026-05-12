# Whitecap Estates Website

Built with Astro. Hosted on Netlify. Domain on Namecheap.

---

## Setup Instructions

### 1. Push to GitHub
1. Create a new repository on GitHub (e.g. `whitecap-estates`)
2. In your terminal, navigate to this folder and run:
   ```
   git init
   git add .
   git commit -m "Initial site build"
   git branch -M main
   git remote add origin https://github.com/YOUR_USERNAME/whitecap-estates.git
   git push -u origin main
   ```

### 2. Connect to Netlify
1. Go to netlify.com and log in
2. Click "Add new site" > "Import an existing project"
3. Choose GitHub and select your repository
4. Build settings (should auto-detect):
   - Build command: `npm run build`
   - Publish directory: `dist`
5. Click "Deploy site"

### 3. Connect Your Namecheap Domain
1. In Netlify: Site settings > Domain management > Add custom domain
2. Type `whitecapestates.com` and confirm
3. Netlify will give you nameserver addresses (e.g. dns1.p01.nsone.net)
4. In Namecheap: Domain List > Manage > Nameservers > Custom DNS
5. Paste in the Netlify nameservers and save
6. Wait 24-48 hours for DNS to propagate

### 4. Add Calendly (when ready)
In `src/pages/contact.astro`, find the comment that says REPLACE THE PLACEHOLDER ABOVE WITH and swap in:
```html
<div class="calendly-inline-widget" data-url="https://calendly.com/YOUR-LINK" style="min-width:320px;height:700px;"></div>
<script type="text/javascript" src="https://assets.calendly.com/assets/external/widget.js" async></script>
```

### 5. Add Google Voice Number (when ready)
Do a find-and-replace across all files:
- Replace `(469) 358-5646` and `(945) 349-9179` with your single Google Voice number
- Update the tel: links accordingly

### 6. Add Headshots (when ready)
- Add photos to `/public/` folder (e.g. `kyle.jpg`, `cristian.jpg`)
- In `src/pages/about.astro`, replace the `.team-photo-placeholder` divs with `<img>` tags

---

## Adding Blog Posts

Create new `.astro` files in `src/pages/blog/` following the same structure as existing pages.

Update the `posts` array in `src/pages/blog/index.astro` to include your new post.

---

## Running Locally

```
npm install
npm run dev
```

Site will be live at http://localhost:4321
