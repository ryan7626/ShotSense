# ShotSense  
_On-device AI for intelligent photo composition._

---

## Overview  

**ShotSense** is an iOS app that leverages on-device artificial intelligence to guide photographers toward better picture composition.  
By analyzing the live camera feed, it detects subjects, evaluates framing, and provides real-time visual feedback based on professional composition rules such as the rule of thirds, symmetry, and leading lines.  

Built entirely with **Swift**, **SwiftUI**, and **CoreML**, ShotSense demonstrates how powerful AI-assisted creativity can run privately and efficiently on-device — without cloud dependencies.  

![App Preview Placeholder](docs/app-preview.png)

---

## Core Features  

| Feature | Description | Status |
|----------|--------------|--------|
| Live Camera Feed | Capture real-time video stream using AVFoundation | ✅ MVP |
| Composition Grid Overlay | Visual guide for rule-of-thirds alignment | ✅ MVP |
| Subject Detection | Detects main subject and framing position | 🧠 In Progress |
| Composition Feedback | Textual hints for better alignment or framing | 🧠 In Progress |
| On-device AI Inference | Pre-trained model integrated with CoreML | 🧩 Planned |
| Custom Fine-tuned Model | Fine-tuned dataset for aesthetic composition | 🔬 Planned |
| Photo Capture & Save | Save optimized shots locally | 🧩 Planned |
| Offline Mode | 100% on-device intelligence | 🔒 Planned |

---

## Tech Stack  

- **Language:** Swift (SwiftUI, Combine)  
- **Frameworks:** CoreML, Vision, AVFoundation, CoreImage  
- **Model Conversion (future):** PyTorch → CoreMLTools pipeline  
- **Development Environment:** macOS + Xcode  
- **Version Control:** Git & GitHub  

---

## Architecture Overview  

![Architecture Diagram Placeholder](docs/architecture-diagram.png)

**Modular Design**

1. **Camera Engine**  
   - Handles live video input using AVFoundation.  
   - Streams frames into the AI Analyzer module.

2. **AI Analyzer**  
   - Runs composition model inference locally with CoreML + Vision.  
   - Outputs subject bounding boxes and composition metrics.

3. **Feedback Layer**  
   - Displays visual overlays and guidance text using SwiftUI.  
   - Updates dynamically based on real-time analysis results.

---

## AI Integration Strategy  

ShotSense currently integrates a **pre-trained computer vision model** (e.g., MobileNetV3 or YOLOv8 CoreML) to detect subjects and basic composition cues.  
The long-term goal is to **fine-tune a custom model** trained on a dataset of professionally composed images to evaluate framing quality more intelligently.  

**Pipeline Overview:**  
1. Pre-trained PyTorch model (vision)  
2. Export → CoreMLTools  
3. Optimize for iOS using quantization & model compression  
4. Run inference on-device with CoreML + Vision  

This ensures ShotSense remains **fast, private, and responsive** — even offline.  

---

## Setup & Run  

**Requirements:**  
- macOS with Xcode 15+  
- iOS 17+ target  
- Swift 5.9+  

**Build Instructions:**  
```bash
# Clone repository
git clone https://github.com/yourusername/shotsense-ios.git
cd shotsense-ios

# Open project in Xcode
open ShotSense.xcodeproj
