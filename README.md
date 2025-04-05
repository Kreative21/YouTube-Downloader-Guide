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

### 3️⃣ **Install Required Tools**
- **Copy this code:**
```python
!pip install yt-dlp
!apt install ffmpeg -y
```
🔧 **How to run:**

- Paste the code into the cell

- Click the ▶️ button on the left of the cell

- Let it Download the needed resources

---
### 4️⃣ Add New Code Cell
- Click **`+ Code`** in the top toolbar

- A new empty cell will appear below

---

### 5️⃣ Convert Playlist to MP3
- **Copy this code:**
```
import yt_dlp

PLAYLIST_URL = "PASTE_YOUR_PLAYLIST_URL_HERE"  # 👈 Replace this link

ydl_opts = {
    'format': 'bestaudio/best',
    'postprocessors': [{
        'key': 'FFmpegExtractAudio',
        'preferredcodec': 'mp3',
        'preferredquality': '192',
    }],
    'outtmpl': '/content/%(title)s.%(ext)s',
    'ignoreerrors': True,
}

with yt_dlp.YoutubeDL(ydl_opts) as ydl:
    ydl.download([PLAYLIST_URL])
```
🔧 **How to run:**

- Replace **`PASTE_YOUR_PLAYLIST_URL_HERE`** with your actual playlist link

- Click ▶️ to run the code

---

### ⏳ Conversion takes time! Have patience.

---

### 6️⃣ Create ZIP File
- Click **`+ Code`** to make another new cell

- Paste this code:
```
!zip -r playlist.zip *.mp3
```
- Run with ▶️ button

---

### 7️⃣ Download Your Music
- Look at the left sidebar → Click the **📁 Files icon**

- Find **`playlist.zip`** → **`Click 3 dots`** → **`Download`**

---

# 💡 Pro Tips
- If a cell gets stuck: **`Click Runtime`** → **`Restart runtime`**

- To pause: Click **`Runtime`** → **`Interrupt execution`**

- Need more quality? Change **`'preferredquality': '320'`**
