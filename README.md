# pong-openpose
A two-player version of Pong that uses keypoint tracking by means of an RGB-camera to control the paddles.

This game was realized using Unity as the game engine and the ![OpenPose](https://github.com/CMU-Perceptual-Computing-Lab/openpose?tab=readme-ov-file) Python API for keypoint tracking. 

# Structure
The Python scripts for keypoint tracking and the Unity project are launched seperately.

The Unity project will listen for an incoming socket connection, and will accept exactly one.

The Python script will connect to Unity via the socket connection and start sending keypoint-data as soon as it is ready.

# Prerequisites *(refer to the respective readme of each submodule for detailed instructions)*
Our system:
- Windows 10
- ZOTAC GAMING GeForce RTX 4090 Trinity (NVIDIA)

For the Python Scripts:
- OpenPose *(refer to submodule for detailed instruction)*
- Pyton 3.7.0
- opencv 4.9.0.80

For Unity:
- Unity 2022.3.11f1

# Installation and launching the game
The readme files in the submodules detail the respective installation processes.
Once everything is installed, follow these steps to launch the game:
1. Launch the Unity project and execute it by pressing the play button.\
   *Unity will now be blocked as it waits for an incoming socket connection. Don't be alarmed that the program hangs, it will resume when a connection is established.*
   
2. Now launch the main.py file. A socket connection will now be established between the Python script and the (running) Unity project.\
   *The paddles will be controllable as soon as Python is ready to send the data after connecting to and launching the RGB-webcam.*

# How to play
>In the current state, the game requires two players to work as intended. The optimal setup is placing a RGB-webcam on top of the monitor that will be displaying the game and of course having the lens of the camera and the screen of the monitor facing towards the players.

The keypoint-data processing is invariant to the player position in the room, as long as their whole body is within the camera's view.

Importantly, whichever player is farthest to the left will control the left paddle with their left hand.\
The player farthest to the right will control the right paddle with their right hand.\
By switching positions (swapping which player is one the left/right) the control of the paddles will also be swapped. 

By raising the hand that controls the paddle above one's shoulder, the paddle will move upwards.\
By lowering the hand that controls the paddle below one's shoulder, the paddle will move downwards.\
The distance between the shoulder and the hand will determine the velocity of the paddle. The greater the distance the faster it moves.



