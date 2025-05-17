# CycleGAN_Monet
# Photo-to-Monet Style Transfer using CycleGAN

This project implements and compares two generator architectures (Generator_A and Generator_B) in a CycleGAN framework to perform **image-to-image translation** from real-world photographs to Monet-style paintings.

The goal is to explore how different architectural choices in the generator network affect image quality, training stability, and model performance.

---

## Project Overview

CycleGAN is a type of Generative Adversarial Network (GAN) designed for **unpaired image-to-image translation**. In this project:

- Generator_A is a lightweight U-Net-style model with 4 downsampling/upsampling layers.
- Generator_B is a deeper and wider version, with 8 downsampling/upsampling layers and added dropout.
- Both models are trained on paired datasets of photographs and Monet paintings using TensorFlow/Keras.
- Outputs are visually and quantitatively compared to evaluate performance.

---

## Files

- `MoMonet_DCGAN.ipynb` — Full training and evaluation notebook
- `/images_A/` — Generated Monet-style images from Generator_A
- `/images_B/` — Generated Monet-style images from Generator_B
- `/output_zips/` — Zipped image folders for submission/export

---

## Training Details

- Image size: 256×256×3
- Batch size: 1 (typical for GAN stability)
- Losses: adversarial, cycle consistency, identity loss
- Optimizer: Adam (2e-4, β1 = 0.5)
- Epochs: 25

---

## Key Findings

- Generator_B consistently produced more detailed and stylistically rich Monet images due to its greater depth and capacity.
- Increasing model complexity showed improved realism up to a point, after which diminishing returns were observed.
- Skip connections and dropout were essential for preserving spatial coherence and generalizing better.

---

## Getting Started

To run this project on your own:

1. Clone the repo
2. Open `MoMonet_DCGAN.ipynb` in Google Colab or Jupyter
3. Upload or mount datasets (`photo_tfrec` and `monet_tfrec`)
4. Train the models and generate image outputs
5. Evaluate visual quality and zip results for export

---

## Dependencies

- Python 3.8+
- TensorFlow 2.x
- NumPy
- Matplotlib
- PIL (Pillow)
- Google Colab (recommended)

---

## Sample Outputs

<p float="left">
  <img src="samples/photo.jpg" width="256"/>
  <img src="samples/monet_a.jpg" width="256"/>
  <img src="samples/monet_b.jpg" width="256"/>
</p>

---

## License

This project is open-source and free to use for educational and research purposes.

---

## Acknowledgments

- Based on CycleGAN architecture originally proposed by Zhu et al. (2017)
- Monet dataset and photo dataset adapted from the [Kaggle GAN Painting dataset](https://www.kaggle.com/datasets)

