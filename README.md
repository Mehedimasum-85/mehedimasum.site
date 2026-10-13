# Md. Hasan Abdullah Masum - Portfolio Website

A plain HTML, CSS and JavaScript website. No Node.js, no terminal, no installs.

## Open it on your PC
1. Unzip the folder.
2. Double-click `index.html`. It opens in your browser.

## Folder layout
- `index.html`, `portfolio.html`, `about.html`, `contact.html` - the four pages
- `css/style.css` - all styles (colors and sizes are at the top, under `:root`)
- `js/main.js` - mobile menu and scroll animations
- `js/portfolio-data.js` - the list of portfolio projects (edit this to add or change projects)
- `js/portfolio.js` - filters, animations and the slider preview on the Portfolio page
- `fonts/` - fonts used by the site (no internet needed)
- `images/profile/` - your portrait; `images/portfolio/` - project images

## About page
`about.html` has the hero, My Creative Journey, Career & Experience timeline, skills, design approach and closing CTA. Edit the text directly in the file. Its styles are at the bottom of `css/style.css` under `About page`. 
## Contact page (IMPORTANT: form delivery is NOT configured yet)
`contact.html` has the form (Full Name, Email, Subject, Project Type, Message), a LinkedIn icon link, project inquiry guidance and a closing CTA. Its code is in `js/contact.js`.

**Right now the form cannot deliver messages.** The site is static and has no backend or email service. It validates the fields, then shows a clear notice that the message was NOT sent and points visitors to your email in the footer or LinkedIn. It never pretends to send, and it stores nothing in the browser.

To make it really deliver messages:
1. Create a free form endpoint with a service such as Formspree or Web3Forms (or your own backend) and copy its URL.
2. Open `js/contact.js` and paste the URL into `FORM_ENDPOINT` at the top (it is empty now).
3. Test one message. After that, the form shows success or error messages based on the real response and blocks double submits while sending.

The endpoint must accept a JSON POST with the fields `name`, `email`, `subject`, `project_type`, `message`. If your service wants a different format, tell me and I will adjust it.

## Homepage "Selected Work" and category order
The Homepage shows 5 cards in this order: Social Media, Logo & Brand Identity, Thumbnail Design, Print Material Design, Website Design Presentation. Each card links to its category on the Portfolio page (`portfolio.html#social`, `#brand`, `#thumbnail`, `#print`, `#website`). The Portfolio page uses the same order, set by the list at the top of `js/portfolio-data.js`. Advertising & Campaign and Video Editing & Motion Graphics still exist after these five on the Portfolio page; delete their projects from the data file if you do not want them.

## Replace images
- Portrait: replace `images/profile/masum-portrait.jpg` (keep the name).
- Projects: put your image in `images/portfolio/graphic-design/` (or `video-editing/`), then in `index.html` change the image `src`, the `alt` text, and delete that card's `<span class="project__badge">Placeholder</span>`.

## Edit text, experience, social links
Open the `.html` file in Notepad or VS Code and edit the text. Social links: find the `SOCIAL LINKS` comment in the footer of each page, add your real URLs and remove the comment markers. The footer is repeated on every page, so update all four.

## Put it online later
Upload everything inside this folder (the four `.html` files and the `css`, `js`, `fonts`, `images` folders) to your host's public folder (usually `public_html`), keeping the folder structure. `index.html` must sit at the top level. Works on any host, including cPanel, Netlify, Vercel, GitHub Pages and Cloudflare Pages.

## Portfolio page: add your real projects
The Portfolio page is built as: **Category -> Project cards** (3 per row on desktop). No brand headings are shown; the card shows only its `title`, so put the brand name there.

1. Make your images (see sizes below) and put them in `images/portfolio/<category>/<brand>/`, for example `images/portfolio/logo-branding/nova-coffee/`.
2. Open `js/portfolio-data.js` in Notepad or VS Code. Copy one `{ ... }` project block, paste it, and change:
   - `title` - the brand name shown on the card
   - `category` - `brand`, `social`, `print`, `advertising` or `video`
   - `brand` - optional, for your own reference only (not shown)
   - `cover` - the banner shown on the page
   - `images` - 1 to 3 pictures for the preview slider
   - `alt` - short description for screen readers
   - `placeholder` - set to `false` for real work (removes the "Placeholder" badge)
3. To remove a project, delete its block. Filters, counts and the preview update automatically.
4. A category with no projects is hidden automatically. To rename a category, edit its `label` at the top of the data file.

### Image sizes
- **Cover (banner): 4000 x 3000 px (4:3).** Every card shows it at 4:3. If you leave `cover` out, the first image in `images` is used and cropped to 4:3.
- **Slider images: any size.** Portrait, square or wide, they are shown whole and never cropped. Use 1, 2 or 3 images per project. A project with 1 image shows no slider controls. More than 3 are ignored.
- Tip: a 4000 x 3000 file can be heavy. Export JPG or WebP at good quality and try to keep each file under about 1 MB so the page loads fast.

### Linking to one category
`portfolio.html#social`, `#brand`, `#print`, `#advertising` and `#video` open the page with that category already selected.

### Preview slider
Click a card to open it. Use the arrows, the dots, the left/right keys or swipe to move between images. "Previous project / Next project" moves to the next card.
