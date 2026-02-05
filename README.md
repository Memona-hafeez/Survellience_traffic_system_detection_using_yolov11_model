# 🚦 Surveillance Traffic System Detection using YOLOv11 Model

This project implements a **Surveillance Traffic Detection System** using the **YOLOv11 object detection model** for real-time detection and monitoring of vehicles, pedestrians, and traffic objects in video feeds or CCTV footage.

The system uses **YOLOv11 (You Only Look Once version 11)** — an advanced deep learning object detection model — to detect multiple object classes simultaneously, enabling automated traffic surveillance and analytics. :contentReference[oaicite:0]{index=0}

---

## 📌 Project Overview

With increasing vehicle numbers and urban traffic complexity, monitoring traffic in real-time is essential for improving road safety, traffic flow management, and smart city infrastructure. This project:

✔ Detects vehicles in video footage  
✔ Labels objects with bounding boxes and confidence scores  
✔ Works with webcam/CCTV/video input  
✔ Uses a pre-trained or custom-trained YOLOv11 model  
✔ Can be extended for traffic counting and analytics

---

## 🛠 Features

- 🚗 Real-time object detection using YOLOv11  
- 📹 Supports video file and camera stream input  
- 🚦 Detection of cars, buses, motorcycles, trucks, pedestrians  
- 📊 Bounding boxes with class labels and confidence  
- 🧠 Easy model training and inference  
- 🗂 Integrates with OpenCV for video processing  
- 💾 Log detections for analytics

---

## 🧠 How YOLOv11 Works

YOLOv11 is part of the YOLO family designed for **fast and accurate object detection**.  
It processes input images only once and **predicts bounding boxes and class labels in a single pass**, making it ideal for real-time surveillance applications. :contentReference[oaicite:1]{index=1}

YOLO models are efficient and can be deployed on GPUs and optimized for edge devices. :contentReference[oaicite:2]{index=2}

---

## 📁 Project Structure

```
Survellience_traffic_system_detection_using_yolov11_model/
├── data/                  # Input videos / test footage
├── models/                # YOLOv11 weights & configs
├── src/
│   ├── detect.py          # Main inference script
│   ├── train.py           # (Optional) training script
│   └── utils.py           # Helper utilities
├── requirements.txt       # Python dependencies
├── README.md              # Project documentation
```

---

## 🧪 Requirements

Install Python 3.8+ and then install dependencies:

```bash
pip install -r requirements.txt
```

Sample dependencies include:

```
ultralytics
opencv-python
numpy
torch
```

---

## ⚙️ Download YOLOv11 Model

You must download one of the YOLOv11 weights (e.g., `yolo11n.pt`, `yolo11s.pt`, etc.) and place it in the `models/` folder.

➡️ You can get official YOLOv11 models from Ultralytics repository or documentation. :contentReference[oaicite:3]{index=3}

---

## 🚀 Run Detection

To run object detection on a **video file**:

```bash
python src/detect.py \
    --source data/traffic_video.mp4 \
    --weights models/yolo11n.pt \
    --output output/
```

To run on a **live webcam stream**:

```bash
python src/detect.py \
    --source 0 \
    --weights models/yolo11n.pt
```

The script will detect and draw bounding boxes around vehicles/pedestrians in real-time.

---

## 🧠 Script Explanation

### **detect.py**

- Loads YOLOv11 model using `ultralytics` library  
- Reads video stream or webcam  
- Processes frames to detect objects  
- Draws bounding boxes + labels  
- Saves or displays output

---

## 🧠 Training (Optional)

If you have a custom dataset:

```bash
python src/train.py \
    --data data/traffic_dataset.yaml \
    --weights models/yolo11n.pt \
    --epochs 50
```

This trains YOLOv11 on your own traffic object dataset.

---

## 📊 Output

Detected objects are displayed with:

| Class        | Description              |
|--------------|--------------------------|
| Car          | Four-wheeled vehicles    |
| Bus          | Bus coaches              |
| Truck        | Heavy vehicles           |
| Motorcycle   | Bikes and scooters       |
| Pedestrian   | People walking           |

The bounding box shows confidence scores (e.g., 0.85). :contentReference[oaicite:4]{index=4}

---

## 🧠 Extensions & Improvements

✨ Add traffic counting and direction tracking  
✨ Integrate DeepSORT for consistent tracking IDs  
✨ Log detections to CSV or dashboard  
✨ Integrate with edge devices like Jetson Nano or Raspberry Pi  
✨ Add alerts for traffic violations

---

## 📝 Notes & Best Practices

✔ Use a GPU for faster inference  
✔ Use well-annotated datasets for custom training  
✔ Configure YOLOv11 input image size (e.g., 640×640) for best performance :contentReference[oaicite:5]{index=5}

---

## 🧩 Use Cases

- Smart city traffic surveillance  
- Parking lot monitoring  
- Vehicle count analytics  
- Road safety systems  
- CCTV real-time alert systems

---

## 📜 License

MIT License

---

⭐ **If you find this project useful, please give it a star!**
