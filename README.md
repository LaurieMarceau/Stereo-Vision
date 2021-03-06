
# Stereo Vision with OpenCV

Please find the full documentation in the documentation folder. This was made for the course HW/SW co-design with a LEGO car (IN2106, IN0012, IN4154) at TUM, in the Winter semester 2016.

This program calibrate a stereocamera (intrinsic and extrinsic), calculate a depth map and provides a top view of the depth map so the automated car can decide where to go. Can only be used with the plugged stereo camera. You can see the result video [here](https://youtu.be/H497a5wq_IY).

## Dependencies

Install following libraries: 
- Boost C++
- OpenCV 2.7

Boost is only for the calibration process. Once the calibration is done, the intrinsics and extrinsics files can be used without using this library.

## How to use it

- Go into at the root of the folder in a terminal, and make sure the file build.sh as the proper access with ```sudo chmod 777 build.sh```
- Then send the command ```./build.sh```
- Go into the folder build with ```cd build```
- If you wanna do the calibration process send ```./sv 1``` but make sure you have the proper pictures taken with the stereocamera in the calibration folder. A set of at least 7 pairs is necessary.
- If you wanna just use the program, send ```./sv```
- Enjoy the depth map and the top view!

## Things to be aware when using the program:

- In the main.cpp verify the two camera index.
- If you use the calibration, verify the chessboard size in the cameracalibrator.hpp file (default is 9.6) and the square size of the chessboard in the cameracalibrator.cpp (default is 2.5 cm)
- To change the default matching method, go in depthsubstraction.cpp, by default it's the BM method.
- If you wanna use the SGBM algorithm, you have to change de disparity parameters, because the default parameters are changed to work with the BM algorithm only.

## Acknowledgement

This code was not only developped for a university course but also for a master student thesis, Roger Rösch. You can find part of my code he refactored for OpenCV 3.1.0 [here](https://github.com/ModelCar/Collision-Avoidance). You can also find his full master thesis about the Development and Construction of an Autonomous Car with Low Cost Components [here](http://wwwknoll.in.tum.de/pub/Main/Hub/Developmen.pdf).
