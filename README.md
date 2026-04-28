# TAIL-Safe Project Page

Static project page for **TAIL-Safe: Task-Agnostic Safety Monitoring for Imitation Learning Policies** (RSS 2026).

## Local preview

Just open `index.html` in a browser, or serve the folder:

```bash
python -m http.server 8000
# then visit http://localhost:8000
```

## Deploy to GitHub Pages

```bash
cd project_page
git init
git add .
git commit -m "Initial project page"
git branch -M main
git remote add origin https://github.com/riadahmedunh/tail_safe.git
git push -u origin main
```

In the repo settings -> **Pages**, set:
- Source: `Deploy from a branch`
- Branch: `main` / `(root)`

The page will be live at `https://riadahmedunh.github.io/tail_safe/`.

## Main overview video (.mkv -> .mp4)

The supplementary video `TAIL_Safe.mkv` is not natively playable in browsers.
Convert it to MP4 once with ffmpeg and place it at `static/videos/main_overview.mp4`:

```bash
ffmpeg -i "TAIL_Safe.mkv" -c:v libx264 -preset slow -crf 23 -c:a aac -movflags +faststart static/videos/main_overview.mp4
```

(The setup script copies the original `.mkv` next to it as a backup.)

## Real-robot videos (.MOV -> .mp4)

The iPhone `.MOV` files play in Safari but not all browsers. To re-encode:

```bash
ffmpeg -i real_demo_1.mov -c:v libx264 -c:a aac -movflags +faststart real_demo_1.mp4
```

## File map

```
project_page/
  index.html
  static/
    css/index.css
    pdfs/paper741.pdf
    images/   (figures: PNG/SVG)
    videos/   (rollouts, recoveries, failures, real-world)
```

## Code

The Code button on the page is intentionally disabled and labeled "coming soon".
When the repo is public, edit `index.html` and replace the placeholder href in
the GitHub button with the real URL.
