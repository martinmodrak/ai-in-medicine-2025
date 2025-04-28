---
title: "Lesson 6 - Task materials"
output: 
  html_document:
    number_sections: true
---


# Download data for lesson

- Download everything from http://195.113.43.46:3388/lesson6/
  - File sources (for access from outside): 
    - QuPath: for Windows: https://github.com/qupath/qupath/releases/download/v0.6.0-rc4/QuPath-v0.6.0-rc4-Windows.zip
      - For other systems see https://github.com/qupath/qupath/releases/tag/v0.6.0-rc4 
    - Ki67 Slide 1: https://openslide.cs.cmu.edu/download/openslide-testdata/Hamamatsu/OS-2.ndpi
    - Ki67 Slide 2 (small): https://molecular.pathology.ufl.edu/2017/06/05/ki67-ihc-single-stain-on-human-tumor-slide/
- Save to a temporary folder (e.g. on Desktop)

# Unpack and run QuPath

- If asked to create a user directory, allow it (with default settings)

# Analyzing first Ki-67 image

Will be done together with everybody

We are mostly following the tutorial at:  https://qupath.readthedocs.io/en/0.5/docs/tutorials/cell_detection.html

- Open file "OS-2.tif" in QuPath
  - File -> Open, choose the file
  - Under "Set image type" Select "Brightfield H-DAB" 
- Check Image (left pane) -> Pixel width
  - Should be 0.2271μm (both width and height)
- View -> Brightness + Contrast
  - Inspect channels/stains
  - We'll now work with the full image ("Original")
- Draw a small-ish rectangle ("R" key  or the rectangle icon on the main toolbar) - we want ~100-1000 cells in it
- Analyze -> Cell detection -> Positive cell detection
  - Run with default settings
  - Use the 'D' key to show/hide annotations
  - Re-run positive cell detection with "Detection image"  = "Optical Density sum"
  - Note: when deleting annotations, you want to choose "No" when asked if to "Keep descendant objects"
- Tuning other parameters
  - Background radius (larger = allow larger nuclei)
  - Cell expansion (how much space around nucleus is considered part of the cell)
  - Threshold 1 (how much DAB stain is required to classify as positive)
- Once we are happy with detection settings, analyze a larger region (should be the "hotspot" of the cancer)
  - Note: when deleting annotations (rectangles), you will be asked if you want to "Keep descendant objects", you want to say "No" (so that annotated cells are deleted with rectangles)
- You can see the percent positive in the left pane, Annotations, bottom part


# Analyze a Ki-67 image on your own

- Try the same set of steps for the file `Ki67_2.jpg`   
- You'll need to set the pixel size (both with and height) to 0.67μm under "Image" in the left pane


# Test the InstanSeg automatic segmenter on Ki-67

- InstanSeg is described at https://arxiv.org/pdf/2408.15954
- Install InstanSeg
  - Open "Extensions -> Manage Extensions"
    - Find "QuPath InstanSeg extension v0.1.0-rc1", click the green plus sign to install
  - Open "Extensions -> Deep Java Library -> Manage DJL Engines"
    - Under "PyToch", click "Check/Download", once downloaded close the window
  - You should now see "InstanSeg" under "Extensions"
    - If you don't, then restart QuPath (save your changes)
- Try InstanSeg
  - Make a rectangle annotation overlapping your previous detections and select it
  - Open "Extensions -> InstanSeg -> Run InstanSeg"
    - Allow checking for updates
    - Click the directory icon near "Choose directory to store models". 
      - Choose the directory where you have your other data
    - Select "brightfield-nuclei" under "Select a model"
    - Make sure you have the correct rectangle selected (in yellow color)
    - Click "Run"
  - Compare the annotations to the nuclei annotations made manually
    - In the left pane, under "Annotations" and "Class list" you can hide some annotations --- 
      by default the new annotations from InstanSeg will be marked as "None" while the annotations
      done manually are classified as "Positive" or "Negative"
        - Note that the default InstanSeg model only selects nuclei.
- Classify InstanSeg cells as Ki-67 positive
  - Delete manually annotated rectangles+
  - Choose "Classify -> Object Classification -> Set Cell Intensity Classification"
  - Select "DAB: Mean" as the "Measurement", pick a suitable threshold.
  

