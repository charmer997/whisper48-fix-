# Whisper48

English | [简体中文](https://github.com/ifeimi/Whisper48/blob/main/README_CN.md)

## What is Whisper48?

**Whisper48** is an easy-to-use tool for automatically generating **accurate subtitles** from videos and audio files. It uses advanced AI models to:

- ✅ Convert speech to text automatically
- ✅ Generate accurate word-level timestamps (when each word is spoken)
- ✅ Support multiple languages (Japanese, Chinese, English, French, German, Spanish, Italian, Portuguese, Russian, and more)
- ✅ Work completely in the cloud (no installation required!)

**Perfect for:** Video creators, translators, content producers, podcast editors, and anyone who needs to transcribe audio without tedious manual work.

---

## 🚀 Quick Start Guide (No Programming Knowledge Required!)

### Option 1: Cloud-Based (Recommended for Beginners)

The easiest way to use Whisper48 is through **Google Colab** - a free cloud service that runs the software for you. No installation needed!

#### Step-by-Step Instructions:

**1. Prepare Your Files**
   - Have your audio or video file ready (MP3, WAV, MP4, MKV, etc.)
   - Upload it to your **Google Drive** (if you don't have one, create a free Google account)
   - Place your file in any folder in Google Drive - the notebook will help you find it

**2. Open the Notebook**
   - Click this link: [**WhisperX48 on Google Colab**](https://colab.research.google.com/github/ifeimi/Whisper48/blob/main/WhisperX48.ipynb)
   - Google will open the notebook in your browser

**3. Configure GPU (Important!)**
   - At the top of the page, click `Runtime` → `Change runtime type`
   - Select **GPU** as the hardware accelerator
   - Click `Save`
   - This gives you free computing power to process your files faster

**4. Run Each Step in Order**
   - Each cell (code block) has clear instructions in both **Chinese and English**
   - Click the ▶ button (or press Ctrl+Enter) to run each cell one by one
   - Wait for it to finish before moving to the next one
   - The notebook will guide you through:
     1. Connecting to Google Drive
     2. Installing required software
     3. Selecting your media file
     4. Configuring settings (language, model size, etc.)
     5. Processing and downloading your subtitles

**5. Download Your Subtitles**
   - After processing completes, the subtitle file (`.srt` format) will automatically download
   - Use this file in any video editor (Adobe Premiere, DaVinci Resolve, CapCut, etc.)

#### Tips for Best Results:
- **Audio Quality**: Clearer audio = better results. If possible, use the original audio track rather than compressed versions
- **Model Size**: Choose `large-v2` or `large-v3` for best accuracy. Larger models take longer but are more accurate
- **Language Selection**: Select the correct language of your content for better accuracy
- **Chunk Size**: Leave at 5 seconds (default) unless you know what you're doing

#### Troubleshooting Common Issues:

| Issue | Solution |
|-------|----------|
| "GPU not found" error | Go to `Runtime` → `Change runtime type` and make sure GPU is selected |
| Running very slowly | GPU memory issue - reduce `batch_size` in advanced settings, or use a smaller model |
| Subtitles have poor timing | Try using `large-v3` model instead of `large-v2`, or check if audio quality is good |
| File not appearing in browser | Run the file browser cell again (step 1.3) to refresh the file list |

---

### Option 2: Run Locally on Your Computer

**Requirements:**
- Advanced technical knowledge
- Python programming experience
- Powerful GPU (NVIDIA recommended)
- 30+ GB of free disk space

**Instructions:**
Try running [this script](https://github.com/ifeimi/Whisper48/blob/main/WhisperX48_local.ipynb) on your own computer. You will need to install PyTorch, WhisperX, FFmpeg, and other dependencies first.

⚠️ **Note:** Local setup is complex and not tested thoroughly. We recommend using Google Colab instead. 

---

## 📊 Features Explained

### What Makes Whisper48 Special?

**WhisperX Technology**: Unlike standard Whisper, WhisperX provides **word-level timestamps**:
- Standard Whisper: "Hello world" (0:00-0:05)
- WhisperX: "Hello" (0:00-0:02) "world" (0:02-0:05)

This precision allows for better subtitle synchronization and more professional results.

### Supported Languages
- 🇯🇵 Japanese (日本語)
- 🇨🇳 Chinese (中文)
- 🇬🇧 English
- 🇫🇷 French
- 🇩🇪 German
- 🇪🇸 Spanish
- 🇮🇹 Italian
- 🇵🇹 Portuguese
- 🇷🇺 Russian
- And many more...

### Supported File Formats
- **Audio**: MP3, WAV, M4A, AAC, FLAC
- **Video**: MP4, MKV, TS, FLV

---

## 📝 Examples & Sample Output

For a comparison between WhisperX and other models please have a look here: [https://www.bilibili.com/video/BV1RFa5zhEeG/](https://www.bilibili.com/video/BV1RFa5zhEeG/)

---

## 🔧 How It Works (Technical Overview)

Whisper48 uses a 3-step process:

1. **Speech Recognition**: OpenAI's Whisper model converts audio to text
2. **Timestamp Alignment**: WhisperX uses wav2vec2.0 to align text with precise word timings
3. **Subtitle Generation**: Automatic subtitle formatting and download

The entire process runs on Google Colab's free GPU servers - no installation needed on your computer!

---

## 🙋 Support & Troubleshooting

### Getting Help

- **Website**: Detailed guides and FAQ: [ifeimi.github.io/whisper48](https://ifeimi.github.io/whisper48/)
- **Email**: Contact the developer at: yfwu0202 AT gmail DOT com
- **GitHub Issues**: Report bugs or request features on [the project's issue page](https://github.com/ifeimi/Whisper48/issues)

---

## 📚 Technical References & Credits

### Built On Top Of:

This project is based on excellent open-source software:

- **[WhisperX](https://github.com/m-bain/whisperX)**: Improves OpenAI's Whisper with accurate word-level timestamps
- **[OpenAI Whisper](https://github.com/openai/whisper)**: State-of-the-art speech recognition model
- **[faster-whisper](https://github.com/guillaumekln/faster-whisper)**: Optimized Whisper implementation
- **[wav2vec2.0](https://huggingface.co/facebook/wav2vec2-large-960h-lv60-self)**: Speech model for timestamp alignment

### Project Origins

Whisper48 started as a fork from **N46Whisper** and has been significantly modified to:
- Use more accurate Whisper-based models (WhisperX)
- Improve Japanese language support
- Provide better timestamp accuracy
- Add more language options
- Simplify the user interface

We encourage contributions to both this project and the upstream projects!

---

## 📄 License & Copyright

This project is released under the **MIT License**. See [LICENSE.md](https://github.com/ifeimi/Whisper48/blob/main/LICENSE.md) for details.

### Attribution

- Original concept: [N46Whisper](https://github.com/Ayanaminn/N46Whisper) by Ayanaminn
- Improvements: WhisperX integration and optimization
- Code improvements: Bilingual documentation and interface enhancements

You are free to:
- ✅ Use for personal and commercial projects
- ✅ Modify and redistribute
- ✅ Study and learn from the code

You must:
- ✅ Include the license text
- ✅ Credit the original authors

---

## 📞 Contact & Support

Have questions or suggestions? Get in touch!

- **Email**: ifeimi48 AT gmail DOT com
- **GitHub Issues**: [Report bugs or request features](https://github.com/ifeimi/Whisper48/issues)
- **Website**: [ifeimi.github.io/whisper48](https://ifeimi.github.io/whisper48/)

I would love to hear your feedback and help with any questions!

---

**Last updated**: January 2026

![GitHub License](https://img.shields.io/github/license/ifeimi/Whisper48)
![GitHub Stars](https://img.shields.io/github/stars/ifeimi/Whisper48?style=social)
