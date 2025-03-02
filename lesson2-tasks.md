---
title: "Lesson 2 - Task materials"
output: 
  html_document:
    number_sections: true
---


# Fitting and overfitting

We will use the demo app at https://codepen.io/oscarsaharoy/full/eYggrme

The app tries to fit a function to data points you entered.

You may:

- Click on empty space to add a point
- Click on a point to remove a point
- Drag points to change their position
- Change the type of fit (we will focus on linear/polynomial)


## When line is not enough

- Start with the default "linear" fit and default dataset. 
- Add/move a couple points, until you think the data is not well fit with a line.
- Switch to "polynomial" fit (keep the default order of the polynomial)
- Has the fit improved?
- Try moving a single point around. Where do you need to place the point to affect the overall fit the most?

## Find polynomial order

Paste the following in the "points" text area:

```
-0.250, 0.700
0.400, 2.00
3.00, 0.100
0.800, 0.800
-2.88, 3.33
-2.67, 2.58
-2.51, 1.80
-2.00, -0.760
-1.43, -1.23
-0.560, -0.145
-0.830, -0.535
-0.635, 0.545
-0.515, -0.745
-1.16, -0.730
-2.16, 0.650
-1.91, 1.13
-2.57, 0.785
-2.73, 1.37
-0.110, 1.14
0.265, 1.19
0.265, 1.52
0.955, 1.50
1.38, 1.52
1.84, 0.560
1.93, 0.980
2.64, -0.0400
3.21, -0.355
3.43, 0.185
3.88, -0.310
2.62, 0.740
3.36, -0.940
4.00, -1.15
1.71, 1.52
0.655, 1.13
0.865, 1.97
1.14, 2.43
1.57, 1.95
1.65, 2.57
2.16, 2.57
2.19, 2.12
-1.43, -0.325
-1.79, -0.385
-1.28, 0.380
-1.65, 0.650
3.07, 1.64
3.42, 1.17
3.55, 0.740
-3.12, 1.86
-3.44, 2.93
```

Switch to "polynomial" fit and change the order of the polynomial. Which order looks like the best generalization?
Why?

## Manual "cross-validation"

Paste the following as "points":

```
0.318, 1.85
0.800, 0.800
2.97, -0.377
1.92, -0.128
-7.14, -2.74
-6.24, -1.96
-4.25, 1.19
-1.87, 2.30
3.67, 0.881
```

- Overall idea: you can remove one point by clicking on it, see how that affects the fit and the click again to put the point back at (almost) the same place
- Try a polynomial fit of order 3
  - Which of the points produces the biggest change in fit when removed?
- Now do the same for polynomial or order 2 and then for order 1 (linear)
  - Which of the points produces the biggest change in fit when removed now?
- Which of the fits seems to generalize best?
