# Landuse Segmentation

## About The Project

This repository is a research framework for advanced semantic segmentation of land use from satellite imagery. The project aims to implement, compare, and explore various deep learning architectures, starting from the classic U-Net to modern hybrid models involving Vision Transformers (ViT) and enhancement techniques like Super-Resolution.

The primary dataset used for development is the [DeepGlobe Land Cover Classification Dataset](https://www.kaggle.com/datasets/balraj98/deepglobe-land-cover-classification-dataset).

### Core Goals

-   Implement a classic **U-Net** as a performance baseline.
-   Build a hybrid **ViT-UNet** architecture as described in the research papers.
-   Explore the impact of **Super-Resolution (SR)** as a pre-processing step and through advanced methods like Feature Fusion and Multi-Task Learning.
-   Maintain a modular, configuration-driven codebase for easy experimentation.

---

## Project Structure

```
Landuse-Segmentation/
├── configs/
│   ├── 01_unet_baseline.yaml
│   └── 02_vit_unet.yaml
├── data/
│   └── .gitkeep
├── scripts/
│   └── train.py
├── land_use_seg/
│   ├── data_loader/
│   │   └── deepglobe_dataset.py
│   ├── models/
│   │   ├── unet.py
│   │   └── vit_unet.py
│   ├── engine/
│   │   └── trainer.py
│   └── utils/
│       └── utils.py
├── .gitignore
├── README.md
└── requirements.txt
```

---

## Getting Started

Follow these steps to set up the project environment.

### Prerequisites

-   Python 3.8+
-   Git

### Installation

1.  **Clone the repository**
    ```sh
    git clone https://github.com/minhnion/Landuse-Segementaition.git
    cd Landuse-Segmentation
    ```

2.  **Create and activate a virtual environment** (recommended)
    ```sh
    python -m venv venv
    source venv/bin/activate  # On Windows: venv\Scripts\activate
    ```

3.  **Install the required packages**
    ```sh
    pip install -r requirements.txt
    ```

4.  **Download the dataset**
    -   Download the data from [Kaggle: DeepGlobe Land Cover Classification](https://www.kaggle.com/datasets/balraj98/deepglobe-land-cover-classification-dataset).
    -   Unzip the contents into the `data/` directory. The final path to the training images should look like this: `data/deepglobe-land-cover-classification-dataset/train/`.

---

## Usage

All experiments are controlled via configuration files located in the `configs/` directory.

To run an experiment, use the `train.py` script and specify the path to your desired config file.

1.  **Run the U-Net Baseline Experiment**
    ```sh
    python scripts/train.py --config configs/01_unet_baseline.yaml
    ```

2.  **Run the ViT-UNet Experiment**
    ```sh
    python scripts/train.py --config configs/02_vit_unet.yaml
    ```

---

## Roadmap

-   [ ] Implement U-Net model.
-   [ ] Implement ViT-UNet model.
-   [ ] Implement ESRT model for Super-Resolution.
-   [ ] Implement Feature Fusion experiment.
-   [ ] Implement Multi-Task Learning experiment.
-   [ ] Explore Foundation Models for segmentation.

---

## License

Distributed under the MIT License. See `LICENSE` for more information. 

## Acknowledgments

*   [U-Net Paper](https://arxiv.org/abs/1505.04597)
*   [Vision Transformer (ViT) Paper](https://arxiv.org/abs/2010.11929)
*   [DeepGlobe Dataset](https://www.kaggle.com/datasets/balraj98/deepglobe-land-cover-classification-dataset)
