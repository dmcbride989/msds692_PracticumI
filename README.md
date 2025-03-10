# 🚔 License Plate Detection for Police Chase Analysis  
**Automating vehicle identification in police chase footage**  

## 📌 Project Overview  
Law enforcement agencies rely on dashcam footage to analyze police chases and determine the involvement of multiple vehicles. However, manually reviewing footage is **time-consuming, prone to human error, and inefficient**, leading to investigation delays.  

### **Business Question:**  
🔍 *How can license plate detection help determine the involvement of multiple vehicles in police chases?*  

### **Objectives:**  
✅ Automate **license plate detection** from police dashcam footage  
✅ Identify **direct and indirect vehicle involvement** in chases  
✅ Accelerate **investigations** by reducing manual review time and increasing accuracy  

---

## 🏗️ Project Scope  
This project implements a **computer vision system** to automatically detect and read **license plates** from dashcam footage. The system performs the following steps:  
1️⃣ **Extract video frames** from dashcam footage  
2️⃣ **Detect vehicles and license plates** using **YOLO (You Only Look Once)-based object detection**  
3️⃣ **Apply OCR (Optical Character Recognition)** to extract license plate numbers  
4️⃣ **Log and visualize results** to assist officers in reviewing and validating findings  

---

## 📊 Data Collection Strategy  
To build a robust model, a custom dataset was collected across various real-world scenarios:  

| **Scenario**            | **Details**  |  
|--------------------------|----------------------------------------------------|  
| 🚗 **Parking Lot**       | Stationary vehicles, clear plates                 |  
| 🏡 **Neighborhood**      | Slow traffic, stop signs                          |  
| 🚦 **Intersections**     | Vehicles in close proximity                       |  
| 🛣️ **Rush Hour Highway** | Dense traffic patterns                            |  
| 🚀 **High-Speed (70mph)**| Motion blur challenges                            |  

📽️ **Data Stats:**  
- Captured **images every 5th frame**  
- **12:16 minutes** of footage → **4,326 frames** at **1920x1080** resolution  

---

## 🏎️ Model Optimization Approach  
To balance **speed, accuracy, and model size**, different YOLO models were tested:  

| **Model**   | **Speed (FPS)** | **Size (MB)** | **Accuracy** | **Best Use** |  
|------------|---------------|------------|------------|--------------------|  
| YOLOv8n    | Fastest       | ~6MB       | Lower      | Edge devices       |  
| YOLOv8s    | Fast          | ~20MB      | Better     | General detection  |  
| YOLOv8m    | Slower        | ~48MB      | Highest    | Small object detection |  

🖼️ **Training Data:** 4,360 labeled images  

---

## 📉 Model Results & Challenges  
### 🔴 Issues Encountered:  
- **False Positives**: Vehicles misclassified as license plates  
- **Bounding Box Size**: Large bounding boxes reducing precision  
- **Low Confidence Scores**: Some detections had **confidence below 0.8**  

### ✅ Mitigation Strategies:  
✔️ **Increased confidence threshold** to filter weak detections  
✔️ **Refined labeling** by tightening bounding boxes  
✔️ **Adjusted IoU threshold** to improve detection precision  

---

## 🔧 Next Steps  
🚀 **Practicum II Enhancements:**  
1️⃣ **Validation** – Review automatic labeling results  
2️⃣ **Model Retraining** – Fine-tune YOLO for improved accuracy  
3️⃣ **OCR Integration** – Implement text recognition for plates  
4️⃣ **Performance Tuning** – Optimize hyperparameters  

---

## 🛠️ Tech Stack  
- **Python**, OpenCV, TensorFlow/PyTorch  
- **YOLO (You Only Look Once) Object Detection**  
- **OCR (Tesseract/ EasyOCR)**  
- **Pandas, NumPy, Matplotlib**  

---

## 🚀 How to Run the Project  
1️⃣ **Clone the Repository:**  
```bash
git clone https://github.com/yourusername/license-plate-detection.git
cd license-plate-detection
