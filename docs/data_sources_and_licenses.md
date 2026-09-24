# Data Sources and Licensing

## 1. Dataset Overview

The road pavement defect dataset used in this project was assembled from multiple image sources and curated in Roboflow for object-detection training.

The dataset contains three classes:

- `pothole`
- `road_crack`
- `uneven_manhole`

Dataset Version 1 contains 252 source images. Following preprocessing and augmentation, the exported dataset contains 656 images:

- Training: 606 images
- Validation: 50 images

Five additional road photographs taken specifically for this project were kept completely outside the training and validation datasets and used only for unseen-image inference.

## 2. Data Sources

Images used to develop the dataset came from three sources.

### Kaggle Source 1

**Potholes, Cracks and Openmanholes (Road Hazards)**

Source:
https://www.kaggle.com/datasets/sabidrahman/pothole-cracks-and-openmanhole

Selected images from this dataset were incorporated into the project dataset.

### Kaggle Source 2

**Road Damage Dataset: Potholes, Cracks and Manholes**

Source:
https://www.kaggle.com/datasets/lorenzoarcioni/road-damage-dataset-potholes-cracks-and-manholes

Selected images from this dataset were incorporated into the project dataset.

### Original Project Photographs

Additional road photographs taken specifically for this project were included to increase the diversity of road conditions represented in the dataset.

Five separate photographs taken specifically for this project were reserved exclusively for unseen-image inference and were not included in training or validation.

## 3. Roboflow Dataset

The images were curated and annotated in Roboflow using the three project classes.

Roboflow Universe Version 1 serves as the annotation and dataset-versioning reference.

The exact dataset export used for model training is preserved as `road_dataset.zip` in GitHub Release `v1.0` to support reproducibility.

## 4. Licensing

The project dataset combines images from different sources. The original licensing and attribution requirements of the source images therefore need to be considered separately.

The combined dataset published in Roboflow was assigned **CC BY-NC-SA 4.0** for this project.

Images originating from the two Kaggle datasets remain subject to their respective original source licenses and attribution requirements. Original project photographs are separate from these third-party sources.

The project does not claim ownership of third-party source images, and the project code license does not override the licensing conditions of the original datasets.

## 5. Project Code and Dataset Rights

Project code and third-party dataset images are treated separately for licensing purposes.

A software license applied to the project code does not automatically apply to images originating from third-party datasets.

Detailed licensing information should therefore be checked at the original dataset source before reuse or redistribution.

## 6. Responsible Reuse

Anyone reusing this project should:

- review the original dataset licenses;
- preserve required attribution;
- comply with applicable non-commercial or share-alike conditions;
- distinguish project code from third-party dataset rights; and
- review road photographs for unnecessary personally identifiable information before redistribution.
:::
