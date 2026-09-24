# Error Analysis and Iteration Plan

## 1. Purpose

This analysis reviews representative successes and failures from the YOLOv8 road pavement defect detection model. The objective is to identify where the model performs reliably, where errors occur, and how the dataset and model could be improved in future iterations.

The validation results achieved an overall precision of 0.511, recall of 0.434, mAP@50 of 0.438, and mAP@50–95 of 0.207. Class-level evaluation showed that `uneven_manhole` performed strongest, while `road_crack` remained the most challenging class.

## 2. Representative Successful Detections

### Success 01 – Uneven Manhole
The model correctly identified an `uneven_manhole` with approximately 0.89 confidence. The object was clearly visible and the predicted bounding box closely localized the annotated defect.

Evidence: `results/success_01.jpg`

### Success 02 – Pothole
A relatively small and distant pothole was correctly detected with approximately 0.69 confidence. This demonstrates that the model can identify some defects even when they occupy a relatively small area of the road image.

Evidence: `results/success_02.jpg`

### Success 03 – Road Crack
The model detected visible road-crack regions with confidence values of approximately 0.43 and 0.33. Although the confidence was lower than the stronger pothole and uneven-manhole examples, the road cracks were detected, but at lower confidence than the pothole and uneven-manhole examples.

Evidence: `results/success_03.jpg`

## 3. Representative Failure Cases

### Failure 01 – Missed Road Crack
A road crack present in the ground-truth annotation was not detected by the model. This represents a false negative and is consistent with the relatively low recall observed for the `road_crack` class.

Evidence: `results/failure_01.jpg`

### Failure 02 – Class Confusion
A ground-truth pothole was predicted as `road_crack` with approximately 0.35 confidence. This indicates class confusion where irregular pavement deterioration can share visual characteristics with more than one defect category.

Evidence: `results/failure_02.jpg`

### Failure 03 – Multiple Missed Potholes
Multiple potholes visible in the ground-truth annotations were not detected. The defects appear relatively small and distant within a wider road scene, indicating that object scale, viewing distance, lighting, and scene complexity can affect detection performance.

Evidence: `results/failure_03.jpg`

## 4. Key Error Patterns

The evidence indicates three recurring limitations:

1. **Missed defects (false negatives):** Some genuine defects are not detected, particularly road cracks and small or distant objects.
2. **Class confusion:** Irregular pavement damage may be classified as the wrong defect type when visual characteristics overlap.
3. **Background similarity:** Features such as road markings, pavement joints, repaired surfaces, kerbs and shadows can visually resemble road cracks and may contribute to incorrect detections.

## 5. Iteration Plan

Future model development should focus on the following data improvements:

1. **Increase road-crack diversity:** Add examples covering different crack widths, orientations, pavement textures, lighting conditions, viewing distances, and deterioration levels. Include hard-negative examples such as road markings, paving joints, kerbs, shadows, and repaired seams.

2. **Expand challenging pothole examples:** Include water-filled potholes, irregular boundaries, partial occlusion, surrounding cracking, different depths, and defects captured at different distances and camera angles.

3. **Improve uneven-manhole diversity:** Include circular and rectangular covers, drainage grates, different materials, partial visibility, viewing angles, surrounding pavement repairs, and examples of correctly aligned covers as negative samples.

## 6. Annotation Limitation

The dataset was annotated using a mixture of bounding boxes, polygons and masks.

During YOLOv8 object-detection training, Ultralytics identified the mixed annotation types and used the bounding-box information while disregarding segmentation information.

For future development, the annotation format should be standardized. Segmentation could also be explored for irregular defects such as road cracks.

## 7. Environmental and Camera Limitations

The current model was trained mainly using road images captured under normal daytime conditions. Its performance has not been sufficiently tested under challenging environmental conditions such as:

- night-time or very low-light conditions;
- rain or wet pavement;
- strong sunlight, glare, and reflections;
- heavy or uneven shadows across the road surface;
- poor visibility or motion blur from a moving camera.

These conditions may change the visual appearance of potholes, cracks and manhole covers and could affect detection accuracy.

Future dataset versions should include more images from different lighting, weather and camera conditions before the model is considered for wider field use.

## 8. Conclusion

The model successfully detected examples from all three defect classes, but the results also show several missed detections and class-confusion cases.

`road_crack` remains the most challenging class and should be the main focus of future dataset improvement.

The model is therefore suitable for preliminary screening and experimentation, with human verification required before maintenance or safety decisions.
