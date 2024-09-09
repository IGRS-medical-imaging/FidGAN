<h1 align="center">FidGAN: A Fiducial Prediction Based GAN for Image Guided Spine Surgery</h1>

<p  align="center">  
  
Precise localization and detection of fiducials is crucial for the registration process in Image-Guided Spine Surgery (IGSS), particularly when combined with Minimally Invasive Surgery (MIS), to accurately guide and position surgical tools relative to the patient’s anatomy. In IGSS, the calibration drum fiducials help to register the C-Arm images with the patient's space. However, due to inherent drawbacks in the imaging modality, it becomes challenging for computational algorithms to detect all fiducials. Registration with lesser fiducials results in a reduction of accurate registration between the patient and the imaging space, it reduces the precision of the IGSS. We propose a novel FidGAN approach that modifies and tailors the Generative Adversive Network (GAN) algorithm specifically for fiducials prediction in the C-Arm fluoroscopic imaging modalities employed in IGSS.The proposed FidGAN comprises novel contributions such as the additional skip connection in U-Net architecture, use of style loss in the generator, customized patch sizes, and random noise in the discriminator, all of which make it possible to predict the missing fiducials with an average Root Mean Square Error (RMSE) of 0.638 mm, between the predicted fiducials in the images and the corresponding fiducials in real space this will improve the accuracy of registration process and increases the precision of the IGSS. 
</p>

<h3 > <i>Index Terms</i> </h3> 

 :diamond_shape_with_a_dot_inside:Image Guided Surgery
  :diamond_shape_with_a_dot_inside:Fiducials Prediction
  :diamond_shape_with_a_dot_inside:GAN
  :diamond_shape_with_a_dot_inside:Deep Learning    
  :diamond_shape_with_a_dot_inside:Calibration
  :diamond_shape_with_a_dot_inside:C-Arm Fluoroscopy

</div>


## <div align="center">Getting Started</div>

<details>
  <summary><i>Proposed  Framework</i></summary>



- **Architecture:**:FidGAN adopts an `altered U-Net` like structure, effective for image generation and transformation tasks.

- **Encoder-Decoder:**:</ln> The proposed U-Net architecture is tailored for generating images from occluded fiducial point input images. FidGAN employs segmentation tasks in the generator by modified U-Net architecture with additional skip connections in the encoder. In this setup, the output from the first layer generated feature maps, down-sampled to [1, 64, 128, 128], is linked to the third layer. This means the third layer receives input from both the first layer’s down-sampled output and the second layer’s output. This modification enhances the extraction of detailed features like edges and textures from the input image. The calibration drum fiducials, sized 4 mm and 5 mm, are distributed across two plates. This setup helps differentiate between fiducials of different sizes, ensuring they do not overlap in the generated image.

- **Input and Output**: Takes an input image with `occluded fiducials` and outputs a reconstructed image with `predicted fiducials`.
<br/>

</details>
<details open>
<summary><i>Training Objectives</i></summary>

  
- **Adversarial Loss**: Discriminator and generator are optimized using adversarial loss to ensure the generated images resemble real images.
  
- **Ground Truth Loss**: Promotes pixel-wise similarity between generated and real images, is also known as L1 Loss
  
- **Style Loss**:Encourages the generator to facilitates the production of images that closely resemble
the target images.VGG19 helps to calculate style loss by extracting features from both the ground truth and generated images through its convolutional layers. These features are transformed into Gram matrices by dot products between all pairs of flattened feature vectors from the features, these features capture the textures and patterns of the images. The style loss is computed as the mean squared error between the Gram matrices of the two images, measuring how well the generated image matches the textures and circular arrangement of fiducials in the ground truth image.
  
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
  <img src="Images/d25.drawio (1).png">
</p>
<div align = "center">
  
  :small_orange_diamond: Fig 1:Detection of Missing Fiducials
</div>
</details>

## <div align="center">Methodology</div>

<p align="center">
  <img src="Images/b1.drawio (1).png">
</p>
<div align = "center">
  
  :small_orange_diamond: Fig 2:Block diagram of FidGAN Training
</div>


## <div align="center">Pre-requisites</div>
Before installing and running the project, ensure you have the following prerequisites:

 :grey_exclamation: Download and install Jupyter Notebook from the `Jupyter website`.
 
 :wavy_dash: The version for this project is **Jupyter Notebook 6.0.3**.
 
 :grey_exclamation: Pix2Pix

:wavy_dash: `Pix2Pix` is required for the project.

To includethe above repository in your project, follow these steps:

1. Download from the official [ML GANs GitHub repository](https://github.com/aladdinpersson/Machine-Learning-Collection/tree/master/ML/Pytorch/GANs/Pix2Pix):

    ```bash
    git clone https://github.com/aladdinpersson/Machine-Learning-Collection/tree/master/ML/Pytorch/GANs/Pix2Pix
    cd Machine-Learning-Collection/ML/Pytorch/GANs/Pix2Pix
    
    ```

2. Extract the contents to a directory on your system if you downloaded a compressed file. If you cloned the repository, you can skip this step.

3. Include the directory in your project's include path. 

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
