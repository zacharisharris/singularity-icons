# Singularity Icons

High-quality subscription icons for the Singularity iOS app, hosted on GitHub Pages.

## 📁 Structure

```
singularity-icons/
├── icons/              # All icon PNGs (1024×1024)
│   ├── anthropic.png
│   ├── openai.png
│   └── ...
├── index.html          # Icon gallery page
└── README.md           # This file
```

## 🚀 Setup Instructions

### 1. Create GitHub Repository

1. Go to [github.com/new](https://github.com/new)
2. Repository name: `singularity-icons`
3. Make it **Public**
4. Check "Add a README file"
5. Click "Create repository"

### 2. Upload Icons

**Option A: Web Upload (Easy)**
1. Go to your new repo on GitHub
2. Click "Add file" → "Upload files"
3. Drag the entire `icons/` folder
4. Also upload `index.html`
5. Commit changes

**Option B: Git Command Line**
```bash
git clone https://github.com/YOUR_USERNAME/singularity-icons.git
cd singularity-icons
# Copy icons/ folder and index.html here
git add .
git commit -m "Add initial icons"
git push origin main
```

### 3. Enable GitHub Pages

1. Go to repo Settings → Pages (left sidebar)
2. Source: Deploy from a branch
3. Branch: `main` / `root`
4. Click Save
5. Wait 2-3 minutes for site to deploy
6. Your URL will be: `https://YOUR_USERNAME.github.io/singularity-icons/`

## 🔗 Icon URLs

Once deployed, icons are accessible at:

```
https://YOUR_USERNAME.github.io/singularity-icons/icons/ICON_NAME.png
```

**Examples:**
- `https://zacharisharris.github.io/singularity-icons/icons/anthropic.png`
- `https://zacharisharris.github.io/singularity-icons/icons/openai.png`
- `https://zacharisharris.github.io/singularity-icons/icons/midjourney.png`

## 📱 App Integration

### Update UIImageView+Ext.swift

Replace the Firebase URL with GitHub Pages URL:

```swift
// OLD (Firebase):
let url = URL(string: "https://firebasestorage.googleapis.com/v0/b/singularity-crashlytics.appspot.com/o/\(preset.imageName!)?alt=media&token=d421488d-890c-49dd-869d-37d1675fa767")

// NEW (GitHub Pages):
let url = URL(string: "https://YOUR_USERNAME.github.io/singularity-icons/icons/\(preset.imageName!)")
```

### Make it configurable:

```swift
enum IconSource {
    static let baseURL = "https://YOUR_USERNAME.github.io/singularity-icons/icons/"
    
    static func url(for imageName: String) -> URL? {
        return URL(string: baseURL + imageName)
    }
}

// Usage:
let url = IconSource.url(for: preset.imageName!)
```

## ➕ Adding New Icons

1. Convert SVG to PNG (1024×1024)
2. Upload to `icons/` folder
3. Update `index.html` to include new icon
4. Commit & push
5. Changes are live in 1-2 minutes

## 📊 Current Icons

Total: 10 icons

| Icon | Size | Company |
|------|------|---------|
| anthropic.png | 104KB | Anthropic |
| openai.png | 1.3MB | OpenAI |
| midjourney.png | 874KB | Midjourney |
| perplexity.png | 142KB | Perplexity |
| elevenlabs.png | 4.7KB | ElevenLabs |
| runway.png | 36KB | Runway |
| huggingface.png | 982KB | Hugging Face |
| characterai.png | 716KB | Character.AI |
| jasper.png | 657KB | Jasper |
| copyai.png | 270KB | Copy.ai |

**Total Size:** ~4.9MB

## 💰 Cost

**FREE**
- GitHub Pages: Free for public repos
- Bandwidth: Unlimited
- Storage: Unlimited (within GitHub's fair use)

## 🔄 Backup Strategy

1. **Primary:** Local SVGs in app bundle (Assets.xcassets)
2. **Secondary:** GitHub Pages (this repo)
3. **Fallback:** Firebase Storage (if still available)

## 📝 License

Icons are property of their respective companies. This repo is for app integration purposes only.