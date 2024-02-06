# pong-openpose
A two-player version of Pong that uses keypoint tracking by means of an RGB-camera to control the paddles.

# Description
This game was realized using Unity as the game engine and the ![OpenPose](https://github.com/CMU-Perceptual-Computing-Lab/openpose?tab=readme-ov-file) Python API for keypoint tracking. 

# Structure
The Python scripts for keypoint tracking and the Unity project are launched seperately. The Unity project will listen for an incoming socket connection, and will accept exactly one. 
The Python script will connect to Unity via the socket connection and start sending (somewhat post-processed) keypoint data as soon as it is ready. It will send the keypoint-data as fast as it possibly can. 
Most of the keypoint-data post-processing happens within Unity.
Unity will wait for an incoming socket connection on the main thread. The keypoint-data post-processing happens on a seperate thread, as to not block the game. 

# Installation and launching the game
The readme files in the submodules detail the respective installation process.
Once everything is installed, follow these steps to launch the game:
1. Launch the Unity project and execute it by pressing the play button. Unity will now be blocked as it waits for an incoming socket connection. (Don't be alarmed that the program hangs, it will resume when a connection is established.)
2. Now launch the main.py file. A socket connection will now be established between the Python script and the (running) Unity project. The paddles won't will be controllable as soon as Python is ready to send the data after connecting to and launching the RGB-webcam.

# How to play
In the current state, the game requires two players to work as intended.
The optimal setup is placing a RGB-webcam on top of the monitor that will be displaying the game and of course having the lens of the camera and the screen of the monitor facing towards the players.
The left player in relation to the camera will control the left paddle with their left hand. 
The right player in relation to the camera will control the right paddle with their right hand.
By raising and lowering the hand 

- openpose installieren (viel spaß lol)
- visual studio enterprise 2019
- python 3.7.0 (stimmt das? sagt vs code)
- opencv 4.9.0.80
- unity 2022.3.11f1

kamera
unity starten
main.py starten

