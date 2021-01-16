# MyWork
1.find P

2.find [R t]

.........................................................

# calibration_wand
Fundamental Matrix Estimation, Camera Calibration, Triangulation 2. 
The goal of this assignment is to implement fundamental matrix estimation to register pairs of images, as well as attempt camera calibration, triangulation in 
lecture 14(http://saurabhg.web.illinois.edu/teaching/ece549/sp2020/slides/lec14_calibration.pdf), 
and
lecture 15(http://saurabhg.web.illinois.edu/teaching/ece549/sp2020/slides/lec15_epipolar.pdf).
Test Images: We are providing two image pairs (library and lab in data/Q2/), and some starter code in semi.MP3_Q2_starter.ipynb, that we will work with.


(a) Fundamental Matrix Estimation . Given point matches, your task is to fit a fundamental matrix.
You will implement and compare the normalized and the unnormalized algorithms as discussed in lecture 15. 
For each algorithm and each image pair, report the estimated fundamental matrix, the residual (mean squared distance (in pixels) between points in both images and the corresponding epipolar line), and visualization of epipolar lines and corresponding points.
We have provided some starter code.
Note: For fundamental matrix estimation, don’t forget to enforce the rank-2 constraint. 
This can be done by taking the SVD of F, setting the smallest singular value to zero, and recomputing F.
You should use the least square setup that involves solving a homogeneous system.


(b) Camera Calibration. For the lab pair, calculate the camera projection matrices by using 2D matches in both views and 3D point coordinates in lab_3d.txt. Once you have computed your projection matrices, you can evaluate them using the provided evaluation function (evaluate_points). The function outputs the projected 2-D points and residual error. Report the estimated 3 × 4 camera projection matrices (for each image), and residual error.

Hint: The residual error should be < 20 and the squared distance of the projected 2D points from actual 2D points should be < 4. For the library pair, there are no ground truth 3D points. Instead, camera projection matrices are already provided in library1_camera.txt and library2_camera.txt.

(c) Camera Centers . Calculate the camera centers using the estimated or provided projection matrices for both pairs. Report the 3D locations of all the cameras in your report. Hint: Recall that the camera center is given by the null space of the camera matrix.

(d) Triangulation . Use linear least squares to triangulate the 3D position of each matching pair of 2D points using the two camera projection matrices. As a sanity check, your triangulated 3D points for the lab pair should match very closely the originally provided 3D points in lab_3d.txt. For each pair, display the two camera centers and reconstructed points in 3D. Include snapshots of this visualization in your report. Also report the residuals between the observed 2D points and the projected 3D points in the two images, for each pair. Note: You do not need the camera centers to solve the triangulation problem.
They are used just for the visualization. 

(e) Extra Credits . Use your putative match generation and RANSAC code from the last question to estimate fundamental matrices without ground-truth matches. For this part, only use the normalized algorithm. Report the number of inliers and the average residual for the inliers. Compare the quality of the result with the one you get from ground-truth matches.
