# Insect Classifiers: 2D-to-3D
By Dev Mehrotra and Lauren Glynn


[Insect Classifer Slides](https://uwprod-my.sharepoint.com/:p:/g/personal/leglynn_wisc_edu/EbHMKGl8CTVBulvhWcyrYJQBgjP4ENtP7L4bLouSrN66mw?e=yl6cD7)

## Motivation and Significance

> Challenges with traditional 2D representations of insects (viewing angles, occlusions)
>
> Need for enhanced understanding in entomology, biodiversity research, and pest management
>
> Aiding in pest management strategy development

Insect models are helpful in overcoming viewing angle variations and self-occlusions, which is a common issue in 2D images.  Embracing 3D representation offers a solution to these limitations.  Entomology, along with other fields that have been slower to adopt advanced technologies, stands to gain significant benefits from embracing the active support of these 3D models. The active support of these 3D models will drive advancements in understanding biodiversity and refining pest management strategies, benefiting both entomological research and practical applications in insect control. More broadly, 3D models provide a more comprehensive and realistic representation of insects, which can benefit various applications such as scientific visualization, education, and creative expression [1]. 

## Methodology

> Previous approaches, such as HoloDiffusion, have employed diffusion models trained on 2D images but may struggle to capture fine textures and details accurately.
> 
> Other methods, like DreamCraft3D, use hierarchical 3D generation to improve texture quality but can be computationally expensive.

Our Approach: Dream Gaussian Framework

1.  Directly optimizes a Gaussian model from 2D images

2.  Starts with a Gaussian distribution and optimizes its parameters directly from the input 2D images

3.  Convert 3D Gaussians into textured meshes

4.  Apply a fine tuning stage to further refine the details

#### How DreamGaussian Differs from other Approaches

| Approach        | DreamGaussian        | Holodiffusion | DreamCraft 3D |
|:-------------|:------------------|:------|:----------|
| Input          |  Directly optimizes from 2D images| Pre-trained on 2D images  |   Initializes a NeRF model with random weights         | 
| 3D Generation | Renders views from different angles   | Employs diffusion models  | Hierarchial 3D generation approach           |
| Optimization           | Score distillation loss guides optimization| Trains diffusion models on 2D data   | Bootstrapped Score Distillation Loss           |
| Texture Quality           | Captures fine-grained details effectively | May struggle with intricate features  | Aims for improved texture quality           ||
| Computational Complexity           | More efficient | The slowest of all 3  | High computational complexity           ||

## Demos of Approach

![wcrw_500-ezgif com-video-to-gif-converter](https://github.com/dashingzombie/insectclassifiers/assets/110515153/2eefab8d-fbca-4264-96e4-3066d5379c88)

![diptera_99](https://github.com/dashingzombie/insectclassifiers/assets/110515153/85444a46-4e2d-4025-a85c-29bf082a16e7)

![neuroptera_49](https://github.com/dashingzombie/insectclassifiers/assets/110515153/77564c4c-ca6b-489e-afcc-a830c29f6ab3)

## Quantitative Results

We ran a Clip Similarity Score where we render 8 different images from different angles for 100 samples and then evaluated with the preprocessed image

![DreamGaussianResults](https://github.com/dashingzombie/insectclassifiers/assets/110515153/9b2f8bb5-0c56-4338-894f-7555f667573a)

## Discussion

>Data Dependency:

The accuracy heavily relies on the quality of the dataset. The Clip Similarity Score serves as a metric indicating the alignment between predicted and ground truth segments. The values of the Clip Similiarity Score indicate there is room for improvement as an average of 54 percent for this sample. Enhancing the dataset with a larger volume of high-quality images is essential. Presently, the framework's preprocessing methods have shown inconsistencies in effectively removing backgrounds entirely, likely impacting its performance.

Addressing these issues through dataset augmentation and refined preprocessing techniques can contribute to significant enhancements in accuracy and overall performance.
 
>Processing Time:

The current implementation is computationally intensive, necessitating exploration of alternative models. One promising option is Plenoxel, a view-dependent sparse voxel model.  Plenoxels rely on a a simple and explicit volumetric representation that can be optimized from calibrated images via gradient methods and regularization without any neural components [2].
 
>Anatomy Complexity:

Capturing the intricate and fine texture of insect anatomy poses a significant challenge for the model due to the complexity of the data. To address this challenge effectively, it's important to gain a deeper understanding of how the framework handles more complex data structures. By comprehensively understanding the framework's capabilities and limitations in processing intricate details, we can develop approaches to create better datasets tailored to the specific nuances of insect anatomy.

### References

1.	X. Zhang, Y. Gao and T. Caelli. (2010). Primitive-based 3D structure inference from a single 2D image for insect modeling: Towards an electronic field guide for insect identification. In Proceedings of the 2010 11th International Conference on Control Automation Robotics & Vision (pp. 866-871). Singapore. doi: 10.1109/ICARCV.2010.5707814

2.	Yu, A., Fridovich-Keil, S., Tancik, M., Chen, Q., Recht, B., & Kanazawa, A. (2021). Plenoxels: Radiance Fields without Neural Networks. arXiv preprint arXiv:2112.05131.
