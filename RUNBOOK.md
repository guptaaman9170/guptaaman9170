# Runbook — GitHub Profile Setup & Automation Guide for Aman Kumar Gupta

This repository powers the dynamic GitHub Profile README for **Aman Kumar Gupta** ([@guptaaman9170](https://github.com/guptaaman9170)).

## 📂 Project Structure
```
profile_github/
  ├── README.md                               # Dynamic GitHub Profile README
  ├── RUNBOOK.md                              # This setup and automation guide
  ├── info-card.svg                           # Animated neofetch terminal info card
  ├── contrib-heatmap.svg                     # Daily contribution heatmap SVG
  ├── aman-ascii.svg                          # Terminal ASCII portrait SVG
  ├── aman-photo.png                          # High-res profile portrait
  ├── requirements-local.txt                  # Image processing dependencies (Pillow, rembg, opencv)
  ├── .github/
  │   └── workflows/
  │       └── update-profile-art.yml          # Daily GitHub Action to refresh heatmap
  ├── data/
  │   └── contributions.json                  # Parsed GitHub contribution records for guptaaman9170
  └── scripts/
      ├── fetch_contributions.py              # Scrapes GitHub public contributions
      ├── render_heatmap_svg.py               # Generates contribution SVG heatmap
      ├── make_info_card.py                   # Generates animated terminal info card SVG
      ├── make_ascii_svg.py                   # Generates ASCII art SVG from portrait
      ├── prep_photo.py                       # Prepares photo with background removal
      └── requirements.txt                    # Scraper dependencies (requests, beautifulsoup4)
```

---

## 🛠️ Step-by-Step Setup & Maintenance

### 1. Install Dependencies
```bash
pip install -r scripts/requirements.txt
```

### 2. Regenerate SVG Assets Locally
```bash
# Render terminal neofetch info card
python scripts/make_info_card.py

# Fetch guptaaman9170's contributions & render heatmap
python scripts/fetch_contributions.py
python scripts/render_heatmap_svg.py
```

### 3. (Optional) Generate Your Custom ASCII Portrait
When you have a front-facing portrait photo:
1. Place your photo in the root directory as `source-photo.jpg`.
2. Install local image dependencies:
   ```bash
   pip install -r requirements-local.txt
   ```
3. Run the image preparation and ASCII SVG generator:
   ```bash
   python scripts/prep_photo.py source-photo.jpg source-prepped.png
   python scripts/make_ascii_svg.py source-prepped.png aman-ascii.svg
   ```

---

## 🚀 Connecting Directly to Your GitHub Profile (`guptaaman9170/guptaaman9170`)

> [!NOTE]
> GitHub displays the README on your main profile page `https://github.com/guptaaman9170` when it is pushed to the special repository named **`guptaaman9170`** (matching your exact GitHub username).

To link this profile README to your public profile page:
1. Create a public repository named **`guptaaman9170`** on GitHub (if not already created).
2. Push this repo to your repository:
```bash
git add .
git commit -m "Update profile README, projects, skills, and assets for Aman Kumar Gupta"
git branch -M main
git remote set-url origin https://github.com/guptaaman9170/guptaaman9170.git
git push -u origin main
```

---

## 🔄 Automated Daily Updates via GitHub Actions

1. Go to your repository on GitHub: **Settings → Actions → General → Workflow permissions**.
2. Select **"Read and write permissions"** and click **Save**.
3. The `.github/workflows/update-profile-art.yml` workflow will automatically run every day at 03:17 UTC to refresh your contribution heatmap and commit any changes automatically!
