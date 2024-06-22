<h1 align="center">.......</h1>

<p  align="center">  
  
 Precise viewing of the calibrator with `17 fiducial markers` is crucial in image-guided spine surgery (IGSS) for accurate tool guidance. However, C-arm x-ray imaging often obstructs these markers, complicating the procedure. Incorrect depiction can lead to mispositioning of instruments, increasing surgical risks and complications. This research introduces `FidGAN`, a Generative Adversarial Network (GAN) designed to detect occluded fiducials. FidGAN can accurately identify and fill in missing fiducials in images. Studies show that FidGAN effectively correlates missing fiducials with `high accuracy`. The synthetic images created by FidGAN, which include all fiducials, prove useful in real-world applications, enhancing segmentation tasks.
</p>

<h3 > <i>Index Terms</i> </h3> 

 :diamond_shape_with_a_dot_inside:....
  :diamond_shape_with_a_dot_inside: ....
  :diamond_shape_with_a_dot_inside:....

</div>


## <div align="center">Getting Started</div>

<details>
  <summary><i>Proposed  Framework</i></summary>



- **Architecture:**:FidGAN adopts an `altered U-Net` like structure, effective for image generation and transformation tasks.

- **Encoder-Decoder:**:</ln> It includes downsampling and upsampling pathways with skip connections to preserve spatial details and high-level features.

- **Input and Output**: Takes an input image with `occluded fiducials` and outputs a reconstructed image with `predicted fiducials`.
<br/>

</details>
<details open>
<summary><i>Training Objectives</i></summary>

  
- **Adversarial Loss**: Discriminator and generator are optimized using adversarial loss to ensure the generated images resemble real images.
  
- **L1 Loss**: Promotes pixel-wise similarity between generated and real images
  
- **Style Loss**:Encourages the generator to replicate textures and styles from the target image.
  
- **Optimization**: Adam optimizer adjusts parameters to minimize losses and enhance image quality.
  </details>
  
  <details open>
<summary><i>Dataset and Preprocessing</i></summary>


- **Dataset Preparation**: Utilizes Minimum-Size Elliptical Region (MSER) technique to extract fiducial coordinates and generate a diverse dataset.
  
- **Image Generation:** Synthetic images are created by randomly occluding fiducials from original images, simulating real-world occlusion scenarios.


</details>

<details open>
<summary><i>Evaluation Metrics</i></summary>

  
- **Performance Comparison**:FidGAN is compared with other GAN variants (CycleGAN, StarGAN, DCGAN) using metrics like PSNR, SSIM, MSE, MAE, and Root Mean Squared Error (RMSE).
  
- **Accuracy**: Achieves lower RMSE and higher PSNR, SSIM compared to other GANs, indicating superior fidelity in predicting fiducials.
  
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
