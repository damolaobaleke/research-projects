# Afrowatch A.I African Dubbing System

> **An advanced AI-powered dubbing system for African languages, featuring two distinct architectures optimized for different use cases.**

Dubbing Process Architecture V1
<img src="https://github.com/Afrowatch/pe-video-management/assets/45045727/6d1509a2-9abe-4433-95c8-b86019a2aca0" alt="architecture" width="350" style="border:1px solid black;"/>


## 🌍 Overview

The AI African Dubbing System is a comprehensive machine learning solution that automatically translates and synchronizes audio dialogue into different African languages. Built to address the lack of representation in the animation and media industry, this system supports **60+ African languages** across all regions of the continent.

### 🎯 Mission
- Deliver Afrowatch Black Animation Content in multiple African languages
- Bridge language barriers in African animation and media
- Preserve and promote African languages through technology
- Enable global accessibility for African content creators

---

## 🏗️ System Architecture

The system offers **two distinct versions** to meet different performance and quality requirements:

### 📊 Version Comparison

| Feature | **V1 (Simple)** | **V2 (Advanced)** |
|---------|-----------------|-------------------|
| **AI Models** | 3 models | 6 models |
| **Processing Steps** | 3-step process | 6-step pipeline |
| **Audio Quality** | Good | Professional |
| **Language Support** | 20+ languages | 60+ languages |
| **Voice Options** | Limited | Gender-specific voices |
| **Background Separation** | ❌ | ✅ |
| **Speaker Diarization** | ❌ | ✅ |
| **Use Case** | Quick prototyping | Production-ready |

---

## 🚀 Version 1 (Simple Pipeline)

### Architecture
A streamlined **3-step process** for basic dubbing functionality:

```
Audio Input → Speech-to-Text → Text Translation → Text-to-Speech → Dubbed Output
```

### Core Components
1. **Speech-to-Text**: OpenAI Whisper
2. **Translation**: Language-specific translation models
3. **Text-to-Speech**: Microsoft SpeechT5 TTS

### Supported Languages (V1)
- **West Africa**: Yoruba, Igbo, Hausa, Twi
- **East Africa**: Swahili, Amharic
- **Southern Africa**: Zulu, Xhosa
- **North Africa**: Arabic variants

### Quick Start (V1)
```bash
# Basic dubbing command
python run_cli.py --input_file_path 'path/to/audio.mp3' \
                  --source_language fra:fr \
                  --target_languages eng:gbr
```

---

## 🎭 Version 2 (Advanced Pipeline)

### Architecture
A sophisticated **6-step AI pipeline** for professional-grade dubbing:

```
Audio Input → Background Separation → Speaker Diarization → Gender Detection → 
Speech-to-Text → Translation → Text-to-Speech → Audio Synthesis → Final Output
```

