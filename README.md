# Automatic Number Plate Recognition (ANPR) 🚗🔍

This project implements an **Automatic Number Plate Recognition (ANPR)** system using **YOLOv8** for license plate detection and **EasyOCR** for text recognition. The system processes video input, detects license plates in real-time, extracts plate text, applies OCR corrections, and stabilizes predictions across frames for accuracy.

---

## 📌 Features

- **Real-time License Plate Detection**: Utilizes YOLOv8, a state-of-the-art object detection model, to locate license plates in each frame of the input video.
- **Text Extraction with EasyOCR**: Extracts text from detected license plates using EasyOCR, which supports multiple languages and works well with various fonts and backgrounds.
- **OCR Error Correction**: Applies custom rules and post-processing to correct common OCR mistakes, improving the reliability of recognized text.
- **Prediction Stabilization**: Uses a history buffer to smooth out predictions across frames, reducing flicker and false positives.
- **Annotated Video Output**: Overlays bounding boxes and recognized text on the video frames, saving the annotated output for review or further processing.
- **Modular Design**: Easily extendable for different detection models, OCR engines, or post-processing techniques.

---

## 🚀 Getting Started


### 1. Download YOLOv8 Weights

Place your YOLOv8 weights in the `models/` directory. You can train your own model or use pre-trained weights.

### 2. Run the ANPR Pipeline

```bash
python run.py --input data/sample_video.mp4 --output output/annotated_video.mp4
```

---

## ⚙️ Configuration

- **YOLOv8 Model Path**: Set in `src/detector.py`
- **OCR Language**: Configurable in `src/ocr.py`
- **History Buffer Size**: Adjustable in `src/stabilizer.py`

---

## 📝 How It Works

1. **Detection**: Each frame is processed by YOLOv8 to detect license plates.
2. **OCR**: Detected plates are cropped and passed to EasyOCR for text extraction.
3. **Correction**: Custom rules fix common OCR errors (e.g., confusing '0' and 'O').
4. **Stabilization**: A buffer maintains recent predictions to stabilize output.
5. **Annotation**: Results are drawn on the frame and saved to the output video.

---

## 📊 Results & Performance

- **Detection Accuracy**: Depends on YOLOv8 training and dataset quality.
- **OCR Accuracy**: Improved by post-processing and stabilization.
- **Speed**: Real-time processing on modern GPUs; slower on CPU.

---

## 🛠️ Customization

- **Train YOLOv8**: Use your own dataset for better regional accuracy.
- **Extend OCR**: Add support for more languages or custom plate formats.
- **Integrate with APIs**: Connect to vehicle databases or law enforcement systems.

---

## 📖 References

- [YOLOv8 Documentation](https://docs.ultralytics.com/)
- [EasyOCR Documentation](https://www.jaided.ai/easyocr/)
- [OpenCV](https://opencv.org/)

---
