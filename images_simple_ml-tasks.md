---
title: "Lesson 7 - Task materials"
output: 
  html_document:
    number_sections: true
---


# Download data for lesson

- Download everything from http://195.113.43.46:3388/
  - This includes materials from previous lesson (folder `lesson6`) and a new histology slide (under `lesson7`).
  - File sources (for access from outside): 
    - Same as previous lesson:
      - QuPath: for Windows: https://github.com/qupath/qupath/releases/download/v0.6.0-rc4/QuPath-v0.6.0-rc4-Windows.zip
        - For other systems see https://github.com/qupath/qupath/releases/tag/v0.6.0-rc4 
      - Ki67 Slide 1: https://openslide.cs.cmu.edu/download/openslide-testdata/Hamamatsu/OS-2.ndpi
    - New for this lesson:
      - Lung cancer samples stained for MAGEA4 https://www.ebi.ac.uk/biostudies/files/S-BIAD453/MAGEA4/MAGEA4_(CAB040535)_25000_BOMI2_slide1.svs
- Save to a temporary folder (e.g. on Desktop)

# Unpack and run QuPath

# Train a classifier together

Following https://qupath.readthedocs.io/en/0.5/docs/tutorials/cell_classification.html

- Open  "OS-2.tif" in QuPath
  - File -> Open, choose the file
  - Under "Set image type" Select "Brightfield H-DAB" 
- Detect cells 
  - This is the same as we did in [the tasks for previous lesson](images_simple-tasks.html), but we don't need "Positive cell detection" and "Cell detection" alone
  is enough (using "Poistive cell detection" will also work, but will be a bit more messy to work look at). 
- Manually inspect cell information
  - Measure -> show measurements maps
    - Nucleus/cell area ratio (filter!)
    - Lower the maximum value (lower slider) to better highlight
  - But those measurements itself are not enough
- Add information about neighbourhood
  - Analyze -> Calculate features -> Add smoothed features (keep the default 25μm radius)
- Annotate regions as tumor/stroma
  - The Brush tool ![brush tool](https://qupath.readthedocs.io/en/0.5/_images/BRUSH_TOOL.png) is probably the best
  - Right-click region -> Set classification -> Tumour OR Stroma
- Classify -> Object classification -> Train object classifier
  - Live update
  - If you see incorrect classifications, add annotations to improve training
- Optional: classify tumor cells as positive/negative
  - Classify ‣ Object classification ‣ Set cell intensity classifications.
  - Choose "DAB OD mean" for "Measurement"

# Final task (for credit)

**Important:** Start with creating a new project. This will let you send the results needed to get credit.

Evaluating the presence of cancer-testis antigens in multiple tissue samples. The original study is at https://europepmc.org/article/MED/37341056#mol213474-sec-0007 (for interest only, not needed for the task)

- Import file `MAGEA4_(CAB040535)_25000_BOMI2_slide1.svs` into the QuPath project (drag onto the window or File -> Open). 

- There are many samples in the same file, we will focus on the top-left cores (the first 4 in the first row).

- Run cell detection for a couple areas. The default settings will tend to detect too many cells due to the relatively low resolution of the image. You will want to increase smoothing via "Median filter radius" and "Sigma" options. 
You may also need to change the "Background radius" setting to allow for larger cells.
  - If you have it working from previous lesson, you can also try InstanSeg and see if it is sufficient

- Once you are happy with the result, store (e.g. screenshot, or just write down) your final cell detection parameters!

- Train a classifier to distinguish between the two cell populations shown below - you can use Tumor/Stroma classes (or add your own in the Annotations card in the left pane and the "..." button below the class list).

![](populations-final-task.png)

- Once the classifier works good on one sample, detect cells at another sample (with the same detection method and settings!)
  - If you used "Analyze -> Calculate features -> Add smooth features" previously, you need to rerun it for the new region
  - Does it work well also here?
  - If not, add annotations on the new sample
  - Once it works nice on both sample, try on yet another samples. 
    - This is kind of cross validation

- Save the classifier
  - In the "Train object classifier" window, enter "classifier name" at the bottom and click "Save"

To get credit at the lesson, show your results to lecturer. Outside of the class, send: your cell detection parameters (screenshot is fine) and the classifier file (found under `your-project-directory\classifiers\object_classifiers`) to martin.modrak@lfmotol.cuni.cz

<!-- 
Note to self: evaluate on 
Slide 1: 
   - Top 4, Left - 2
   - Bottom - 3, LEft-
Slide 2:
  - Left 4, Top - 2
  - Top 1, Right - 4 ( - 3without spaces)
  - Bottom -3, Left - 5 (-3 without spaces)
-->

# Bonus tasks

Detect cell on whole patches and calculate positive/negative-ly stained proportion in each cell-type.

Find other populations to classify in different types of samples.


