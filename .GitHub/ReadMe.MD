
<h1 align="center">🎵˹Vᴀɴʏᴀ Mᴜsɪᴄ˼ 🎵</h1>

<p align="center">
  <b>Ultimate Telegram Music Bot with Superior Audio Quality & Advanced Music Features</b>
</p>

<h2 align="center">🚀 Deploy to Render (Free Hosting)</h2>

<p align="center">
  <a href="https://render.com/deploy?repo=https://github.com/NoxxOP/ShrutixMusic">
    <img src="https://render.com/images/deploy-to-render-button.svg" alt="Deploy to Render">
  </a>
</p>

<h2 align="center">☁️ Deploy to Railway</h2>

<p align="center">
  <a href="https://railway.app/template/ShrutixMusic?referralCode=NoxxOP">
    <img src="https://railway.app/button.svg" alt="Deploy on Railway">
  </a>
</p>

## ✨ Music Features

### 🎵 **High-Quality Audio Streaming**
- **Crystal Clear Sound**: 320kbps premium audio quality
- **Zero Lag Streaming**: Optimized for smooth playback
- **Multiple Audio Sources**: YouTube, Spotify, SoundCloud, Apple Music, Deezer
- **Live Stream Support**: Radio stations and live music streams
- **Local File Support**: Upload and play your own music files

### 🎛️ **Advanced Music Controls**
- **Smart Queue Management**: Add, remove, and reorder songs
- **Playlist Creation**: Save your favorite tracks
- **Shuffle & Repeat**: Various playback modes
- **Volume Control**: Precise volume adjustment (1-200%)
- **Seek Function**: Jump to any part of the song
- **Speed Control**: Playback speed from 0.5x to 2x

### 🎧 **Audio Enhancement**
- **Audio Filters**: Bass boost, treble, echo, reverb effects
- **Equalizer**: Custom sound profiles
- **Noise Reduction**: Clear audio in noisy environments
- **Auto-Quality**: Adapts to network conditions
- **Crossfade**: Smooth transitions between songs

### 🎪 **Interactive Features**
- **Lyrics Display**: Real-time synchronized lyrics
- **Song Recognition**: Identify playing songs
- **Music Search**: Advanced search with filters
- **Trending Music**: Discover popular tracks
- **Genre-Based Playlists**: Curated music collections

## 🎯 Bot Commands

Bot mein sabhi commands ka detailed information `/help` command se mil jayega. Bot ke andar hi comprehensive help section available hai jo sabhi features aur commands explain karta hai.

## 🚀 VPS Deployment Guide

### 🔧 **System Requirements**
- **OS**: Ubuntu 20.04+ / Debian 11+ / CentOS 8+
- **RAM**: Minimum 1GB (Recommended 2GB+ for better performance)
- **Storage**: 5GB+ free space for music cache
- **Network**: Stable internet connection (10+ Mbps recommended)
- **Python**: 3.8+ required

### 📦 **Step-by-Step Installation**

#### **1. Update System & Install Dependencies**
```bash
# Update system packages
sudo apt-get update && sudo apt-get upgrade -y

# Install required packages
sudo apt-get install -y python3 python3-pip python3-venv git wget curl ffmpeg screen

# Install Node.js (for better audio processing)
curl -fsSL https://deb.nodesource.com/setup_lts.x | sudo -E bash -
sudo apt-get install -y nodejs

# Install additional audio libraries
sudo apt-get install -y libopus0 opus-tools libavcodec-extra
```

#### **2. Clone Repository**
```bash
# Clone the ShrutixMusic repository
git clone https://github.com/NoxxOP/ShrutixMusic
cd ShrutixMusic

# Make scripts executable
chmod +x start
```

#### **3. Setup Python Environment**
```bash
# Create virtual environment
python3 -m venv venv
source venv/bin/activate

# Upgrade pip and install dependencies
pip3 install --upgrade pip setuptools wheel
pip3 install -r requirements.txt
```

#### **4. Configure Environment Variables**
```bash
# Edit the .env file with your details
nano .env
```

