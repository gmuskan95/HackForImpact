# 🧠 Real vs. AI Image Detector

This project is a web-based tool that detects whether an image is real or AI-generated using a fine-tuned CVT (Convolutional Vision Transformer) model. It combines a Python backend with a simple HTML/JS frontend.

---

## 🚀 Features

- Frontend image gallery with click-to-analyze interaction
- Flask backend with a `/serverTest` endpoint
- Pretrained CVT-13 backbone with a custom classifier
- Automatically downloads and analyzes the image
- Returns classification (`Real` or `AI Generated`) with confidence score

---

## 📁 Project Structure

```
main/
│
├── models/
│   ├── model_epoch_XX.pth       # trained model weights
│   ├── custom_dataset.py
│   ├── model.py
│   ├── aidetector.py
│   ├── inference.py
│   ├── train.py
│   └── evaluate.py
│
├── server.py                    # Flask API server
│
└── website/
    ├── index.html
    ├── content_script.js
    └── styles.css               # (optional)
```

---

## 🛠️ Setup Instructions

### 1. 📦 Install Requirements

Make sure Python 3.9+ is installed. Then run:

```bash
pip install -r requirements.txt
```

---

### 2. 🧠 Train Your Model (optional)

If you don't already have model weights:

```bash
python3 main/train.py main/models/DATASET/train --total_epochs 10 --save_path main/models
```

This will generate `.pth` files like `model_epoch_9.pth` in the `models/` folder.

---

### 3. ▶️ Start the Backend Server

Run the Flask server:

```bash
python3 main/server.py
```

It will run on:  
**`http://127.0.0.1:5000`**

---

### 4. 🌐 Launch the Frontend

Navigate to the `website/` folder and run a static file server:

```bash
cd website
python3 -m http.server
```

Then open your browser and go to:  
**`http://localhost:8000`**

---

## 📸 Usage

1. Click on an image in the gallery.
2. The image will be sent to the backend.
3. The server returns whether it's **Real** or **AI Generated**, along with the confidence level.
4. The result is logged in the console or displayed (if UI supports it).

---

## 📌 Notes

- Make sure the model file is inside `main/models/` and named something like `model_epoch_24.pth`
- The image URLs in the frontend must be accessible via full URLs (not `"images/dog.jpg"`)
- This tool is for educational purposes — AI detection is an evolving field.

---

## 👩🏻‍💻 Author

Created by Team RealSeal: **Anna Scribner**, **[Michael Gilbert](https://github.com/mjgilbert20)**, **[Muskan Gupta](https://github.com/gmuskan95)**, and **[Roger Tang](https://github.com/Roger1of1)** during NSC Hack4Impact - we won 1st prize!
