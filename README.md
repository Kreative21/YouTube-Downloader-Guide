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
# 🎧 YouTube Playlist Downloader - By Ronak 🎧
# ============================================

# Cleanup previous files from earlier runs
!rm -f /content/*.mp3
!rm -f /content/playlist.zip

# Install dependencies
!pip install yt-dlp
!apt install ffmpeg -y

# Download and convert playlist
import yt_dlp

PLAYLIST_URL = "PASTE URL HERE"  # 👈 Replace with your Playlist/Video URL

ydl_opts = {
    'format': 'bestaudio/best',
    'postprocessors': [{
        'key': 'FFmpegExtractAudio',
        'preferredcodec': 'mp3',
        'preferredquality': '192',  # Change to 320 for higher quality
    }],
    'outtmpl': '/content/%(title)s.%(ext)s',
    'ignoreerrors': True,
}

with yt_dlp.YoutubeDL(ydl_opts) as ydl:
    ydl.download([PLAYLIST_URL])

# Create ZIP archive
!zip -r playlist.zip *.mp3

# Success message
print("\n\033[92m" + "🎉" * 10 + " SUCCESS! " + "🎉" * 10)
print("""\033[96m
███████╗██╗   ██╗ ██████╗  ██████╗ ███████╗███████╗███████╗
██╔════╝██║   ██║██╔════╝██╔════╝██╔════╝██╔════╝██╔════╝
███████╗██║   ██║██║     ██║     ███████╗███████╗███████╗
╚════██╗██║   ██║██║     ██║     ██╔════╝╚════██╗╚════██╗
███████║╚██████╔╝╚██████╗╚██████╗████████╗███████║███████║
╚══════╝ ╚═════╝  ╚═════╝ ╚═════╝ ╚══════╝╚══════╝╚══════╝
\033[0m""")
print("\033[95m✅ ZIP file created successfully! ✅")
print("\033[94m📦 playlist.zip is ready for download!")
print("\033[93m➡️ Find it in the 📁 Files icon on the left!")
print("\033[92m🌟 You can download either (Clicking the 3 DOTS):")
print("   - Individual MP3 files")
print("   - The complete playlist.zip")
print("\033[95m" + "✨" * 35 + "\033[0m\n")
```

## 🔧 **How to run:**

- Paste the above code into the cell

- Replace the **`PASTE URL HERE`** in the code with actual Link of your playlist/video

- Click the ▶️ **button** on the left of the cell

- Let the code RUN

---


# ⏳ It takes time! Have patience. Longer your playlist, longer the time it will take

### 4️⃣ Download Your Music
- Look at the left sidebar → Click the **📁 Files icon**

- Find **`playlist.zip`** → **`Click 3 dots`** → **`Download`**


# 💡 Pro Tips
- If a cell gets stuck: **`Click Runtime`** → **`Restart runtime`**

- To pause: Click **`Runtime`** → **`Interrupt execution`**

- Need more quality? Change **`'preferredquality': '320'`**
