---
layout: default
---

Text can be **bold**, _italic_, or ~~strikethrough~~.

[Link to another page](./another-page.html).

There should be whitespace between paragraphs. We recommend including a README, or a file with information about your project.

# Insect Classifiers
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
Your methodology (method, data, evaluation metrics). If applicable, highlight how it differs from prior work (new experiments, new methods, etc)

> Previous approaches, such as HoloDiffusion, have employed diffusion models trained on 2D images but may struggle to capture fine textures and details accurately.
> 
> Other methods, like DreamCraft3D, use hierarchical 3D generation to improve texture quality but can be computationally expensive.

#### Discussion + quantitative results
Discussion of quantitative results

*   This is an unordered list following a header.
*   This is an unordered list following a header.
*   This is an unordered list following a header.

*   ![Octocat](https://github.githubassets.com/images/icons/emoji/octocat.png)

##### Demos of Approach
Our Approach: Dream Gaussian Framework

1.  Directly optimizes a Gaussian model from 2D images

2.  Starts with a Gaussian distribution and optimizes its parameters directly from the input 2D images

3.  Convert 3D Gaussians into textured meshes

4.  Apply a fine tuning stage to further refine the details

![Diptera](https://github.com/dashingzombie/insectclassifiers/blob/main/gifs/diptera_99.gif)

![Neuroptera](https://github.com/dashingzombie/insectclassifiers/blob/main/gifs/neuroptera_49.gif)


###### Header 6

| Approach        | DreamGaussian        | Holodiffusion | DreamCraft 3D |
|:-------------|:------------------|:------|:----------|
| Input          |  Directly optimizes from 2D images| Pre-trained on 2D images  |   Initializes a NeRF model with random weights         | 
| 3D Generation | Renders views from different angles   | Employs diffusion models  | Hierarchial 3D generation approach           |
| Optimization           | Score distillation loss guides optimization| Trains diffusion models on 2D data   | Bootstrapped Score Distillation Loss           |
| Texture Quality           | Captures fine-grained details effectively | May struggle with intricate features  | Aims for improved texture quality           ||
| Computational Complexity           | More efficient | The slowest of all 3  | High computational complexity           ||


### There's a horizontal rule below this.

* * *

### Here is an unordered list:

*   Item foo
*   Item bar
*   Item baz
*   Item zip

### And an ordered list:

1.  Item one
1.  Item two
1.  Item three
1.  Item four

### And a nested list:

- level 1 item
  - level 2 item
  - level 2 item
    - level 3 item
    - level 3 item
- level 1 item
  - level 2 item
  - level 2 item
  - level 2 item
- level 1 item
  - level 2 item
  - level 2 item
- level 1 item

### Small image

![Octocat](https://github.githubassets.com/images/icons/emoji/octocat.png)

### Large image

![Branching](https://guides.github.com/activities/hello-world/branching.png)


### Definition lists can be used with HTML syntax.

<dl>
<dt>Name</dt>
<dd>Godzilla</dd>
<dt>Born</dt>
<dd>1952</dd>
<dt>Birthplace</dt>
<dd>Japan</dd>
<dt>Color</dt>
<dd>Green</dd>
</dl>

```
Long, single-line code blocks should not wrap. They should horizontally scroll if they are too long. This line should be long enough to demonstrate this.
```

```
The final element.
```
