# Cell Instance Segmentation

## Introduction
### Problem Statement
Neurological disorders, including neurodegenerative diseases such as Alzheimer's and various forms of brain tumors, stand as a significant challenge in global health, leading to substantial mortality and disability worldwide. A crucial aspect of managing and understanding these disorders involves monitoring how they respond to treatment. Currently, one of the primary methods for this monitoring is through the analysis of neuronal cells using light microscopy. This approach is both accessible and non-invasive, offering a window into the cellular level changes brought about by these diseases and their treatments.

However, a significant challenge in this process is the segmentation of individual neuronal cells in microscopic images. Neuronal cells, particularly neuroblastoma cell lines like SH-SY5Y, are notoriously difficult to segment accurately due to their unique, irregular, and concave morphology. This difficulty is compounded by the time-intensive nature of manual segmentation, which limits the speed and scale at which data can be analyzed.

![Cell Segmentation Example]([https://github.com/user/repo/blob/main/image.png](https://github.com/rohit-sahoo/Cell_Instance_Segmentation/blob/main/segmentation.png) "Cell Segmentation")



### Project Objective
The objective of this project is to develop an advanced instance segmentation model specifically tailored for neuronal cells. By leveraging the capabilities of computer vision, we aim to accurately segment individual neuronal cells in phase contrast microscopy images. This task holds particular importance due to the unique challenges posed by the morphology of neuronal cells, which have traditionally resulted in lower precision scores in segmentation tasks.

Our goal is to create a model that not only performs with high accuracy but also contributes significantly to neurobiological research. By automating and improving the segmentation process, we can facilitate the collection of robust quantitative data. This data is crucial for researchers to measure the effects of diseases and treatment conditions on neuronal cells more effectively.

## Dataset Description

The dataset provided for this project plays a crucial role in the development and validation of our cell instance segmentation model. Below is a detailed description of the dataset components:

### File Formats and Content
- **Images**: All images are provided in PNG format.
- **Annotations**: Annotations for the training set are provided in run-length encoded masks, a format that efficiently represents the segmented neuronal cells.

### Training Set
- The training dataset consists of a modest number of images, but each image contains a high number of annotated neuronal cells. This rich annotation is key to developing a precise segmentation model.

### Test Set
- The hidden test set comprises approximately 240 images. These images are used to evaluate the performance of the segmentation model in unseen conditions.

### Files and Metadata
1. **train.csv**: This file contains IDs and masks for all objects in the training set.
   - `id`: Unique identifier for each object.
   - `annotation`: Run-length encoded pixels for the identified neuronal cell.
   - `width`: Width of the source image.
   - `height`: Height of the source image.
   - `cell_type`: The cell line type.
   - `plate_time`: Time when the plate was created.
   - `sample_date`: Date when the sample was created.
   - `sample_id`: Identifier for the sample.
   - `elapsed_timedelta`: Time elapsed since the first image was taken of the sample.

2. **train**: Directory containing the training images in PNG format.
3. **test**: Directory containing the test images in PNG format.

The combination of detailed annotations and high-quality images in this dataset provides a robust foundation for developing an effective instance segmentation model for neuronal cells.


## Models:

### 1. Mask R-CNN:

In this project, I have developed a Mask R-CNN model focused on the challenging task of cell instance segmentation. This model is adept at handling the intricate and unique morphology of neuronal cells. My implementation of the Mask R-CNN is specifically tailored to enhance precision in segmenting individual cells, a crucial aspect in neurobiological research. Despite the inherent complexities in the dataset, the model achieved an Intersection over Union (IoU) score of 0.280. This metric reflects the model's capability to accurately segment cells, and it signifies a substantial step forward in automating cell segmentation for neurological disorder studies.

### 2. U-Net

1. **U-Net Training Notebook:**

In this notebook, I have detailed the training process of the U-Net model. The U-Net architecture is particularly suited for the nuanced task of cell segmentation due to its ability to capture fine details through a series of convolutional and pooling layers. The training notebook covers the steps taken to optimize the model, fine-tune its parameters, and prepare it for effective segmentation performance.

2. **U-Net Inference Notebook:**

This notebook is centered around the U-Net model, specifically tailored for the inference phase in the segmentation task. U-Net, known for its efficacy in medical image segmentation, is applied here to identify and delineate neuronal cells. The focus of this notebook is on applying the trained U-Net model to unseen data, demonstrating its capability in accurately segmenting cells in complex images.

### 3. Detectron2

1. **Detectron2 Training Notebook:**

The training notebook outlines the process of training the Detectron2 model. The notebook highlights the strengths of Detectron2, particularly its ability to handle complex image segmentation tasks with high efficiency. Key features of the training process, including data visualization and model optimization, are covered in this notebook. The Visualizer class in Detectron2 is utilized for insightful visualizations of the training dataset, including masks and bounding boxes.

2. **Detectron2 Inference Notebook:**

This notebook is dedicated to the application of the Detectron2 model in the inference stage. Detectron2 is a powerful and versatile framework for object detection and segmentation tasks. The focus of this notebook is on deploying the trained Detectron2 model to perform segmentation on new, unseen data, showcasing its effectiveness in accurately identifying and delineating neuronal cells.

