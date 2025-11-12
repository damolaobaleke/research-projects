# Research Projects

A comprehensive collection of interdisciplinary research projects spanning antenna design, artificial intelligence, FPGA systems, and emerging technologies.

[![GitHub](https://img.shields.io/badge/github-research--projects-blue)](https://github.com/damolaobaleke/research-projects)
[![License](https://img.shields.io/badge/license-Research-orange)]()

## 📚 Table of Contents

- [Research Projects](#research-projects)
  - [📚 Table of Contents](#-table-of-contents)
  - [🔬 Overview](#-overview)
  - [🎯 Research Areas](#-research-areas)
    - [Antennas](#antennas)
    - [Artificial Intelligence](#artificial-intelligence)
      - [Version 1 (Simple Pipeline)](#version-1-simple-pipeline)
      - [Version 2 (Advanced Pipeline)](#version-2-advanced-pipeline)
    - [FPGAs and Electronics](#fpgas-and-electronics)
    - [AR and VR](#ar-and-vr)
    - [Robotics](#robotics)
    - [Video](#video)
  - [📂 Repository Structure](#-repository-structure)
  - [🔧 Prerequisites](#-prerequisites)
    - [For AI/NLP Projects:](#for-ainlp-projects)
    - [For Antenna Research:](#for-antenna-research)
    - [For FPGA Projects:](#for-fpga-projects)
  - [📊 Research Highlights](#-research-highlights)
    - [Key Achievements](#key-achievements)
    - [Technical Innovations](#technical-innovations)
  - [📝 Citation](#-citation)
  - [📧 Contact](#-contact)
  - [📄 License](#-license)
  - [🙏 Acknowledgments](#-acknowledgments)

---

## 🔬 Overview

This repository serves as a centralized hub for various research initiatives exploring cutting-edge technologies in hardware design, artificial intelligence, and multimedia systems. Each project represents a deep dive into specific engineering challenges with practical applications.

## 🎯 Research Areas

### Antennas

**Liquid Metal Antenna Research - Reconfigurable Monopole Antenna**

An experimental study of a reconfigurable monopole antenna designed using safe liquid metal (Galinstan) to achieve variable frequencies at different heights.

**Key Features:**
- **Frequency Range**: UHF (340MHz - 1GHz)
- **Technology**: Galinstan liquid metal alloy (68.5% Gallium, 21.5% Indium, 10% Tin)
- **Design**: Quarter-wavelength monopole with tunable electrical length
- **Applications**: Ground-based communications, satellite communications, vehicle-mounted antennas


📄 **Documentation**: [Liquid-Metal-Antenna-Research.pdf](Antennas/Liquid-Metal-Antenna-Research.pdf)

**Research Focus:**
- Antenna reconfigurability through liquid metal height adjustment
- Radiation pattern analysis for monopole structures
- Ground plane effects on finite-sized conducting surfaces
- Impedance matching techniques

---

### Artificial Intelligence

**Afrowatch AI African Dubbing System**

An advanced AI-powered dubbing system designed to translate and synchronize audio dialogue into 60+ African languages, addressing the lack of representation in animation and media.

**System Architectures:**

#### Version 1 (Simple Pipeline)
- **Models**: 3 AI models
- **Process**: Speech-to-Text → Translation → Text-to-Speech
- **Languages**: 20+ African languages
- **Use Case**: Quick prototyping and basic dubbing

#### Version 2 (Advanced Pipeline)
- **Models**: 6 AI models
- **Process**: Background Separation → Speaker Diarization → Gender Detection → Speech-to-Text → Translation → Text-to-Speech
- **Languages**: 60+ African languages
- **Use Case**: Production-ready professional dubbing

**AI Models Used:**
- **Demucs** - Background noise isolation
- **pyannote/speaker-diarization-3.1** - Speaker segmentation
- **wav2vec2-large-robust-24-ft-age-gender** - Gender identification
- **OpenAI Whisper** - Speech transcription
- **Meta NLLB** - Neural machine translation (No Language Left Behind)
- **Multiple TTS Engines** - MMS, Coqui TTS, OpenAI TTS, Edge TTS

**Supported African Languages (by Region):**
| Region | Languages |
|--------|-----------|
| **North Africa & Horn** | Arabic variants, Amharic, Tigrinya, Oromo, Somali, Kabyle, Tamazight |
| **West Africa** | Yoruba, Igbo, Hausa, Fulfulde, Bambara, Wolof, Ewe, Fon, Twi |
| **Central Africa** | Lingala, Kongo, Luba-Lulua, Chichewa, Bemba, Kimbundu, Sango |
| **East Africa** | Swahili, Luo, Kamba, Kikuyu, Nuer |
| **Southern Africa** | Zulu, Xhosa, Tswana, Tsonga, Shona, Swati, Sotho, Chokwe |

**Key Features:**
- Background music and sound effects preservation
- Gender-specific voice synthesis
- Multi-speaker diarization
- Subtitle generation (dubbed and original)
- REST API and CLI interfaces
- Docker deployment ready

📄 **Documentation**: [african_languages_nlp.md](Artificial%20Intelligence/african_languages_nlp.md)

**Applications:**
- Animation and film dubbing
- Educational content localization
- News and media accessibility
- Cultural preservation through technology

---

### FPGAs and Electronics

**FPGA Design and Circuit Systems**

Research and development projects focusing on Field-Programmable Gate Array (FPGA) design methodologies and electronic circuit implementations.

**Available Resources:**
- 📄 [Circuit Design FPGA](FPGAs%20and%20Electronics/circuit_design_fpga.pdf)
- 📄 [FPGA Design Requirements](FPGAs%20and%20Electronics/Fpga_design_requirements.pdf)

**Research Areas:**
- Digital circuit design and implementation
- Hardware description languages (HDL)
- FPGA architecture and optimization
- System-on-Chip (SoC) development
- Signal processing implementations

---

### AR and VR

**Augmented and Virtual Reality Research**

*Coming Soon*

Exploring immersive technologies and spatial computing applications.

---

### Robotics

**Robotics and Autonomous Systems**

*Coming Soon*

Research in robotic control systems, automation, and intelligent machines.

---

### Video

**Video Processing and Computer Vision**

*Coming Soon*

Investigation into video analysis, processing techniques, and visual computing.

---

## 📂 Repository Structure

```
research-projects/
├── Antennas/
│   └── Liquid-Metal-Antenna-Research.pdf
├── Artificial Intelligence/
│   └── african_languages_nlp.md
├── FPGAs and Electronics/
│   ├── circuit_design_fpga.pdf
│   └── Fpga_design_requirements.pdf
├── AR and VR/
├── Robotics/
├── Video/
├── .gitignore
└── README.md
```

## 🔧 Prerequisites

Depending on the project you're working with:

### For AI/NLP Projects:
```bash
- Python 3.8+
- FFmpeg
- CUDA (optional, for GPU acceleration)
- HuggingFace account and API token
```

### For Antenna Research:
```bash
- Vector Network Analyzer (VNA)
- Arduino IDE
- CAD software (for mechanical design)
- MATLAB or AWR Design Environment
```

### For FPGA Projects:
```bash
- Xilinx Vivado or Intel Quartus
- HDL simulation tools
- FPGA development board
```

## 📊 Research Highlights

### Key Achievements
- ✅ Successfully developed tunable liquid metal antenna with UHF frequency range
- ✅ Created multilingual AI dubbing system supporting 60+ African languages
- ✅ Documented FPGA design methodologies for digital circuit implementation
- 🔄 Ongoing research in AR/VR, robotics, and video processing

### Technical Innovations
- Non-toxic liquid metal antenna design with Arduino-controlled frequency tuning
- End-to-end AI pipeline for professional-grade audio dubbing
- Comprehensive VNA analysis and impedance matching techniques
- Multi-modal AI integration (speech, vision, translation)

## 📝 Citation

If you use any of this research in your work, please cite appropriately:

```bibtex
@misc{damolaobaleke2025research,
  author = {Obaleke, Ayomipo Oyindamola},
  title = {Multi-Disciplinary Engineering Research Projects},
  year = {2025},
  publisher = {GitHub},
  url = {https://github.com/damolaobaleke/research-projects}
}
```

## 📧 Contact

**Oyindamola Obaleke**

For inquiries, collaborations, or questions:
- GitHub: [@damolaobaleke](https://github.com/damolaobaleke)
- Repository: [research-projects](https://github.com/damolaobaleke/research-projects)

---

## 📄 License

This repository contains research materials and documentation. Individual projects may have specific licenses. Please refer to individual project documentation for licensing details.

---

## 🙏 Acknowledgments

- **Loughborough University** - Antenna research supervision and facilities
- **Afrowatch** - AI dubbing system development and African language support
- **Meta AI, OpenAI, HuggingFace** - AI models and infrastructure
- **Academic supervisors and collaborators** - Research guidance and support

---

<p align="center">
  <b>Built with passion for innovation in engineering and technology</b>
</p>

<p align="center">
  ⭐ Star this repository if you find it useful!
</p>
