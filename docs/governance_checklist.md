# AECO Governance Checklist

## 1. Data Provenance

- **Source:** The training and validation dataset contains selected images from two publicly available Kaggle datasets together with road photographs taken specifically for this project.
- **Dataset Management:** Images were curated and annotated in Roboflow using three classes: `pothole`, `road_crack`, and `uneven_manhole`.
- **Version:** Roboflow Version 1.
- **Training Dataset:** The frozen dataset used for training is stored in GitHub Release `v1.0`.
- **Unseen Test Images:** Five additional road photographs taken specifically for this project were kept completely outside the training and validation datasets and used only for unseen-image inference.
- **Image Rights:** Source-specific licensing and attribution are documented separately in `data_sources_and_licenses.md`.

## 2. PII Handling (Privacy)

- **Possible PII:** Road images may incidentally contain pedestrians or vehicle registration plates.
- **Protection Strategy:** Images should be reviewed before public release, with unnecessary identifiable information cropped, removed, or blurred where required.
- **Data Minimization:** Only imagery required for pavement-defect detection and evaluation should be retained.

## 3. Risk Statement

- **False Negative:** A genuine road defect may be missed, potentially delaying inspection or maintenance.
- **False Positive:** A normal road feature may be identified as a defect, resulting in unnecessary inspection or maintenance effort.

For this application, missed defects are considered the more significant operational concern.

## 4. Human-in-the-Loop

The model is intended for preliminary road-condition screening.

Model detections should be reviewed by qualified inspection or maintenance personnel before engineering, maintenance, or safety-related decisions are made.

The model does not replace professional road inspection.

## 5. License

- The project dataset contains images from two publicly available Kaggle datasets together with original road photographs taken specifically for this project.
- The combined dataset published in Roboflow was assigned **CC BY-NC-SA 4.0** for this project.
- Images originating from the Kaggle datasets remain subject to their respective original source licenses and attribution requirements.
- The original project photographs, including the five unseen test images, are separate from the third-party Kaggle sources.
- Project code and dataset images are treated separately for licensing purposes.
- Detailed source and licensing information is provided in `data_sources_and_licenses.md`.