**Required Configuration:**
```env
# Telegram API Credentials (Get from my.telegram.org)
API_ID=12345678
API_HASH=your_api_hash_here

# Bot Token (Get from @BotFather)
BOT_TOKEN=123456789:ABCdefGHIjklMNOpqrSTUvwxYZ

# Bot Information
BOT_NAME=ShrutixMusic
BOT_USERNAME=YourBotUsername

# Database (MongoDB Atlas - Free tier available)
MONGO_DB_URI=mongodb+srv://username:password@cluster.mongodb.net/ShrutixMusic

# Owner Details
OWNER_ID=your_telegram_user_id
OWNER_USERNAME=your_username

# Pyrogram Session String (Generate using @ShrutiSessionBot)
STRING1=your_session_string_here

# Optional: Additional Assistant Accounts
STRING2=
STRING3=
STRING4=
STRING5=

# Logging
LOG_GROUP_ID=-100xxxxxxxxx
LOG_CHANNEL_ID=-100xxxxxxxxx

# Support Links
SUPPORT_GROUP=https://t.me/ShrutiBotSupport
SUPPORT_CHANNEL=https://t.me/ShrutiBots

# Music Settings
DURATION_LIMIT_MIN=1440
AUTO_LEAVING_ASSISTANT=True
AUTO_LEAVE_ASSISTANT_TIME=3600

# Spotify Integration (Optional)
SPOTIFY_CLIENT_ID=your_spotify_client_id
SPOTIFY_CLIENT_SECRET=your_spotify_client_secret

# Additional Settings
START_IMG_URL=https://telegra.ph/file/your-image.jpg
UPSTREAM_REPO=https://github.com/NoxxOP/ShrutixMusic
UPSTREAM_BRANCH=main
GIT_TOKEN=your_github_token
```

#### **5. Running the Bot**

**Option A: Using Screen (Recommended for VPS)**
```bash
# Create a new screen session
screen -S shrutixmusic

# Start the bot
python3 -m ShrutixMusic

# Detach from screen: Press Ctrl+A then D
# To reattach later: screen -r shrutixmusic
```

**Option B: Direct Execution**
```bash
# Run directly (will stop when terminal closes)
python3 -m ShrutixMusic
```

**Option C: Using the Start Script**
```bash
# Use the provided start script
./start
```

**Option D: Background Service (Advanced)**
```bash
# Create systemd service
sudo nano /etc/systemd/system/shrutixmusic.service
```

Add this content:
```ini
[Unit]
Description=ShrutixMusic Telegram Bot
After=network.target

[Service]
Type=simple
User=your_username
WorkingDirectory=/path/to/ShrutixMusic
Environment=PATH=/path/to/ShrutixMusic/venv/bin
ExecStart=/path/to/ShrutixMusic/venv/bin/python -m ShrutixMusic
Restart=always
RestartSec=10

[Install]
WantedBy=multi-user.target
```

```bash
# Enable and start service
sudo systemctl daemon-reload
sudo systemctl enable shrutixmusic
sudo systemctl start shrutixmusic

# Check status
sudo systemctl status shrutixmusic

# View logs
journalctl -u shrutixmusic -f
```


