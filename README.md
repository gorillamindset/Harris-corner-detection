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


Detecting corner points inside the ROI
used Harris corner points recognition to find salient corner points inside the selected ROI. After detecting the corner points, those points are visualized.

2D displacement estimation

Pixel-to-meter conversion of displacement

The displacement estimated now is in pixels, or in other words, measured in the image coordinate system. In our scenario, however, we are interested in measuring physically-meaningful displacement, e.g. vertical displacement of the joints expressed in meters. for the pixel-to-meter conversion,there are two cases:
• The truss plane is parallel to the image plane, and the truss longitudinal axis and the vertical direction are aligned with the image horizontal and vertical axes, respectively

• The truss plane is not parallel to the image plane
In the first case, vertical (and longitudinal) compoent of the bridge displacement can be obtained by scaling the 2D displacement by an appropriate factor. In contrast, the second case is more challenging, because different scaling factors should be used for joints at the different distances. Moreover, image vertical direction is no longer aligned with the direction of the vertical structural displacement, requiring an additional coordinate transform.

The project upto now focused on converting for the first case only where image plane is parallel to truss plane.

