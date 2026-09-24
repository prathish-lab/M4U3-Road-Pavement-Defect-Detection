# SAM Exploration Notes

## 1. Purpose

The Segment Anything Model (SAM) was explored during dataset preparation in Roboflow to assess whether AI-assisted segmentation could reduce the manual effort required to annotate road pavement defects.

SAM was used as an annotation-support tool rather than as the final defect-detection model.

## 2. Approaches Explored

Two SAM-assisted annotation approaches were explored during dataset preparation.

### 2.1 Direct SAM-Assisted Segmentation

SAM was used to assist in identifying the boundary of visible pavement defects and generating segmentation masks.

This approach was useful for defects with relatively clear and distinguishable boundaries. However, the results were less consistent for thin and irregular features, particularly `road_crack`.

Road cracks often have narrow, discontinuous, or irregular shapes and may visually blend with pavement texture, repaired surfaces, joints, shadows, and other linear features. In these situations, the generated mask did not always follow the intended defect region accurately.

Manual review and adjustment were therefore required.

### 2.2 Bounding Region Followed by SAM Mask Generation

A second approach involved first identifying the approximate defect location using a bounding region and then using SAM assistance to generate a more detailed mask within the selected area.

Providing the approximate object location gave greater control over the region that SAM was expected to segment.

This approach was useful for generating more detailed boundaries around some defects, although the resulting masks still required visual verification and occasional manual correction.

## 3. Class Assignment

SAM was used primarily to assist with segmentation of the selected image region.

The defect classes used in this project:

- `pothole`
- `road_crack`
- `uneven_manhole`

were assigned and verified during the annotation process.

Therefore, difficulties encountered during SAM exploration are described as segmentation or boundary-selection issues rather than SAM incorrectly classifying the pavement defect.

## 4. What Helped

SAM was most useful when:

- the approximate location of the defect was already known;
- the defect had a reasonably distinguishable boundary;
- a bounding region was provided to guide the segmentation process; and
- the generated mask was subsequently reviewed by the annotator.

The experiment demonstrated that AI-assisted annotation can reduce some of the manual effort required to create detailed object boundaries.

## 5. What Did Not Work Well

The main limitations observed during the exploration were:

- difficulty following thin and irregular road cracks;
- difficulty separating some defects from surrounding pavement textures;
- inconsistent boundaries for visually ambiguous pavement deterioration;
- the need for manual review and correction of generated masks.

Road cracks were particularly challenging because their geometry is often irregular and does not always form a clearly separated object within the image.

## 6. Lesson Learned

The SAM exploration demonstrated that AI-assisted annotation can support and accelerate parts of the dataset-labelling process, but it does not eliminate the need for human quality control.

For this project, SAM was therefore treated as an annotation-assistance tool rather than an autonomous annotation method.

The exploration also contributed to the dataset containing a mixture of bounding boxes, polygons, and masks. Since the final experiment used YOLOv8 for object detection, the training workflow ultimately relied on bounding-box information rather than segmentation masks.

A future iteration could standardize the annotation format and investigate segmentation models for irregular defects such as road cracks.
