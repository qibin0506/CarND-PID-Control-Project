# CarND-Controls-PID
Self-Driving Car Engineer Nanodegree Program

---

## Reflection
Describe the effect each of the P, I, D components had in your implementation.
Proportional component (P): Makes the car steer towards the CTE. It is achieved by multiplying the CTE by P values. It will never reach the CTE but will oscillate around it, resulting in an unsecure behaviour. That's the reason to use I and D temrs.

Integral component (I): Compensates the systematic bias. When the car steering has been incorrectly fixed, lets say to the left, the I term should compensate it. This is achieved acumulating the value of the surface between the car position and the CTE over time, and multipying this value by the I coefficient.


Differential component (D): Counter-steers when the car begins to steer toward the CTE. It goes smaller as the car drives towards the CTE, avoiding P component tendency to ring and overshoot the center line.

The final values are:

P = 0.18, I = 0, D = 3.0

Result:

You can observe the result in this video([https://youtu.be/GsOKjwxbiXE](https://youtu.be/GsOKjwxbiXE)).

## Dependencies

* cmake >= 3.5
 * All OSes: [click here for installation instructions](https://cmake.org/install/)
* make >= 4.1(mac, linux), 3.81(Windows)
  * Linux: make is installed by default on most Linux distros
  * Mac: [install Xcode command line tools to get make](https://developer.apple.com/xcode/features/)
  * Windows: [Click here for installation instructions](http://gnuwin32.sourceforge.net/packages/make.htm)
* gcc/g++ >= 5.4
  * Linux: gcc / g++ is installed by default on most Linux distros
  * Mac: same deal as make - [install Xcode command line tools]((https://developer.apple.com/xcode/features/)
  * Windows: recommend using [MinGW](http://www.mingw.org/)
* [uWebSockets](https://github.com/uWebSockets/uWebSockets)
  * Run either `./install-mac.sh` or `./install-ubuntu.sh`.
  * If you install from source, checkout to commit `e94b6e1`, i.e.
    ```
    git clone https://github.com/uWebSockets/uWebSockets 
    cd uWebSockets
    git checkout e94b6e1
    ```
    Some function signatures have changed in v0.14.x. See [this PR](https://github.com/udacity/CarND-MPC-Project/pull/3) for more details.
* Simulator. You can download these from the [project intro page](https://github.com/udacity/self-driving-car-sim/releases) in the classroom.

Fellow students have put together a guide to Windows set-up for the project [here](https://s3-us-west-1.amazonaws.com/udacity-selfdrivingcar/files/Kidnapped_Vehicle_Windows_Setup.pdf) if the environment you have set up for the Sensor Fusion projects does not work for this project. There's also an experimental patch for windows in this [PR](https://github.com/udacity/CarND-PID-Control-Project/pull/3).

## Basic Build Instructions

1. Clone this repo.
2. Make a build directory: `mkdir build && cd build`
3. Compile: `cmake .. && make`
4. Run it: `./pid`. 
