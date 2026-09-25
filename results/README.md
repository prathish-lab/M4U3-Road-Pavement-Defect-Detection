# Results Evidence

This folder contains the main evidence generated during training, validation and error analysis of the YOLOv8 road-pavement defect model.

## Training Results

- `results.png` — YOLOv8 training and validation curves.
- `confusion_matrix_normalized.png` — normalized confusion matrix showing class-level performance.

## Annotation Examples

Three examples from the annotated dataset are included:

- `annotation_pothole.jpg`
- `annotation_road_crack.jpg`
- `annotation_uneven_manhole.jpg`

These demonstrate the annotation approach for each of the three defect classes.

## Validation Evidence

YOLO-generated validation batches are provided as paired ground-truth labels and model predictions:

- `val_batch0_labels.jpg` — ground-truth annotations.
- `val_batch0_pred.jpg` — corresponding model predictions.
- `val_batch1_labels.jpg` — ground-truth annotations.
- `val_batch1_pred.jpg` — corresponding model predictions.

Together, these provide prediction evidence across more than 10 validation images.

## Success and Failure Examples

Three successful detections and three selected failure cases are provided:

- `success_01.jpg` to `success_03.jpg`
- `failure_01.jpg` to `failure_03.jpg`

Detailed interpretation of the failure cases and proposed improvements is provided in [`../docs/error_analysis.md`](../docs/error_analysis.md).
