=================================================================
stereo_calibration - StereoCamera Calibration using Python-OpenCV
=================================================================
* Python Implementation of Stereo Camera Calibration using [checkerboard pattern images](http://docs.opencv.org/2.4/doc/tutorials/calib3d/camera_calibration/camera_calibration.html).

Features
--------
* Prints -or- Returns dict object containing Camera Matrices and R, T, E and F
* Takes Stereo Camera Images path as an input

Requirements
------------
* cv2
* numpy

Example
-------
* Run using the command line
```
python camera_calibration.py /path/to/stereo/camera/images/
```
* Run using Python
```
>>> from camera_calibration import StereoCalibration
>>> cal = StereoCalibration('/path/to/stereo/camera/images')
>>> cal.camera_model
```

Results
-------
```
$python camera_calibration.py /path/to/stereo/camera/images/
('Intrinsic_mtx_1', array([[  4.14602008e+03,   0.00000000e+00,   7.59295870e+02],
       [  0.00000000e+00,   4.21635719e+03,   4.42260382e+02],
       [  0.00000000e+00,   0.00000000e+00,   1.00000000e+00]]))
('dist_1', array([[ -2.73378180e+00,   1.41433393e+02,  -1.36677475e-02,
          1.01134046e-01,  -5.17885999e+03]]))
('Intrinsic_mtx_2', array([[  4.16808926e+03,   0.00000000e+00,   7.33997545e+02],
       [  0.00000000e+00,   4.20937958e+03,   7.02753997e+01],
       [  0.00000000e+00,   0.00000000e+00,   1.00000000e+00]]))
('dist_2', array([[ -7.91010976e-01,   4.49627502e+01,  -1.55972074e-02,
         -3.95037927e-03,  -1.24662356e+03]]))
('R', array([[ 0.99869078,  0.00100433,  0.05114416],
       [-0.00564778,  0.99585969,  0.09072808],
       [-0.05084128, -0.09089815,  0.99456156]]))
('T', array([[-9.87912629],
       [ 0.24163047],
       [ 1.61658844]]))
('E', array([[ -3.15467525e-03,  -1.63185902e+00,   9.36464101e-02],
       [  1.11220449e+00,  -8.96370670e-01,   9.90807829e+00],
       [ -1.85519033e-01,  -9.83846631e+00,  -9.08672125e-01]]))
('F', array([[  3.44154284e-09,   1.75055259e-06,  -1.20037917e-03],
       [ -1.20144000e-06,   9.52136218e-07,  -4.38838342e-02],
       [  9.25481179e-04,   4.26384886e-02,   1.00000000e+00]]))
```

Output Parameters
-----------------
__Intrinsic_mtx_1__ – output first camera matrix

__dist_1__ – output vector of distortion coefficients  (k_1, k_2, p_1, p_2[, k_3[, k_4, k_5, k_6]]) of 4, 5, or 8 elements. The output vector length depends on the flags.

__Intrinsic_mtx_2__ – output second camera matrix

__dist_2__ – output lens distortion coefficients for the second camera

__R__ – Output rotation matrix between the 1st and the 2nd camera coordinate systems.

__T__ – Output translation vector between the coordinate systems of the cameras.

__E__ – Output essential matrix.

__F__ – Output fundamental matrix.

More reference on __R__, __T__, __E__ and __F__ can be found [here](http://docs.opencv.org/2.4/modules/calib3d/doc/camera_calibration_and_3d_reconstruction.html#stereocalibrate)

Notes
-----
* Assumption here is that given image path contains two folders of checkerboard images named `LEFT` and `RIGHT`. User can change these relative folder paths.
* User may also change `flags` as per calibration output requirements.

References
----------
* [Stereo Camera Calibration](http://docs.opencv.org/2.4/modules/calib3d/doc/camera_calibration_and_3d_reconstruction.html) using OpenCV