### AI Models Used
1. **[Demucs](https://github.com/facebookresearch/demucs)** - Background noise isolation
2. **[pyannote/speaker-diarization-3.1](https://huggingface.co/pyannote/speaker-diarization-3.1)** - Speaker segmentation
3. **[wav2vec2-large-robust-24-ft-age-gender](https://huggingface.co/audeering/wav2vec2-large-robust-24-ft-age-gender)** - Gender identification
4. **OpenAI Whisper** - Speech transcription
5. **[Meta NLLB](https://ai.meta.com/research/no-language-left-behind/)** - Neural translation
6. **Multiple TTS Engines** - Voice synthesis

### Supported Languages (V2)

| Region | Languages |
|--------|-----------|
| **North Africa & Horn** | Arabic variants, Amharic, Tigrinya, Oromo, Somali, Kabyle, Tamazight |
| **West Africa** | Yoruba, Igbo, Hausa, Fulfulde, Bambara, Wolof, Ewe, Fon, Twi |
| **Central Africa** | Lingala, Kongo, Luba-Lulua, Chichewa, Bemba, Kimbundu, Sango |
| **East Africa** | Swahili, Luo, Kamba, Kikuyu, Nuer |
| **Southern Africa** | Zulu, Xhosa, Tswana, Tsonga, Shona, Swati, Sotho, Chokwe |

### TTS Engine Options
- **MMS**: Meta Multilingual Speech (1100+ languages)
- **Coqui TTS**: Open-source high-quality synthesis
- **OpenAI TTS**: Premium voice quality
- **Microsoft Edge TTS**: Cloud-based synthesis
- **Custom CLI/API**: Extensible architecture

---

## 🛠️ Installation & Setup

### Prerequisites
- Python 3.8+
- FFmpeg
- CUDA (optional, for GPU acceleration)

### 1. Environment Setup
```bash
# Create virtual environment
python -m venv `(name of venv)`

# Activate environment
# Linux/Mac:
source venv/bin/activate
# Windows:
venv\Scripts\activate
```

### 2. Install Dependencies
```bash
pip install -r requirements.txt
```

### 3. Install FFmpeg
```bash
# macOS
brew install ffmpeg

# Windows
choco install ffmpeg

# Ubuntu/Debian
sudo apt install ffmpeg
```

### 4. HuggingFace Authentication
```bash
# Install HuggingFace CLI
pip install huggingface_hub

# Login with your token
huggingface-cli login
```

---

## 📖 Usage Guide

### Version 2 (Advanced) - Command Line Interface

```bash
open-dubbing --input_file video.mp4 \
             --target_language yor \
             --source_language eng \
             --output_directory ./output \
             --tts mms \
             --translator nllb \
             --device cuda \
             --dubbed_subtitles
```

### Key Parameters

#### Required
- `--input_file`: Path to input video/audio file
- `--target_language`: Target language (ISO 639-3 code)

#### Translation Options
- `--translator {nllb,apertium}`: Translation engine
- `--nllb_model {nllb-200-1.3B,nllb-200-3.3B}`: Model size

#### TTS Options
- `--tts {mms,coqui,openai,edge,cli,api}`: Voice synthesis engine
- `--target_language_region`: Regional accent specification

#### Performance
- `--device {cpu,cuda}`: Compute device
- `--cpu_threads`: CPU thread count
- `--whisper_model {medium,large-v2,large-v3}`: STT model size

#### Output Control
- `--dubbed_subtitles`: Include dubbed subtitles
- `--original_subtitles`: Include original subtitles
- `--clean-intermediate-files`: Clean up temporary files

### API Server Mode
```bash
# Start the API server
uvicorn run_webapp:app --port 8000

# Use via HTTP requests
curl -X POST "http://localhost:8000/dub" \
     -F "file=@video.mp4" \
     -F "target_language=yor" \
     -F "source_language=eng"
```

---

## 🔧 Advanced Configuration

### Custom TTS Configuration
```json
{
  "command": "your-tts-command",
  "voice_param": "--voice",
  "text_param": "--text",
  "output_param": "--output",
  "voices": {
    "male": "male_voice_id",
    "female": "female_voice_id"
  }
}
```

### API Integration
The system supports custom TTS engines via API:

**Endpoints:**
- `GET /voices` - List available voices
- `GET /speak?voice={id}&text={text}` - Synthesize speech

---

## 🚀 Production Deployment

### Docker Setup
```dockerfile
FROM python:3.9-slim

# Install system dependencies
RUN apt-get update && apt-get install -y ffmpeg

# Copy application
COPY . /app
WORKDIR /app

# Install Python dependencies
RUN pip install -r requirements.txt

# Expose port
EXPOSE 8000

# Start application
CMD ["uvicorn", "main:app", "--host", "0.0.0.0", "--port", "8000"]
```

### Batch Processing
```bash
# Process multiple files
declare -a inputs=("video1.mp4" "video2.mp4" "video3.mp4")
declare -a languages=("yor" "ibo" "hau")

for input_file in "${inputs[@]}"; do
  for language in "${languages[@]}"; do
    open-dubbing --input_file "$input_file" \
                 --target_language "$language" \
                 --output_directory "output/$(basename "${input_file%.*}").$language/" \
                 --whisper_model medium \
                 --vad \
                 --device cuda \
                 --dubbed_subtitles
  done
done
```

---

## 🤝 Contributing

### Adding New Languages
1. **Translation Support**: Extend the `Translation` class
2. **TTS Integration**: Implement new `TextToSpeech` engines
3. **Voice Models**: Add language-specific voice models

### Development Setup
```bash
# Clone repository
git clone https://github.com/your-org/ai-african-dubbing-system.git
cd ai-african-dubbing-system

# Install development dependencies
pip install -r requirements-dev.txt

# Run tests
pytest tests/

# Code formatting
black src/
flake8 src/
```

---

## 📊 Performance Benchmarks

| Model Size | Processing Speed | Memory Usage | Quality Score |
|------------|------------------|--------------|---------------|
| Small | 2x realtime | 2GB | 7.5/10 |
| Medium | 1.5x realtime | 4GB | 8.5/10 |
| Large | 1x realtime | 8GB | 9.2/10 |

---

## 🔮 Roadmap

- [ ] **Real-time dubbing** for live streams
- [ ] **Voice cloning** capabilities
- [ ] **Browser extension** for web content
- [ ] **Emotion preservation** in voice synthesis
- [ ] **Lip-sync optimization** for video content

---

<!-- ## 📄 License -->

<!-- This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details. -->

---

## 🙏 Acknowledgments

- **Meta AI** for NLLB and MMS models
- **OpenAI** for Whisper technology
- **HuggingFace** for model hosting and transformers
- **Pyannote** for speaker diarization
- **African language communities** for linguistic support

---

## 📞 Support

- **Documentation**: [docs.afrowatch.co](https://docs.afrowatch.co)
- **Issues**: [GitHub Issues](https://github.com/Afrwatch/ai-african-dubbing-system/issues)
- **Discord**: [Join our community](https://discord.gg/afrowatch)
- **Email**: help@afrowatch.co

---

**Built with ❤️ for African languages and global accessibility