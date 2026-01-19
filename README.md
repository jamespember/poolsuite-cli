# Poolsuite CLI 🏖️

> Ultra-summer internet radio from your terminal

An **unofficial** command-line player for [Poolsuite FM](https://poolsuite.net/)'s curated playlists. Stream their amazing music selections directly from your terminal!

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

## 🎵 About

This CLI tool lets you enjoy [Poolsuite FM](https://poolsuite.net/)'s expertly curated music from the comfort of your command line. All music curation credit goes to the amazing team at Poolsuite FM!

**What is Poolsuite FM?**

Poolsuite FM (formerly Poolside FM) is the ultra-summer internet radio station, playing an infinity pool of summer sounds 24/7. They curate incredible playlists ranging from balearic sunsets to Tokyo disco, indie summer vibes to hangover club recovery sessions.

**This is an unofficial tool** - please support the original service:
- 🌐 Website: [poolsuite.net](https://poolsuite.net/)
- 📱 Get their official app on [iPhone](https://poolsuite.net/) and Mac
- 🎧 Follow them on [SoundCloud](https://soundcloud.com/poolsuite)
- 📸 Instagram: [@poolsuite](https://instagram.com/poolsuite)

## ✨ Features

- 🎵 **8 Curated Playlists** - Official FM, Tokyo Disco, Indie Summer, and more
- 🔀 **Shuffle Support** - Random playback for variety
- ⚡ **Lightweight** - Direct audio streaming, no browser needed
- 🎨 **Beautiful Terminal UI** - Colored interface with ASCII art
- 🎹 **Full Playback Controls** - Play, pause, skip, volume control
- 🔧 **Flexible** - Works with mpv, ffplay, or custom players

## 📦 Installation

### Prerequisites

You need one of these media players installed:

**Option 1: mpv (recommended)**
```bash
# macOS
brew install mpv

# Arch Linux
sudo pacman -S mpv

# Ubuntu/Debian
sudo apt install mpv

# Fedora
sudo dnf install mpv
```

**Option 2: yt-dlp + ffplay**
```bash
# macOS
brew install yt-dlp ffmpeg

# Arch Linux
sudo pacman -S yt-dlp ffmpeg

# Ubuntu/Debian
sudo apt install yt-dlp ffmpeg
```

### Quick Install

```bash
# Clone the repository
git clone https://github.com/jamespember/poolsuite-cli.git
cd poolsuite-cli

# Run the installer
./install.sh
```

The installer will:
1. ✓ Check for required dependencies
2. ✓ Make the script executable
3. ✓ Offer to install system-wide or to `~/.local/bin`

### Manual Install

```bash
# Make executable
chmod +x poolsuite

# Option 1: Link to /usr/local/bin (requires sudo)
sudo ln -s "$(pwd)/poolsuite" /usr/local/bin/poolsuite

# Option 2: Copy to ~/.local/bin (no sudo needed)
mkdir -p ~/.local/bin
cp poolsuite ~/.local/bin/
# Make sure ~/.local/bin is in your PATH
```

## 🚀 Usage

### Quick Start

```bash
# Play the default official playlist
poolsuite

# Play a specific playlist
poolsuite tokyo

# Shuffle mode
poolsuite friday --shuffle

# List all available playlists
poolsuite --list
```

### Available Playlists

| Command | Description |
|---------|-------------|
| `official` | Official Poolsuite FM Playlist *(default)* |
| `official2` | Official Poolsuite FM Playlist Two |
| `mixtapes` | Poolsuite Mixtapes Collection |
| `balearic` | Balearic Sundown - Sunset vibes |
| `indie` | Indie Summer - Indie gems |
| `tokyo` | Tokyo Disco - Japanese city pop |
| `friday` | Friday Nite Heat - Weekend energy |
| `hangover` | Hangover Club - Recovery tunes |

### Examples

```bash
# Chill sunset vibes
poolsuite balearic

# Party mode with shuffle
poolsuite friday --shuffle

# Focus music for work
poolsuite indie

# Late night recovery
poolsuite hangover

# Tokyo city pop
poolsuite tokyo
```

### Playback Controls (mpv)

| Key | Action |
|-----|--------|
| `Space` | Play/Pause |
| `9` / `0` | Volume down/up |
| `m` | Mute/Unmute |
| `>` | Next track |
| `<` | Previous track |
| `q` | Quit |
| `f` | Toggle fullscreen visualizer |

### Advanced Options

```bash
# Use a different player
export POOLSUITE_PLAYER=vlc
poolsuite

# Show version
poolsuite --version

# Show help
poolsuite --help
```

## 🛠️ How It Works

This tool streams music from Poolsuite FM's public SoundCloud playlists:

1. **Discovery** - Reverse-engineered Poolsuite's web player to find their SoundCloud URLs
2. **Streaming** - Uses `mpv` or `yt-dlp` to stream directly from SoundCloud
3. **Playback** - Handles HLS/DASH streaming automatically (160kbps AAC)

**Technical Details:**
- All playlists are publicly available on [SoundCloud](https://soundcloud.com/poolsuite)
- No API keys or authentication required
- Streams use SoundCloud's HLS/DASH protocol (`.m4s` segments)
- Zero web overhead - just pure audio streaming

See [TECHNICAL.md](TECHNICAL.md) for full reverse-engineering details.

## 🐛 Troubleshooting

### "No compatible player found"

Install mpv or yt-dlp:
```bash
# macOS
brew install mpv

# Linux
sudo apt install mpv  # or: sudo pacman -S mpv
```

### Playback stuttering or buffering

1. Check your internet connection
2. Update yt-dlp if using ffplay:
   ```bash
   pip install --upgrade yt-dlp
   ```
3. Try using mpv instead (better performance):
   ```bash
   export POOLSUITE_PLAYER=mpv
   ```

### SoundCloud URLs not working

SoundCloud playlist URLs are public and stable, but if you encounter issues:
1. Verify you can access [soundcloud.com/poolsuite](https://soundcloud.com/poolsuite)
2. Update mpv or yt-dlp to the latest version
3. Check if SoundCloud is accessible in your region

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

**Before contributing:**
- Ensure changes don't violate Poolsuite FM or SoundCloud's terms of service
- Test with multiple playlists
- Follow existing code style
- Update documentation as needed

## 📝 License

MIT License - see [LICENSE](LICENSE) file for details

## 💝 Credits & Acknowledgments

**All music curation credit goes to [Poolsuite FM](https://poolsuite.net/)** 🏖️

This is an **unofficial**, fan-made tool. I absolutely love Poolsuite FM and their incredible music curation. This tool simply provides an alternative way to enjoy their public playlists from the terminal.

**Please support the official service:**
- 🌐 Visit [poolsuite.net](https://poolsuite.net/)
- 💳 Consider their [membership perks](https://poolsuite.net/)
- 📱 Download their official apps
- 📸 Follow [@poolsuite](https://instagram.com/poolsuite) on Instagram
- 🎧 Follow them on [SoundCloud](https://soundcloud.com/poolsuite)

**Built with:**
- [mpv](https://mpv.io/) - Media player
- [yt-dlp](https://github.com/yt-dlp/yt-dlp) - Download tool
- [SoundCloud](https://soundcloud.com/) - Music hosting

## ⚖️ Disclaimer

This is an unofficial tool and is not affiliated with, endorsed by, or connected to Poolsuite FM in any way. All trademarks, service marks, trade names, and logos referenced belong to their respective owners.

This tool only accesses publicly available playlists on SoundCloud and does not circumvent any paid features or access restrictions. It's simply a convenience wrapper for streaming public content.

If you represent Poolsuite FM and have concerns about this project, please open an issue and I'll address it immediately.

---

Made with ☀️ for summer vibes all year round | [Report Bug](https://github.com/jamespember/poolsuite-cli/issues) | [Request Feature](https://github.com/jamespember/poolsuite-cli/issues)
