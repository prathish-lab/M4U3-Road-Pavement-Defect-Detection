# Class Definitions and Annotation Guidelines

## 1. Purpose

This document defines the three road pavement defect classes used in the project and records the main annotation guidelines followed during dataset preparation.

## 2. Classes

### 2.1 Pothole

**Definition:**  
A visible depression, cavity, or localized loss of pavement material within the road surface.

**Annotation guidance:**
- Annotate the visible extent of the pothole.
- Include potholes of different sizes, shapes, and deterioration levels.
- Water-filled potholes may be included when the pavement depression remains visually identifiable.
- Do not label normal pavement texture, shadows, or superficial discoloration as potholes.

### 2.2 Road Crack

**Definition:**  
A visible linear or interconnected fracture in the pavement surface.

**Annotation guidance:**
- Annotate clearly visible pavement cracking.
- Cracks may vary in width, direction, length, and pattern.
- Avoid labelling road markings, paving joints, kerb edges, shadows, or repaired seams as road cracks where they can be distinguished from actual pavement damage.
- Where multiple defect types are visible in the same area, each clearly identifiable defect may be annotated according to its appropriate class.

### 2.3 Uneven Manhole

**Definition:**  
A manhole, utility cover, or similar road-surface feature showing an apparent irregularity relative to the surrounding pavement, including visibly sunken, raised, displaced, damaged, or open manhole conditions.

**Annotation guidance:**
- Annotate covers where the visible condition suggests settlement, level difference, deterioration, or irregularity around the cover.
- Include different cover shapes, materials, orientations, and viewing angles.
- Do not classify every visible manhole or utility cover as `uneven_manhole`.
- A normally aligned cover without visible evidence of irregularity should not be labelled as defective.
- Open or uncovered manholes may also be included within the uneven_manhole class for this prototype.

**Limitation:**  
A two-dimensional image cannot reliably measure the actual vertical displacement of a manhole cover. Therefore, this class represents a visually suspected uneven condition rather than a confirmed engineering measurement.

uneven_manhole groups several visually different manhole-related hazards into one class. In a future dataset with sufficient images, open_manhole could be separated as an independent class.

## 3. Ambiguous Cases

Some conditions can visually overlap between classes. For example, repaired pavement or shadows may resemble cracks, while deterioration around a utility cover may resemble a pothole.

Ambiguous images should be reviewed carefully and the same class definitions should be applied consistently throughout the dataset.

## 4. Annotation Format

The dataset was initially annotated using a mixture of bounding boxes, polygons, and masks.

For the YOLOv8 object-detection experiment, Ultralytics used bounding-box information and disregarded segmentation information where mixed annotation types were encountered.

Future dataset versions should use a standardized annotation format. Segmentation could also be explored for irregular defects such as road cracks.
