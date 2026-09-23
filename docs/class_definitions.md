# Class Definitions and Annotation Guidelines

## 1. Purpose

This document defines the three road pavement defect classes used in the project and records the annotation principles applied during dataset preparation.

The objective is to maintain consistent class interpretation and support reproducibility of future dataset versions.

## 2. Classes

### 2.1 Pothole

**Definition:**  
A visible depression, cavity, or localized loss of pavement material within the road surface.

**Annotation guidance:**
- Annotate the visible extent of the pothole.
- Include potholes of different sizes, shapes, and deterioration levels.
- Water-filled potholes may be included when the pavement depression remains visually identifiable.
- Do not label normal pavement texture, shadows, or superficial discoloration as potholes.

---

### 2.2 Road Crack

**Definition:**  
A visible linear or interconnected fracture in the pavement surface.

**Annotation guidance:**
- Annotate clearly visible pavement cracking.
- Cracks may vary in width, direction, length, and pattern.
- Avoid labelling road markings, paving joints, kerb edges, shadows, or repaired seams as road cracks where they can be distinguished from actual pavement damage.
- Where cracking forms part of a larger pothole or severely deteriorated area, the dominant visible defect should be considered when assigning the class.

---

### 2.3 Uneven Manhole

**Definition:**  
A manhole, utility cover, or similar road-surface feature showing an apparent irregularity relative to the surrounding pavement.

**Annotation guidance:**
- Annotate covers where visible pavement conditions suggest settlement, level difference, deterioration, or irregularity around the cover.
- Include different cover shapes, materials, orientations, and viewing angles.
- Do not classify every visible manhole or utility cover as `uneven_manhole`.
- A normally aligned cover without visible evidence of irregularity should not be labelled as defective.

**Important limitation:**  
A two-dimensional image cannot reliably measure the actual vertical displacement of a manhole cover. Therefore, this class represents a visually suspected uneven condition rather than a confirmed engineering measurement.

## 3. Ambiguous Cases

Some pavement conditions may visually overlap between classes. For example:

- severe cracking may occur around a pothole;
- repaired pavement may resemble cracking;
- shadows and road markings may resemble linear cracks;
- deterioration around a utility cover may resemble a pothole.

Where the defect type is uncertain, annotation should follow the most clearly visible dominant condition. Ambiguous cases should be reviewed consistently before inclusion in future dataset versions.

## 4. Annotation Format

The initial dataset was prepared using a combination of bounding boxes, polygons, and masks during annotation.

The final experiment uses YOLOv8 for object detection. During training, Ultralytics used bounding-box information and disregarded segmentation information where mixed annotation types were encountered.

Future dataset versions should use a standardized annotation format to improve consistency.

For irregular defects such as road cracks, segmentation may also be investigated as a future alternative to rectangular object-detection bounding boxes.

## 5. Class Consistency

The class definitions should be applied consistently when:

- adding new training images;
- reviewing existing annotations;
- creating future dataset versions;
- evaluating model errors; and
- preparing additional validation or test datasets.

Consistent annotation is important because inconsistent class definitions can introduce label noise and reduce model performance.
