# 🛡️ RansomGuard-ML

![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)
![License](https://img.shields.io/badge/License-MIT-green.svg)
![Status](https://img.shields.io/badge/Status-In%20Development-yellow.svg)

**Real-time ransomware detection system using Machine Learning and behavioral analysis of Windows API calls**

## 🎯 Project Overview

RansomGuard-ML is an intelligent ransomware detection system that monitors Windows system behavior in real-time and alerts users when suspicious ransomware-like activity is detected. Built with scikit-learn and trained on API call sequences, it achieves 98%+ detection accuracy.

### Key Features
- ✅ Real-time behavioral monitoring
- ✅ Machine learning-based detection (Random Forest)
- ✅ 98%+ accuracy in ransomware detection
- ✅ Desktop notifications for immediate alerts
- ✅ Lightweight background service
- ✅ Multi-class classification (Ransomware, Malware, Benign)

## 🏗️ Architecture

┌─────────────────────┐
│   Sysmon Logs       │  ← Windows API monitoring
└──────────┬──────────┘
↓
┌─────────────────────┐
│  Feature Extraction │  ← N-gram + CF-NCF
└──────────┬──────────┘
↓
┌─────────────────────┐
│  Random Forest ML   │  ← Classification
└──────────┬──────────┘
↓
┌─────────────────────┐
│  Alert System       │  ← Real-time notifications
└─────────────────────┘


## 🚀 Quick Start

### Prerequisites
- Windows 10/11
- Python 3.8+
- Administrator privileges (for Sysmon)

### Installation

```bash
# Clone repository
git clone https://github.com/YOUR_USERNAME/RansomGuard-ML.git
cd RansomGuard-ML

# Install dependencies
pip install -r requirements.txt

# Download dataset (automated)
python src/data_collection/dataset_downloader.py

# Train model
python train.py

# Start real-time detection
python detect.py
```

## 📊 Dataset

Using public ransomware datasets:
- **CIC-MalMem-2022**: Memory dumps and behavioral logs
- **Ransomware samples**: 1000+ samples
- **Benign samples**: 300+ legitimate applications
- **Malware samples**: 900+ non-ransomware malware

## 🧠 Machine Learning Pipeline

1. **Data Collection**: Sysmon API call sequences
2. **Feature Engineering**: 4-gram generation with CF-NCF weighting
3. **Model Training**: Random Forest classifier (6 algorithms tested)
4. **Evaluation**: 5-fold cross-validation
5. **Deployment**: Real-time monitoring service

## 🔬 Technical Details

- **Feature Extraction**: Windows Native API n-grams (n=4)
- **Weighting Scheme**: CF-NCF (Class Frequency - Non-Class Frequency)
- **ML Algorithm**: Random Forest (100 estimators)
- **Monitoring**: Sysmon Event IDs 1, 3, 11, 13, 23

## 📚 Documentation

- [Setup Guide](docs/SETUP.md)
- [Architecture Details](docs/ARCHITECTURE.md)
- [Research Paper Reference](docs/paper_summary.md)

## 🤝 Contributing

Contributions welcome! Please read our contributing guidelines.

## 📄 License

MIT License - see [LICENSE](LICENSE) file

## 🙏 Acknowledgments

Based on research paper: "Ransomware detection using machine learning algorithms" by Bae et al.

## 📧 Contact

Your Name - [@your_twitter](https://twitter.com/your_twitter)

Project Link: [https://github.com/YOUR_USERNAME/RansomGuard-ML](https://github.com/Bilall2003/RansomGuard-ML)

---

⭐ Star this repo if you find it useful!
