# pong-openpose
A two-player version of Pong where the paddles are controlled through keypoint tracking using an RGB camera.

This game was realized using Unity as the game engine and the [OpenPose](https://github.com/CMU-Perceptual-Computing-Lab/openpose?tab=readme-ov-file) Python API for keypoint tracking. 

# Structure
The implementation consists of separate Python scripts for keypoint tracking and the Unity project which are launched seperately.

The Unity project listens for an incoming socket connection, and accepts exactly one at a time.

The Python script establishes a socket connection with Unity and starts sending keypoint-data as soon as it is ready.

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
   *Unity will now be blocked as it waits for an incoming socket connection. Don't be alarmed that the program seems unresponsive, it will resume when a connection is established.*
   
2. Now launch the main.py file. A socket connection will be established between the Python script and the (running) Unity project.\
   *The paddles will be controllable as soon as Python is ready to send the data after connecting to and launching the RGB-webcam.*

# How to play
>In the current state, the game requires two players to work as intended. The optimal setup is placing a RGB-webcam on top of the monitor displaying the game with the camera lens and monitor facing the players.

The keypoint-data processing is invariant to the player position in the room, as long as their entire bodies are within the camera's view.

- The leftmost player controls the left paddle with their left hand.
- The rightmost player controls the right paddle with their right hand.
- Switching player positions switches paddle control accordingly.

By raising the hand that controls the paddle above the shoulder the paddle will move upwards and lowering it below the shoulder will make the paddle move downwards.\
The distance between the shoulder and hand determines the paddle's velocity - the greater the distance the faster it moves.
