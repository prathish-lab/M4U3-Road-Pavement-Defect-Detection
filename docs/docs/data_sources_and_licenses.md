# Data Sources and Licensing

## 1. Dataset Overview

The road pavement defect dataset used in this project was assembled from multiple image sources and curated in Roboflow for object-detection training.

The dataset contains three classes:

- `pothole`
- `road_crack`
- `uneven_manhole`

Dataset Version 1 contains 252 source images. Following preprocessing and augmentation, the exported dataset used for model training contains 656 images:

- Training: 606 images
- Validation: 50 images

Five additional road photographs were kept outside the training and validation datasets and used exclusively for unseen-image inference.

## 2. Data Sources

Images used to develop the dataset were obtained from the following sources:

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

### Additional Road Photographs

Additional road photographs were included to increase the diversity of road conditions represented in the dataset.

Five separate photographs were reserved exclusively for unseen-image inference and were not included in model training or validation.

## 3. Roboflow Dataset

The images were curated and annotated in Roboflow using the three project classes.

Roboflow Universe Version 1 serves as the annotation and dataset-versioning reference.

The exact dataset export used for model training is preserved as a frozen ZIP file (road_dataset.zip) in the project's GitHub Release (v1.0), enabling the same dataset version to be retrieved for reproducible training.

## 4. Licensing

The project dataset combines images originating from different sources. Therefore, the licensing and attribution requirements of the original image sources must be considered separately.

The Roboflow Universe dataset page identifies the published dataset version as **CC BY-NC-SA 4.0**.

This project does not claim ownership of third-party source images, and publication of the project code does not override the licensing conditions associated with the original datasets.

Before redistribution or reuse of individual images, users should review the applicable license and attribution requirements of the original source.

## 5. Project Code and Dataset Rights

Software code, notebooks, model outputs, and dataset images should be treated as separate artifacts for licensing purposes.

A software license applied to the project code does not automatically apply to third-party images contained within the dataset.

Only material for which redistribution rights are confirmed should be included in publicly distributed versions of the dataset.

## 6. Responsible Reuse

Anyone reusing this project should:

- review the original dataset licenses;
- preserve required attribution;
- comply with any non-commercial or share-alike conditions that apply;
- avoid assuming that a software license grants rights to third-party images;
- review road photographs for unnecessary personally identifiable information before redistribution.
