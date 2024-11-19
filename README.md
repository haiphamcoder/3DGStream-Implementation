# 🌟 3DGStream Implementation

## 📖 Introduction

This repository contains the implementation of the method described in the paper **"3DGStream: On-the-Fly Training of 3D Gaussians for Efficient Streaming of Photo-Realistic Free-Viewpoint Videos"** by Jiakai Sun et al., published at CVPR 2024.

The method focuses on real-time training and rendering of Free-Viewpoint Videos (FVVs) using 3D Gaussians for dynamic scenes. It achieves:

- ⚡ Fast per-frame training (~12 seconds per frame).
- 🖥️ Real-time rendering (200 FPS at megapixel resolution).
- 📊 Competitive performance in image quality and model storage.

For more details, please refer to the [official paper](https://openaccess.thecvf.com/content/CVPR2024/papers/Sun_3DGStream_On-the-Fly_Training_of_3D_Gaussians_for_Efficient_Streaming_of_CVPR_2024_paper.pdf).

## 🛠️ Installation

### 📋 Requirements

- Python 3.8+
- CUDA-enabled GPU
- PyTorch 1.11+
- tiny-cuda-nn
- Additional libraries: NumPy, OpenCV, Matplotlib

### 🚀 Steps

1. Clone this repository:

   ```bash
   git clone https://github.com/haiphamcoder/3DGStream-Implementation.git
   cd 3DGStream-Implementation
   ```

2. Install dependencies:

   ```bash
   pip install -r requirements.txt
   ```

3. Set up environment variables if needed.

## 🎮 Usage

### 📂 Preparing Input Data

- Prepare multi-view video datasets with synchronized camera poses.
- Ensure data is in the format specified in the `data/` folder.

### 🔧 Running the Training Pipeline

1. Train initial 3D Gaussians for the first frame:

   ```bash
   python train_initial_frame.py --data_path ./data --output_path ./output
   ```

2. Train for subsequent frames:

   ```bash
   python train_on_fly.py --data_path ./data --output_path ./output
   ```

3. Real-time rendering:

   ```bash
   python render_real_time.py --model_path ./output --frame_index 50
   ```

## 📂 Project Structure

- data/: 📁 Contains input datasets (multi-view videos and camera poses).
- models/: 📂 Contains the implementation of the 3DGStream pipeline.
- output/: 📤 Stores trained 3D Gaussians and rendered outputs.
- utils/: 🛠️ Utility scripts for data preprocessing, evaluation, and visualization.
- train_initial_frame.py: 🔄 Script for initializing the 3D Gaussians for the first frame.
- train_on_fly.py: 📡 Script for training the model on-the-fly.
- render_real_time.py: 🎥 Script for rendering real-time outputs.

## 📚 Citation

If you use this repository, please cite the original paper:

```bibtex
@inproceedings{sun2024_3dgstream,
  title={3DGStream: On-the-Fly Training of 3D Gaussians for Efficient Streaming of Photo-Realistic Free-Viewpoint Videos},
  author={Jiakai Sun, Han Jiao, Guangyuan Li, Zhanjie Zhang, Lei Zhao, Wei Xing},
  booktitle={CVPR},
  year={2024}
}
```

## 🤝 Contributing

Contributions are welcome! Please open an issue or submit a pull request.

## ⚖️ License

This project is licensed under the MIT License. See the `LICENSE` file for details.
