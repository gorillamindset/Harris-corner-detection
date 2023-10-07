# computer-vision-based-vertical-damage-assessment
This code can be used to assess vertical deflection of a structure undergoing noise the points detected are according to the kanade lucas algorithm and the points detected are using harris corner detection.

steps followed:
• Load, analyze, and visualize video frames.
• Apply the Kanade-Lucas-Tomasi (KLT) algorithm to track points in video frames.
• Convert displacement unit from pixels to meters.

Two-dimensional (2D) tracking using Kanade-Lucas-Tomasi (KLT) algorithm
The next task is to measure the structure's vibration in 2D image plane (unit: pixels).Kanade-Lucas-Tomasi (KLT) algorithm, that tracks points specified by the user throughout the video data.This is applied as the following steps:
For each of the joint 1-16 specified in Figure 5 of the competition problem statement,
1. Set a region of interest (ROl) that includes the joint,
2. Detect corner points inside the ROI,
3. Apply KLT algorithm to track each corner point throughout the video data, and


Estimate 2D displacement of the joint by averaging the displacement of the corner points and Detecting corner points inside the ROI

2D displacement estimation
Now, let's get the 2D displacement of each corner point and plot them.


Pixel-to-meter conversion of displacement:
The displacement estimated in the previous section was expressed in pixels, or in other words, measured in the image coordinate system. In our scenario, however, we are interested in measuring physically-meaningful displacement, e.g. vertical displacement of the joints expressed in meters.In that there are two scenarios
• When the truss plane is parallel to the image plane, and the truss longitudinal axis and the vertical direction are aligned with the image horizontal and vertical axes, respectively

• When the truss plane is not parallel to the image plane
In the first case, vertical (and longitudinal) component of the bridge displacement can be obtained by scaling the 2D displacement by an appropriate factor.






