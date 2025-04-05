# YouTube Video/Playlist Download Guide - By Ronak 🎧

[![Open in Google Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com)

*Download YouTube playlists to MP3 files directly in your browser - No technical skills needed!*

---

## ✨ Features
- ⚡ Easy conversion
- 🛡️ Automatic error skipping
- 🎧 Adjustable audio quality (128kbps-320kbps)
- 📦 ZIP file packaging
- ☁️ 100% cloud-based & No viruses

---

## 🚀 Step-by-Step Guide

### 1️⃣ **Open Google Colab**
- Go to [Google Colab](https://colab.research.google.com)

- Open in **Desktop Mode** for better view if you are in mobile

- Click **`File`** in the top menu → Select **`New notebook`**

---

### 2️⃣ **Create Your First Code Cell**
- In your new notebook, you'll see a blank box with "Type code here" (this is a code cell)

- Click inside the box to activate it

---

### 3️⃣ **Code**
- **Copy paste this code in the cell:**
```
# ============================================
# 🎧 YouTube Playlist Downloader - By Ronak
# ============================================

# 🔧 USER SETTINGS (Edit these if needed!)
PLAYLIST_URL = "PASTE_YOUR_PLAYLIST_URL_HERE"  # 🔗 PASTE YOUR PLAYLIST URL HERE
AUDIO_QUALITY = '192'  # 🎚️ Options: 128, 192, 256, 320 (highest)
OUTPUT_FORMAT = 'mp3'  # 🎧 Options: mp3, wav, ogg

# ========================
# 🚀 AUTOMATED PROCESS
# ========================
# Install required packages
!pip install -q yt-dlp
!apt install -qq ffmpeg -y

# Clean previous files (if any)
!rm -f *.mp3 *.zip

# Download and convert to audio
import yt_dlp

ydl_opts = {
    'format': 'bestaudio/best',
    'postprocessors': [{
        'key': 'FFmpegExtractAudio',
        'preferredcodec': OUTPUT_FORMAT,
        'preferredquality': AUDIO_QUALITY,
    }],
    'outtmpl': f'/content/%(title)s.{OUTPUT_FORMAT}',
    'ignoreerrors': True,
    'quiet': False,
}

print("⏬ Downloading playlist... (This may take a while)")
with yt_dlp.YoutubeDL(ydl_opts) as ydl:
    ydl.download([PLAYLIST_URL])

# Create ZIP archive
print("\n📦 Packaging files...")
!zip -q -r playlist.zip *.mp3

# Final instructions
print(f"""
✅ Done! Follow these steps to get your files:
1. Click the 📁 folder icon in the left sidebar
2. Click 3 dots of 'playlist.zip'
3. Select 'Download'

# Optional: Auto-clear large files after download
# !rm -f *.mp3
```

## 🔧 **How to run:**

- Paste the code into the cell

- Click the ▶️ button on the left of the cell

- Let the code RUN

---


# ⏳ It takes time! Have patience. Longer your playlist, longer the time it will take


# 💡 Pro Tips
- If a cell gets stuck: **`Click Runtime`** → **`Restart runtime`**

- To pause: Click **`Runtime`** → **`Interrupt execution`**

- Need more quality? Change **`'preferredquality': '320'`**
