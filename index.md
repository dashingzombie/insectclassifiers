# Insect Classifiers: 2D-to-3D
By Dev Mehrota and Lauren Glynn 

[Insect Classifer Slides]([./https://github.com/dashingzombie/insectclassifiers])

[Link to github repository]([./https://github.com/dashingzombie/insectclassifiers])

## Motivation and Significance

> Challenges with traditional 2D representations of insects (viewing angles, occlusions)
>
> Need for enhanced understanding in entomology, biodiversity research, and pest management
>
> Aiding in pest management strategy development

Insect models are helpful in overcoming viewing angle variations and self-occlusions, which is a common issue in 2D images.  Embracing 3D representation offers a solution to these limitations.  Entomology, along with other fields that have been slower to adopt advanced technologies, stands to gain significant benefits from embracing the active support of these 3D models. The active support of these 3D models will drive advancements in understanding biodiversity and refining pest management strategies, benefiting both entomological research and practical applications in insect control. More broadly, 3D models provide a more comprehensive and realistic representation of insects, which can benefit various applications such as scientific visualization, education, and creative expression [6]. 

### Methodology

> Previous approaches, such as HoloDiffusion, have employed diffusion models trained on 2D images but may struggle to capture fine textures and details accurately.
> 
> Other methods, like DreamCraft3D, use hierarchical 3D generation to improve texture quality but can be computationally expensive.

Our Approach: Dream Gaussian Framework

1.  Directly optimizes a Gaussian model from 2D images

2.  Starts with a Gaussian distribution and optimizes its parameters directly from the input 2D images

3.  Convert 3D Gaussians into textured meshes

4.  Apply a fine tuning stage to further refine the details

##### How DreamGaussian Differs from other Approaches

| Approach        | DreamGaussian        | Holodiffusion | DreamCraft 3D |
|:-------------|:------------------|:------|:----------|
| Input          |  Directly optimizes from 2D images| Pre-trained on 2D images  |   Initializes a NeRF model with random weights         | 
| 3D Generation | Renders views from different angles   | Employs diffusion models  | Hierarchial 3D generation approach           |
| Optimization           | Score distillation loss guides optimization| Trains diffusion models on 2D data   | Bootstrapped Score Distillation Loss           |
| Texture Quality           | Captures fine-grained details effectively | May struggle with intricate features  | Aims for improved texture quality           ||
| Computational Complexity           | More efficient | The slowest of all 3  | High computational complexity           ||

##### Demos of Approach


![image](https://github.com/dashingzombie/insectclassifiers/assets/53788170/4bf582e8-a947-4a23-8046-997fae47544e)


![Diptera](https://github.com/dashingzombie/insectclassifiers/blob/main/gifs/diptera_99.gif)

![Neuroptera](https://github.com/dashingzombie/insectclassifiers/blob/main/gifs/neuroptera_49.gif)

#### Quantitative Results

We ran Clip Similarity Score where we render 8 different images from different angles for 100 samples and then evaluated with the preprocessed image

*   ![Results](https://github.com/dashingzombie/insectclassifiers/blob/main/data/DreamGaussianResults.png)

#### Discussion

Data Dependency: Accuracy depends on dataset quality.
Processing Time: Current implementation is computationally intensive.
Environmental Sensitivity: Models may struggle with extreme conditions.
Anatomy Complexity: Complex structures pose challenges.
