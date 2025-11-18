# YOLO-QueryEngine
# 📦 YOLOv11 Search Engine

A Streamlit-based visual search engine powered by YOLOv11 that detects objects from images, saves metadata, and allows class-based searching with thresholds.

# 🚀 Features

1. Detect objects from a directory of images
2. Save detection metadata automatically
3. Load previously processed metadata
4. Search images by:
OR → any of selected classes
AND → all selected classes
Optional max count thresholds per class
5. Clean, simple Streamlit interface
6. Uses Ultralytics YOLO for fast inference

# 📁 Project Structure
```
yolo-search-engine/
│
├── app.py
├── requirements.txt
├── instruction.txt
├── streamlit_basics.py
│
├── src/
│   ├── inference.py
│   ├── utils.py
│   ├── config.py
│   └── __init__.py
│
├── configs/
│   └── default.yaml
│
├── processed/
└── README.md
```
# 🔧 Installation
CPU Setup
```
conda create -n yolo_image_search python=3.11 -y
conda activate yolo_image_search
pip install -r requirements.txt
```
GPU Setup
```
conda create -n yolo_image_search_gpu python=3.11 -y
conda activate yolo_image_search_gpu
conda install pytorch==2.5.1 torchvision==0.20.1 pytorch-cuda=12.4 -c pytorch -c nvidia
pip install -r requirements.txt
```
# ▶️ Run the App
```
streamlit run app.py
```
Custom port:
```
streamlit run app.py --server.port 8080
```
# ⚙️ Configuration
Modify detection settings in:
```
configs/default.yaml
```
Example:
```
model:
  conf_threshold: 0.25

data:
  image_extension:
    - .jpg
    - .jpeg
    - .png
```

# 🧠 How the App Works
# 1️⃣ Inference

YOLO detects all objects in images and outputs:

1. class
2. confidence
3. bbox
4. class count

# 2️⃣ Metadata Saving

Automatically stored at:
```
processed/<dataset_name>/metadata.json
```

# 3️⃣ Search Mode

1. OR → match any class
2. AND → must contain all selected classes
3. Optional: max count threshold per class

# 📤 Push to GitHub
```
git init
git add .
git commit -m "Initial YOLO Search Engine"
git branch -M main
git remote add origin https://github.com/<username>/<repo>.git
git push -u origin main
```

# 📝 License

MIT License
