# 💵 Australian Bills Object Detection using YOLOv5 | Pretrained Model Demo

This repository contains a **real-time Australian banknote (bill) object detection system** using **YOLOv5** and Computer Vision.

The project demonstrates how to **run a pretrained YOLOv5 model** to detect Australian bills using your **webcam**.
No training is required — the model is pretrained and ready to use.

[Demo Video Link (Google Drive)](https://drive.google.com/file/d/15jAMwYsDmShHRWKmkq9t5Evu0Lda0_dv/view?usp=sharing)

**Quick Metrics:**

![Quick Metrics](Screenshot%202026-01-26%20174254.png)

---

## 🚀 Features

* 🎥 Real-time webcam detection
* 🧠 Pretrained YOLOv5 model (no training required)
* 💵 Detects Australian banknotes (multiple denominations)
* ⚡ Fast and lightweight
* 🖥️ Easy setup on Windows (PowerShell)
* 🔒 Works on restricted school/student laptops (no extra apps required)

---

## 🧰 Tech Stack

* Python 🐍
* YOLOv5 (Ultralytics)
* PyTorch
* OpenCV
* NumPy

---

## 📦 Dataset

[Australian Bills Dataset on Roboflow](https://universe.roboflow.com/mathias-p/australian-bills-dont-delete)

---

## 🛠 Requirements

* Python 3.8 or newer — **recommended: Python 3.10+**
* Visual Studio Code (VS Code) — can be installed from Microsoft Store
* A webcam

---

## 🐍 Installing Python (IMPORTANT)

If you do not already have Python installed:

1. Go to this website:
   [https://www.python.org/downloads/release/python-3100/](https://www.python.org/downloads/release/python-3100/)

2. Click:
   **Windows installer (64-bit)**

3. Open the downloaded installer.

4. On the first installer screen, MAKE SURE you:

   * Tick the box: **Add Python to PATH**

5. Then click: **Install Now**

6. After it finishes installing, **close any open PowerShell or Terminal windows**.

7. Open PowerShell again:

   * Press Windows Key + X
   * Click Terminal or PowerShell

8. Check that Python works:

```
python --version
```

---

## 🚀 FULL SETUP GUIDE (STEP BY STEP)

### 🔹 Step 1 — Download the Repository

1. Go to the repository page in your browser (or your project ZIP).
2. Click the green button **Code → Download ZIP**
3. Extract that folder and keep it in the Downloads folder.

---

### 🔹 Step 2 — Open PowerShell and Go to the Project Folder

On Windows:

* Press Windows Key + X
* Click Terminal or PowerShell

Now enter this (IMPORTANT: **change the username part**):

```
cd "C:\Users\YOURUSERNAME\Downloads\Australian-Bills-Object-Detection-YOLOv5-master\Australian-Bills-Object-Detection-YOLOv5-master"
```

(Only the `"YOURUSERNAME"` needs to be changed (to your own username) — otherwise the full path should work if you keep it in Downloads. Search how to find my windows username for tutorials online.)

---

### 🔹 Step 3 — Create a Virtual Environment (Only Once)

Make sure you are inside the project folder:

```
python -m venv yolovenv
```

---

### 🔹 Step 4 — Activate the Virtual Environment

In PowerShell:

```
.\yolovenv\Scripts\Activate.ps1
```

If successful, you should see:

```
(yolovenv)
```

If PowerShell blocks activation, run:

```
Set-ExecutionPolicy -Scope CurrentUser -ExecutionPolicy RemoteSigned
```

Then try again:

```
.\yolovenv\Scripts\Activate.ps1
```

---

### 🔹 Step 5 — Install Dependencies (IMPORTANT)

Make sure you see:

```
(yolovenv)
```

First, upgrade pip inside the virtual environment:

```
python -m pip install --upgrade pip
```

Then install the requirements:

```
pip install -r requirements.txt
```

---

### 🔹 Step 6 — Run the Australian Bills Detector

Run the detector with the pretrained weights:

```
python detect.py --weights runs/train/exp/weights/best.pt --source 0 --img-size 640 --conf-thres 0.5 --device 0
```

If you **do not** have a GPU, use:

```
python detect.py --weights runs/train/exp/weights/best.pt --source 0 --img-size 640 --conf-thres 0.5 --device cpu
```

---

## 💡 Understanding Command Options

Here’s what the main options mean:

* `--conf-thres 0.5`
  Controls how confident the model must be before showing a detection.

  * 0.10 → more detections but more false positives
  * 0.25 → looser, more detections
  * 0.50 → stricter, fewer detections (recommended for money detection)

* `--device 0`
  Selects which hardware to use:

  * `0` → first GPU (if available)
  * `cpu` → force CPU
  * If no GPU is available and you don't specify `--device`, YOLO will automatically use CPU.

---

## 🎯 What This Does

* Opens your webcam
* Loads the trained YOLOv5 model
* Detects Australian bills in real time and draws bounding boxes + labels

---

## 🔁 How to Run It Again Later

1. Go to the project folder (change the username part):

```
cd "C:\Users\YOURUSERNAME\Downloads\Australian-Bills-Object-Detection-YOLOv5-master\Australian-Bills-Object-Detection-YOLOv5-master"
```

2. Activate the virtual environment:

```
.\yolovenv\Scripts\Activate.ps1
```

3. Run the detector:

```
python detect.py --weights runs/train/exp/weights/best.pt --source 0 --img-size 640 --conf-thres 0.5 --device 0
```

(Or use `--device cpu` if you have no GPU.)

---

## 🧠 Notes

* Make sure your webcam is not being used by another app.
* Press **Q** to quit the detection window.
* If detections seem noisy, try increasing `--conf-thres` to 0.6 or higher.


