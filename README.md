<h1 align="center">FidGAN: A Fiducial Prediction Based GAN for Image Guided Spine Surgery</h1>

<p  align="center">  
  
Accurately localizing and detecting fiducials is critical for image-guided spine surgery (IGSS) to precisely guide surgical tools relative to the patient’s anatomy. However, challenges such as imaging modality limitations or occlusions can hinder fiducial detection, compromising instrument positioning accuracy. In this study, we propose FidGAN, a novel approach tailored for predicting undetected fiducials in C-Arm fluoroscopic images used in IGSS. FidGAN incorporates unique features like additional layer connections, style loss in the generator, customized patch sizes, and random noise to enhance fiducial prediction. Experimental results highlight FidGAN's effectiveness in predicting missing fiducials, demonstrating superior prediction accuracy.
</p>

<h3 > <i>Index Terms</i> </h3> 

 :diamond_shape_with_a_dot_inside:Image Guided Surgery
  :diamond_shape_with_a_dot_inside:Fiducials Prediction
  :diamond_shape_with_a_dot_inside:GAN
  :diamond_shape_with_a_dot_inside:Deep Learning
  

</div>


## <div align="center">Getting Started</div>

<details>
  <summary><i>Proposed  Framework</i></summary>



- **Architecture:**:FidGAN adopts an `altered U-Net` like structure, effective for image generation and transformation tasks.

- **Encoder-Decoder:**:</ln> The proposed U-Net architecture is tailored for generating images from occluded
fiducial point input images. Incorporates feature extraction connections, or skip connections, within the encoder, where features from the first layer, downsampled to [1, 64, 128, 128], to enhancing the extraction of detailed features like edges and textures. Edges are crucial for delineating the boundaries of fiducial points, outlining specific
points, while textures help distinguish between different fiducials based on the calibration drum plates.

- **Input and Output**: Takes an input image with `occluded fiducials` and outputs a reconstructed image with `predicted fiducials`.
<br/>

</details>
<details open>
<summary><i>Training Objectives</i></summary>

  
- **Adversarial Loss**: Discriminator and generator are optimized using adversarial loss to ensure the generated images resemble real images.
  
- **L1 Loss**: Promotes pixel-wise similarity between generated and real images
  
- **Style Loss**:Encourages the generator to facilitates the production of images that closely resemble
the target images.VGG19 helps ensure that the fiducial points in the generated image are arranged in a circular format, similar to the ground truth without occlusion. By extracting high-level perceptual features from both the ground truth image and the generated image.
  
- **Optimization**: Adam optimizer adjusts parameters to minimize losses and enhance image quality.
  </details>
  
  <details open>
<summary><i>Dataset and Preprocessing</i></summary>


- **Dataset Preparation**: The calibration fiducial markers in the dataset were obtained using
X-ray images. We began with images that included all required fiducials. This was achieved by randomly eliminating certain fiducials from each original image and then merging these altered images with the originals.
  
- **Image Generation:** Synthetic images are created by randomly occluding fiducials from original images, simulating real-world occlusion scenarios.


</details>

<details open>
<summary><i>Evaluation Metrics</i></summary>

  
- **Performance Comparison**:FidGAN is compared with other GAN variants (CycleGAN, StarGAN, DCGAN) using metrics like PSNR, SSIM, MSE, MAE, and GTCE(Groundtruth Calbration Error).
  
- **Accuracy**: Achieves lower GTCE and higher PSNR, SSIM compared to other GANs, indicating superior fidelity in predicting fiducials.
  
  <p align="center">
  <img src="Figures/Image 2.jpg">
</p>
<div align = "center">
  
  :small_orange_diamond: Fig 4:Detection of Missing Fiducials
</div>
</details>

## <div align="center">Methodology</div>

<p align="center">
  <img src="Figures/Fidcan Diagram.drawio_page-0001.jpg">
</p>
<div align = "center">
  
  :small_orange_diamond: Fig 4:Block diagram of FidGAN Training
</div>

## <div align="center">Pre-requisites</div>
Before installing and running the project, ensure you have the following prerequisites:

 :grey_exclamation: Download and install Jupyter Notebook from the `Jupyter website`.
 
 :wavy_dash: The version for this project is **Jupyter Notebook 6.0.3**.

## <div align="center">Installation</div>
:arrow_right:Clone the Repository
```bash
git clone https://github.com/Deepa-Ramki/FidGAN.git
```

:arrow_right:Navigate to the Project Directory
```bash
cd FidGAN
```
:arrow_right:Install Dependencies
```bash
pip install -r requirements.txt
```
## <div align="center">Environments</div>
<div align="center">
 <a href="https://jupyter.org/">
    <img src="https://jupyter.org/assets/homepage/main-logo.svg" width="10%" alt="Jupyter Notebook" /></a>
  </a>
</div>
