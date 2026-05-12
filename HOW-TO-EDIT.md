# 🌷 HOW TO EDIT YOUR ANNIVERSARY WEBSITE
## Complete Guide — Read This First!

---

## 📁 FOLDER STRUCTURE (set this up first)

Create this folder layout on your computer:

```
our-story/
├── index.html          ← the main file (already done!)
├── photos/
│   ├── month1/
│   │   ├── cover.jpg   ← the BIG cover photo for Month 1
│   │   ├── 1.jpg
│   │   ├── 2.jpg
│   │   ├── 3.jpg       (add as many as you want)
│   ├── month2/
│   │   ├── cover.jpg
│   │   ├── 1.jpg … etc
│   ├── month3/
│   ├── month4/
│   ├── month5/
│   └── month6/
└── media/
    ├── month1/
    │   ├── vid1.mp4     ← her random videos
    │   ├── vid2.mp4
    ├── month2/
    │   ├── vid1.mp4
    … etc
```

---

## 🖼️ ADDING YOUR PHOTOS

### Step 1 — Prepare your photos
- Rename photos simply: `1.jpg`, `2.jpg`, `3.jpg` etc.
- **iPhone photos**: AirDrop to your Mac, they'll be HEIC — convert them:
  - Open in Preview → File → Export → save as JPEG
  - Or use [cloudconvert.com](https://cloudconvert.com) (free, online)
- **Keep photos under 2MB each** for fast loading

### Step 2 — Replace placeholder images in `index.html`

Open `index.html` in any text editor (Notepad on Windows, TextEdit on Mac, or VS Code).

Search for lines like:
```
src="https://images.unsplash.com/photo-..."
```

Replace with your photo path:
```
src="photos/month1/1.jpg"
```

**Every photo has a comment above it like:**
```html
<!-- 🖼️ Replace src with your photo path -->
```

---

## 🎬 ADDING YOUR VIDEOS

### Step 1 — Convert your videos (IMPORTANT for iPhone)
iPhone videos are `.MOV` format — browsers need `.MP4`.

**Free conversion:**
- **HandBrake** (desktop app, free): open MOV → preset "Web Optimized" → save as MP4
- **cloudconvert.com** (online): upload MOV → convert to MP4 → download
- **iMovie** (Mac): File → Share → File → choose 1080p → saves as MP4

### Step 2 — Name and place your videos
- Put them in `/media/month1/vid1.mp4`, `/media/month2/vid1.mp4` etc.
- Keep under **50MB per video** for smooth GitHub loading

### Step 3 — Add them in `index.html`

In the MONTHS data section, find each month's `videos:` array:

```javascript
videos: [
  {
    src: "",          // ← REPLACE with: "media/month1/vid1.mp4"
    poster: "...",    // ← a thumbnail image shown before video plays
    caption: "You being silly 😂"  // ← your caption
  },
]
```

Change to:
```javascript
videos: [
  {
    src: "media/month1/vid1.mp4",
    poster: "photos/month1/1.jpg",   // any photo as thumbnail
    caption: "You being silly in the kitchen 😂"
  },
]
```

**To add MORE videos to a month**, just add more objects:
```javascript
videos: [
  { src: "media/month1/vid1.mp4", poster: "photos/month1/1.jpg", caption: "Caption 1" },
  { src: "media/month1/vid2.mp4", poster: "photos/month1/2.jpg", caption: "Caption 2" },
  { src: "media/month1/vid3.mp4", poster: "photos/month1/3.jpg", caption: "Caption 3" },
]
```

---

## ✏️ EDITING THE TEXT

### Change your names / dates
Search for these in `index.html` and replace:

| Find | Replace with |
|------|-------------|
| `Our Story` | Your couple name |
| `Since Nov 2024` | Your actual start date |
| `Emma & Liam` | Your names |
| `November`, `December` etc | Your actual month names |

### Change month themes
Each month has a `theme:` — this is the poetic name shown on the card:
```javascript
theme: "The Beginning",
```
Change it to whatever feels right for that month.

### Change quotes
Each month has a `quote:` — shown as the big featured quote:
```javascript
quote: "Some people arrive and make such a beautiful impact...",
```
Replace with:
- A quote she loves
- Something you said to each other
- A lyric from your song
- Something about tulips 🌷

### Change descriptions
Each month has a `desc:` — 2-3 sentences about that month:
```javascript
desc: "The month everything started...",
```

### Change photo captions
Each photo has `caption:` (shown on hover) and `quote:` (shown in fullscreen):
```javascript
{ src: "photos/month1/1.jpg", caption: "Day one 🌷", quote: "I knew from that first moment." }
```

---

## 🌷 ADDING MORE PHOTOS PER MONTH

To add more photos, add more objects to the `photos:` array:

```javascript
photos: [
  { src: "photos/month1/1.jpg", caption: "Caption", quote: "A quote" },
  { src: "photos/month1/2.jpg", caption: "Caption", quote: "A quote" },
  { src: "photos/month1/3.jpg", caption: "Caption", quote: "A quote" },
  // add as many as you want! ↓
  { src: "photos/month1/10.jpg", caption: "New photo", quote: "New quote" },
],
```

---

## 🚀 HOSTING ON GITHUB PAGES

### Step 1 — Create a GitHub account
Go to [github.com](https://github.com) and sign up (free).

### Step 2 — Create a PRIVATE repository
- Click the **+** icon → New repository
- Name it: `our-story` (or anything you want)
- Set to **Private** ← IMPORTANT for photo protection
- Click Create

### Step 3 — Upload your files
- Click **uploading an existing file**
- Drag in your entire `our-story/` folder contents
- Or use GitHub Desktop app (easier for beginners)

### Step 4 — Enable GitHub Pages
- Go to repository **Settings**
- Scroll to **Pages** (left sidebar)
- Source: **Deploy from a branch**
- Branch: **main** / **(root)**
- Click **Save**
- Wait 2-3 minutes — your URL appears at the top!

### Step 5 — Share the link 🌷
Your site will be at:
```
https://yourusername.github.io/our-story
```

---

## 🔒 PHOTO PROTECTION (already built in)

The site already has:
- ✅ Right-click disabled
- ✅ Image dragging disabled
- ✅ Keyboard shortcut saving blocked (Ctrl+S, Ctrl+U etc)
- ✅ CSS overlay on all photos
- ✅ Private GitHub repo = originals never publicly listed

**Extra protection tip:** Before uploading, watermark photos with a tiny transparent
watermark in the corner (use Canva or Snapseed on your phone).

---

## 🐛 TROUBLESHOOTING

**Photos not showing?**
- Check the path is exactly right: `photos/month1/1.jpg` (lowercase, no spaces)
- Make sure the file actually exists in that folder

**Videos not playing?**
- Make sure they're `.mp4` format (not `.mov`)
- Check the path in the `src:` field
- GitHub Pages has a 100MB file size limit — keep videos under 50MB

**Site not updating after edit?**
- GitHub Pages can take 2-5 minutes to refresh
- Try Ctrl+Shift+R to hard-reload your browser

**Test locally first:**
- Open `index.html` directly in Chrome/Safari before uploading
- Note: videos may not play locally due to browser security — that's normal, they'll work on GitHub

---

## 💡 TIPS

- **Add `?guide=1`** to the URL (e.g. `index.html?guide=1`) to see edit markers
- **Portrait photos** look great in the masonry grid — mix portrait and landscape
- **Video length**: 5-30 second clips work best as "memories" — the shorter the sweeter
- **Test on mobile** — the site is fully responsive
- Keep the site link as a surprise, don't spoil it 🤫

---

*Made with 🌷 — enjoy every second of building this for her.*
