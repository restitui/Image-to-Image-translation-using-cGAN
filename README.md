🧠 Pix2Pix Image-to-Image Translation – ML Project
✨ Overview

This project implements a Pix2Pix Conditional GAN to perform image-to-image translation, converting satellite images into map-style images. The model uses paired training data, learns pixel-level relationships, and generates realistic translated outputs.

🎯 Project Objective

The goal of this project is to train a Conditional GAN (cGAN) that can take an input image (satellite view) and generate its corresponding output image (map view). Pix2Pix achieves this by combining U-Net Generator, PatchGAN Discriminator, and L1 loss for structure preservation.

🧱 Architecture
🔷 Generator (U-Net)

Takes a satellite image as input.

Uses encoder–decoder structure with skip connections.

Produces a fake translated map image.

🔷 Discriminator (PatchGAN)

Receives an (input image + output image) pair.

Judges whether the pair is real (ground truth) or fake (generated).

Outputs patch-wise real/fake predictions.

🔷 Combined GAN

Freezes Discriminator weights.

Trains Generator to fool the Discriminator while staying close to the real target using L1 loss + adversarial loss.

🗂️ Dataset & Preprocessing

Paired satellite–map images extracted from the maps dataset.

Each image is split into input (satellite) and target (map).

Images are resized to 256×256 and normalized to [-1, 1].

Converted into training tensors.

⚙️ Training Process

Generator produces fake map images for each input.

Discriminator learns to distinguish real pairs from fake pairs.

Generator updates using GAN loss + L1 loss.

Periodic visualization saves generated samples and training progress.

🛠️ Tech Stack

TensorFlow / Keras

NumPy

Matplotlib

Google Colab

Pix2Pix Architecture (U-Net + PatchGAN)

🚀 Results

The model successfully learns to translate satellite images into map-styled outputs.

Shows improvement across epochs with sharper edges and preserved structure.

Demonstrates the effectiveness of Conditional GANs for pixel-level tasks.

📌 Key Learnings

Understanding of GAN training dynamics.

Use of U-Net for reconstruction tasks.

PatchGAN for texture and local realism.

Working with paired image datasets and preprocessing pipelines.
