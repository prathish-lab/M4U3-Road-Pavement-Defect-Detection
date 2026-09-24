# SAM Exploration Notes

## 1. Purpose

The Segment Anything Model (SAM) was explored in Roboflow as an AI-assisted annotation tool for road pavement defects.

SAM was used to support the annotation process and was not used as the final defect-detection model.

## 2. Approaches Explored

Two SAM-assisted approaches were tested.

### Direct SAM-Assisted Segmentation

SAM was used to generate masks around visible pavement defects.

This worked reasonably well when the defect had a clear boundary. However, it was less consistent for thin and irregular features, particularly `road_crack`, where the generated mask did not always follow the intended defect accurately.

### Bounding Region Followed by SAM

A second approach involved first identifying the approximate defect area and then using SAM to generate a more detailed mask within that region.

Providing the approximate location gave better control over the segmentation, although the generated masks still required visual checking and occasional manual correction.

## 3. What Helped

SAM worked better when:

- the approximate defect location was known;
- the defect had a reasonably clear boundary;
- a bounding region was used to guide SAM; and
- the generated annotation was manually reviewed.

## 4. What Did Not Work Well

The main difficulties were:

- thin and irregular road cracks;
- defects blending with surrounding pavement texture;
- ambiguous defect boundaries; and
- the need for manual correction of some generated masks.

SAM was used to assist with selecting the defect region. The final defect class (`pothole`, `road_crack`, or `uneven_manhole`) was assigned and verified separately during annotation.

## 5. Lesson Learned

SAM was useful for reducing some manual annotation effort, but human review was still necessary.

The exploration also resulted in a mixture of bounding boxes, polygons, and masks in the dataset. Since the final YOLOv8 experiment used object detection, the training workflow ultimately relied on bounding-box information.

For future work, a consistent annotation format should be used, and segmentation could be explored further for irregular defects such as road cracks.
