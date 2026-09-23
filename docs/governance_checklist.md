# Governance Checklist

## 1. Data Provenance

- The project dataset was assembled from selected publicly available road-damage images together with original road photographs captured by the project author.
- Images were curated and annotated in Roboflow using three classes: `pothole`, `road_crack`, and `uneven_manhole`.
- Roboflow Version 1 is retained as the annotation and dataset-versioning reference.
- The frozen dataset used for model training is stored in the project's GitHub Release to support reproducibility.
- Five additional road photographs were kept outside the training and validation datasets and used exclusively for unseen-image inference.
- Source-specific dataset licensing and attribution are documented separately.

## 2. Privacy and PII Handling

Road imagery may incidentally capture pedestrians, vehicle registration plates, buildings, or other identifiable information.

Before images are publicly released, they should be reviewed for unnecessary personally identifiable information (PII). Where appropriate, identifiable information should be removed, cropped, or blurred.

The project follows a data-minimization approach by retaining only imagery required for pavement-defect detection and model evaluation.

## 3. Model Limitations

The model is an educational prototype and should not be treated as an autonomous road-inspection system.

Performance can be affected by:

- lighting and shadows;
- water on the pavement;
- road markings and paving joints;
- repaired or patched surfaces;
- camera angle and viewing distance;
- small or partially visible defects;
- variations in pavement texture.

The `road_crack` class currently demonstrates the weakest detection performance and requires additional training data and hard-negative examples.

## 4. Risk Statement

### False Negatives

A false negative occurs when a genuine road defect is not detected.

This presents the more significant operational risk because a potentially hazardous pavement defect could remain unidentified and maintenance intervention could be delayed.

### False Positives

A false positive occurs when the model identifies a defect where no relevant defect exists.

False positives may result in unnecessary inspection effort or maintenance resources being directed toward non-defective locations.

Both error types therefore require human review.

## 5. Human-in-the-Loop

The model is intended to support, rather than replace, professional road inspection.

Model detections should be reviewed by qualified inspection or maintenance personnel, particularly when:

- confidence is low;
- the defect may affect road safety;
- the visual condition is ambiguous;
- the model output conflicts with field observations.

Final maintenance prioritization and engineering decisions remain the responsibility of qualified personnel.

## 6. Uneven Manhole Interpretation

A two-dimensional road image may help identify a suspected manhole or utility-cover irregularity. However, image-based object detection alone cannot reliably quantify the vertical displacement or settlement of the cover relative to the surrounding pavement.

Where level differences are safety-critical, field verification or complementary measurement methods should be used.

## 7. Annotation Governance

The dataset contains annotations originally created using a mixture of bounding boxes, polygons, and masks.

For the YOLOv8 object-detection experiment, bounding-box information was used while segmentation information was disregarded where mixed annotation types were encountered.

Future dataset versions should standardize the annotation method and apply consistent class-definition rules.

## 8. Licensing and Responsible Use

The dataset includes material originating from multiple sources. Original source licenses and attribution requirements must therefore be respected.

The project's code license does not automatically replace or override the licenses applicable to third-party images or datasets.

Only images for which redistribution rights are confirmed should be included in publicly accessible repository or dataset releases.

## 9. Intended Use

Appropriate use:
- road-condition screening;
- identification of locations requiring further inspection;
- educational computer-vision experimentation;
- support for maintenance-planning workflows.

Not intended for:
- autonomous safety decisions;
- automatic maintenance authorization without verification;
- definitive measurement of defect severity or depth;
- replacement of engineering inspection.
