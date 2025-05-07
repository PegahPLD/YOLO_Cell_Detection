# YOLOv8 Cell Detection

This project uses the YOLOv8 object detection model (from the Ultralytics library) to detect cells in microscopy images. The workflow includes data preparation, annotation, training, and evaluation.

## Dataset

- The dataset consists of **130 annotated microscopy images**, each containing approximately **20 cells**.
- Annotations were created manually using Imagej and exported in YOLO format.
- All images are consistent in resolution and suitable for YOLOv8 input.

> ⚠️ **Current Limitation:**  
> The model performs well at detecting most cells, but **some cells in the field of view (FOV) are missed**. However, the **false positive rate is very low** — almost all predicted cells are indeed valid.

> 📈 **Improvement Needed:**  
> We need **more annotated images** to enhance the model’s generalization and recall performance.

## Model and Training

- Model: `yolov8n.pt` (Nano, ~3M parameters)
- Training:
  - `epochs=50`
  - `imgsz=640`
  - `batch=16`
  - Optimizer: AdamW (auto-tuned learning rate and momentum)
  - Platform: CPU (Torch 2.7.0, Python 3.12.4)
- Output directory: `runs/detect/train5/`