### **Method 2: Online Generator**
Visit: [Session Generator](https://session-generator-tau.vercel.app/)
1. Enter your API_ID and API_HASH
2. Provide phone number and OTP
3. Get your session string

### **Method 3: Manual Generation**
```bash
# Install pyrogram if not installed
pip3 install pyrogram tgcrypto

# Create session generator script
nano generate_session.py
```

Add this code:
```python
from pyrogram import Client

API_ID = int(input("Enter your API_ID: "))
API_HASH = input("Enter your API_HASH: ")

with Client("my_account", API_ID, API_HASH) as app:
    print(f"Session String: {app.export_session_string()}")
```

```bash
# Run the generator
python3 generate_session.py
```

## 🛠️ Troubleshooting

### **Common Issues & Solutions**

#### **🎵 Music Not Playing**
```bash
# Check FFmpeg installation
ffmpeg -version

# Reinstall FFmpeg if needed
sudo apt-get remove ffmpeg
sudo apt-get install ffmpeg

# Check bot permissions in voice chat
# Make sure bot is admin with voice chat permissions
```

#### **🔊 Audio Quality Issues**
```bash
# Install additional audio codecs
sudo apt-get install ubuntu-restricted-extras

# For better opus support
sudo apt-get install libopus-dev opus-tools
```

#### **📱 Bot Not Responding**
```bash
# Check if bot is running
ps aux | grep python

# Check logs
tail -f logs/ShrutixMusic.log

# Restart bot
screen -r shrutixmusic
# Press Ctrl+C to stop, then restart with python3 -m ShrutixMusic
```

#### **🗄️ Database Connection Issues**
- Verify MongoDB URI is correct
- Check if your IP is whitelisted in MongoDB Atlas
- Ensure database user has read/write permissions

#### **🎤 Voice Chat Issues**
- Ensure bot has admin rights in the group
- Check if voice chat permissions are enabled
- Verify the bot can join voice chats

### **Performance Optimization**

#### **🚀 Server Performance**
```bash
# Increase system limits
echo "fs.file-max = 65536" | sudo tee -a /etc/sysctl.conf
echo "net.core.somaxconn = 65536" | sudo tee -a /etc/sysctl.conf
sudo sysctl -p

# Monitor resource usage
htop
# or
top
```

#### **🎵 Music Performance**
- Use SSD storage for faster audio processing
- Allocate at least 2GB RAM for smooth streaming
- Ensure stable internet (10+ Mbps for high quality)
- Close unnecessary applications to free up resources

## 🔄 Updates & Maintenance

### **Updating the Bot**
```bash
# Stop the bot first
screen -r shrutixmusic
# Press Ctrl+C to stop

# Pull latest changes
git pull origin main

# Update dependencies
source venv/bin/activate
pip3 install -r requirements.txt --upgrade

# Restart bot
python3 -m ShrutixMusic
```

### **Automated Updates (Optional)**
```bash
# Create update script
nano update.sh
```

```bash
#!/bin/bash
cd /path/to/ShrutixMusic
git pull origin main
source venv/bin/activate
pip3 install -r requirements.txt --upgrade
sudo systemctl restart shrutixmusic
echo "ShrutixMusic updated successfully!"
```

```bash
# Make executable and run
chmod +x update.sh
./update.sh
```

## 🎵 Music Sources & Compatibility

### **Supported Platforms**
- 🎵 **YouTube**: Songs, playlists, live streams
- 🎧 **Spotify**: Tracks, albums, playlists (requires API)
- ☁️ **SoundCloud**: Independent artists and tracks
- 🍎 **Apple Music**: Track information and search
- 🎶 **Deezer**: High-quality music streaming
- 📻 **Radio Stations**: Live radio streams
- 📁 **Local Files**: Upload and play personal music

### **Audio Formats Supported**
- **MP3**: Standard quality, widely compatible
- **FLAC**: Lossless audio, premium quality
- **OGG/Opus**: Optimized for Telegram
- **M4A/AAC**: High quality, smaller file size
- **WAV**: Uncompressed, studio quality

### **Quality Options**
- **Low**: 96kbps (data saving mode)
- **Medium**: 128kbps (balanced quality)
- **High**: 320kbps (premium quality)
- **Ultra**: FLAC/Lossless (maximum quality)

## 🌍 Multi-Language Support

ShrutixMusic supports multiple languages:
- 🇺🇸 **English** (Default)
- 🇮🇳 **Hindi** - `/language hindi`
- 🇪🇸 **Spanish** - `/language spanish`
- 🇫🇷 **French** - `/language french`
- 🇩🇪 **German** - `/language german`
- 🇷🇺 **Russian** - `/language russian`
- 🇯🇵 **Japanese** - `/language japanese`
- 🇰🇷 **Korean** - `/language korean`
- 🇨🇳 **Chinese** - `/language chinese`
- 🇧🇷 **Portuguese** - `/language portuguese`

## 📈 Analytics & Statistics

Track your bot's performance with built-in analytics:
- **Total Users**: Active users count
- **Music Played**: Total songs played
- **Popular Tracks**: Most requested songs
- **Usage Patterns**: Peak usage times
- **Server Performance**: Resource utilization

Access statistics with `/stats` command (admin only).

## 🤝 Contributing

We welcome contributions! Here's how you can help:

### **🐛 Bug Reports**
- Use GitHub Issues to report bugs
- Include detailed steps to reproduce
- Provide system information and logs

### **✨ Feature Requests**
- Suggest new music features
- Explain the use case and benefits
- Check existing issues first

### **💻 Code Contributions**
- Fork the repository
- Create feature branch
- Submit pull request with clear description

### **📝 Documentation**
- Improve README and guides
- Add usage examples
- Translate to other languages


### **Special Thanks**
- **Pyrogram** - Telegram MTProto API Framework
- **PyTgCalls** - Voice chat integration
- **YouTube-DL** - Media extraction
- **FFmpeg** - Audio/Video processing
- All contributors and testers

### **Open Source Libraries**
- pyrogram, pytgcalls, youtube-dl, ffmpeg-python
- aiohttp, aiofiles, motor, pymongo
- And many more amazing libraries!

## 📄 License

This project is licensed under the **MIT License** - see the [LICENSE](LICENSE) file for details.

### **License Summary**
- ✅ Commercial use allowed
- ✅ Modification allowed
- ✅ Distribution allowed
- ✅ Private use allowed
- ❌ Liability protection
- ❌ Warranty provided

