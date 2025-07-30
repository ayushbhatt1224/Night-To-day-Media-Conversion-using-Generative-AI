Night to Day Media Conversion using Generative AI
This repository hosts the code and resources for a deep learning project focused on transforming nighttime media (images and videos) into realistic daytime representations. Leveraging advanced Generative Adversarial Networks (GANs), specifically CycleGAN, this project enables seamless domain transfer without requiring paired night and day datasets.

Table of Contents
Introduction

Features

Technical Details

Installation

Usage

Results

Applications

Future Work

Contributing

License

Contact

Introduction
The ability to convert media captured in low-light or nighttime conditions into clear, well-lit daytime visuals has significant implications across various domains, including surveillance, autonomous driving, entertainment, and urban planning. This project addresses the challenge of unpaired image-to-image translation by employing a CycleGAN-based architecture to achieve high-quality night-to-day conversion while preserving semantic content and maintaining temporal coherence in video sequences.

Features
Unpaired Image-to-Image Translation: Utilizes CycleGAN for converting night images/frames to day, eliminating the need for perfectly matched night/day pairs.

Video Coherence: Incorporates mechanisms to ensure temporal consistency across converted video frames, minimizing flickering and maintaining smooth transitions.

Robust Architecture: Employs a robust deep learning model capable of handling diverse lighting conditions and environmental variations.

High-Quality Output: Generates realistic and visually appealing daytime representations from various nighttime inputs.

Modular Design: Code is structured for easy understanding, modification, and extension.

Technical Details
The core of this project is built upon Cycle-Consistent Generative Adversarial Networks (CycleGAN).

Generators: Two generators (G_night_to_day and G_day_to_night) are used to learn the mapping between the night and day domains.

Discriminators: Two discriminators (D_day and D_night) are employed to distinguish between real and fake images in their respective domains.

Cycle Consistency Loss: A critical component that encourages the learned mappings to be inverses of each other, ensuring that an image translated from domain A to B and back to A reconstructs the original image. This helps in training with unpaired data.

Dataset: Taken from Kaggle

Framework: Implemented using [e.g., PyTorch / TensorFlow].

Installation
Clone the repository:

Install dependencies:
pip install -r requirements.txt
Usage
Training
To train the model, ensure your dataset is organized as follows:

data/
├── trainA/ (night images)
├── trainB/ (day images)
├── testA/ (night images for testing)
└── testB/ (day images for testing)
Then, run the training script:


python train.py --dataroot ./data --name night_to_day_cyclegan --model cycle_gan
Refer to options/base_options.py and options/train_options.py for detailed training parameters.

Inference
To generate daytime images from nighttime inputs:

python test.py --dataroot ./data --name night_to_day_cyclegan --model cycle_gan --eval
Converted images will be saved in ./results/night_to_day_cyclegan/test_latest/images/.

Results
The model successfully demonstrates high-quality night-to-day conversion, producing realistic and semantically consistent daytime images and videos. Quantitative metrics such as [mention metrics if you have them, e.g., FID, LPIPS] show significant improvements over baseline methods. Qualitative analysis highlights the effectiveness in varied lighting conditions.

Applications
Surveillance & Security: Enhance visibility in low-light surveillance footage.

Autonomous Driving: Improve perception for self-driving vehicles operating at night.

Film & Entertainment: Transform nighttime scene footage to daytime for creative purposes.

Urban Planning: Analyze urban environments in different lighting conditions for better planning.

Future Work
Explore advanced attention mechanisms or transformer-based architectures for improved detail preservation.

Integrate real-time processing capabilities for live video feeds.

Expand the dataset to include more diverse environments and lighting challenges.

Investigate the use of perceptual losses for even more realistic outputs.

Contributing
Contributions are welcome! Please feel free to open issues or submit pull requests.

Contact
For any questions or collaborations, please contact "ayushbhatt1224@gmail.com".
