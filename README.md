# GTSeg Dataset

GTSeg is a dataset for geometric texture segmentation on 2D renderings and 3D meshes. It is designed to support research on recognizing and segmenting repeated geometric patterns from multi-view curvature renderings and projecting the segmentation results onto 3D surfaces.

The dataset contains three parts:

1. **DTSet**: a collection of geometric heightmap textures.
2. **GTSeg**: a multi-view image dataset for training geometric texture segmentation models.
3. **3D Benchmark**: a benchmark of annotated synthetic and real-world 3D models.

## Dataset Overview

| Subset | Description | Size |
|---|---|---:|
| DTSet | Heightmap textures generated from DTD images | 354 heightmaps |
| GTSeg | Paired curvature images and instance masks rendered from textured 3D models | 11,200 image pairs |
| 3D Benchmark | Face-level instance annotations for synthetic and real models | 30 models |

## 1. DTSet

DTSet contains **354 heightmap textures** generated from images in the [Describable Textures Dataset (DTD)](https://www.robots.ox.ac.uk/~vgg/data/dtd/).

We use **Chord** to convert the original texture images into heightmaps. These heightmaps describe geometric displacement rather than surface color and can therefore be applied to 3D meshes to synthesize geometric texture regions.

DTSet contains a diverse range of repetitive and structured patterns, providing source textures for the construction of our synthetic training and benchmark data.

## 2. GTSeg Image Dataset

The GTSeg image dataset is constructed from **80 base meshes selected from Thingi10K**. For each base mesh, we generate ten textured variants by applying randomly selected DTSet heightmaps to different surface regions.

Each textured model is rendered from **14 viewpoints**. For every viewpoint, the dataset provides:

- A grayscale curvature rendering;
- An instance segmentation mask;
- The correspondence between the rendered view and its source 3D model.

All views rendered from the same 3D model are assigned to the same data split to prevent data leakage.

The curvature images serve as model inputs, while the masks provide instance-level supervision for geometric texture segmentation.

## 3. 3D Instance Segmentation Benchmark

The 3D benchmark contains **30 annotated models** for evaluating class-agnostic geometric texture instance segmentation directly on mesh surfaces.

It consists of:

- **20 synthetic models**, generated using the same geometric texture synthesis procedure as the training data;
- **10 real-world models**, manually annotated at the mesh-face level.

The 3D models and texture maps used in the benchmark do not overlap with those used for training or validation.


## Data Sources

This dataset is constructed using data derived from:

- [Describable Textures Dataset (DTD)](https://www.robots.ox.ac.uk/~vgg/data/dtd/);
- [Thingi10K](https://ten-thousand-models.appspot.com/).

Users should also follow the licenses and terms of use of the original datasets when using the corresponding derived data.

## Open-Source Plan

| Component | Contents | Status |
|---|---|---|
| DTSet | 354 geometric heightmap textures | **Coming soon** |
| GTSeg | Curvature renderings and instance masks for training and validation | **Coming soon** |
| 3D Benchmark | 20 synthetic and 10 manually annotated real-world models | **Coming soon** |

## Citation

```bibtex

```
