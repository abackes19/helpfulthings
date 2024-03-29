# helpfulthings
Codes for the arm control using inverse kinematics, starting the cameras, and the CO2 sensor. Work by Amelia Backes.

# Arm
run on pi w/arm motors: fullmotor.py

run on computer: fullarm.py

If you're using them together start fullmotor.py first, otherwise you can run fullarm.py alone on the computer. It uses pygame and socket networking to show a display and run together. Fullarm.py shows both side and top view.

For the inverse kinematics math: x and y planes are fixed, as shown on left side of the display. On the right side (the top view), the traditional x axis is the z axis and the traditional y axis is the w axis. W is a dummy variable. The length of the arm is the x axis. This may sound confusing, but play with fullarm.py and you'll hopefully see what I mean. There's also a diagram in the google drive with helful labels. Feel free to change how the axis are labeled. We did it this way because we thought it would be the easiest/most convenient to control, but you may not think the same. 

Right now there are also a number of things you can do to break the code by making it do some invalid math. This was going to be fixed by putting in the limitations of the physical arm but then it snapped off and we never used it again so that was not done. 

For the socket networking: make sure to change the ip address in the code to the pi you're using (or 127.0.0.1 if you're just doing it on your computer). Control C if it's pausing to connect and you don't want it to (pygame will still open). Ask Brian Bianchi or Alex Saffert if you have questions about it.

If you want to know how the fullmotor.py code works for controlling the motors, ask Connor Weatherly/ see his documentation. It uses potentiometers so if you aren't using those, just take the socket/pickle part of that code to get the xyz coordinates to the pi.

Read the code comments to learn more specifically how it works. The videos on the drive can help. Other versions are in the misc2019 repository and ink (the pygame-ik.py series). Contact me if you're desperate (bugging Hans is probably the easiest way).

# Cameras

The basics is camera.txt, run it on the pi with 
$ bash camera.txt 

check which videos you need with 
$ ls /dev

For every new camera you add, change the video (ex: video0 > video1) depending on the ls /dev and update the port (ex: 8080 > 8090). 

To view the cameras: http://ipaddress:port/?action=stream  example: 
  
or in GUI: config ip addresses: 'ipaddress:port'

# CO2 Sensor
This is for the DFRObot 0159 co2 sensor. Look at the wiki for more info. To view the data, config the ip address of the data in the GUI. 


# RoboGUI-Electron

Be gentle with it. Look at the documentation before you bug Voss. 

Helpful things to do: toggle developer tools. Edit the index js and html scripts to add buttons or do other fun things. To learn more: see my video on the drive, look at Brad Shibley's documentation, ask someone who knows those languages.

# Other things

following2019.py : an attempt at autonomy, never tested. You'll need 6 analog sensors: one on left and front sides, two on right and back sides. Michael Miller may have documentation on this.

timer.py : a timer for the driver during the challenges. You can only run one thing posting data at a time, so sensors.py should do it all but it might not be updated.

#

You'll need RoboPiLib, setup, post_to_web, pygame, and/or python3 depending on the code. You can get these from bsmLib or just import them from there.

Good luck and godspeed.

