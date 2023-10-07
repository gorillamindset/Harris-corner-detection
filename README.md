# computer-vision-based-vertical-damage-assessment
This code can be used to assess vertical deflection of a structure undergoing noise the points detected are according to the kanade lucas algorithm and the points detected are using harris corner detection.

steps followed:
• Load, analyze, and visualize video frames.
• Apply the Kanade-Lucas-Tomasi (KLT) algorithm to track points in video frames.
• Convert displacement unit from pixels to meters.

Two-dimensional (2D) tracking using Kanade-Lucas-Tomasi (KLT) algorithm
The next task is to measure the structure's vibration in 2D image plane (unit: pixels). MATLAB implements a powerful algorithm,termed Kanade-Lucas-Tomasi (KLT) algorithm, that tracks points specified by the user throughout the video data. Following the MATLAB tutorial of the KLT algorithm [1], this tutorial applies the algorithm by the following steps:
For each of the joint 1-16 specified in Figure 5 of the competition problem statement,
1. Set a region of interest (ROl) that includes the joint,
2. Detect corner points inside the ROI,
3. Apply KLT algorithm to track each corner point throughout the video data, and
4. Estimate 2D displacement of the joint by averaging the displacement of the corner points.



