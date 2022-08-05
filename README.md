# pan_servo_controle

This ROS package were created for TK's robot built log. It is also a ros node that subscribes to the /Joy topic published by the Joy_node.
Joy_node reads compatable game controlers like the x-box controler I use and publishes its button presses and joystick posisions.
It then uses rosserial to sent(publishes on the servo topic) angles to a rc servo connected to laptop/raspberry PI through an Arduino UNO.

Prerquisets:

* a ROS installation on machine(laptop/Pi) -- I am using Noetic http://wiki.ros.org/noetic/Installation
* a Arduino Uno flashed with Ros-Arduino tutorial -- http://wiki.ros.org/rosserial_arduino/Tutorials/Servo%20Controller
* a compatable game controler --http://wiki.ros.org/joy
* and ofcourse a rc servo -- I am using a dirt cheap SG90 from tower-pro

Install:
* create a catkin_ws or ad to the one your using -- http://wiki.ros.org/catkin/Tutorials/create_a_workspace
  (if you brake your _ws ....work_space... >your problem, it works on my Ubuntu 20.04 with no dramas)
* clone this git in your src folder of your _ws
* then step back to your _ws forlder (so normally one directory up from your /src directory) and run catkin_make.

usesich:

You will need 4x terminals (command line interfaces)
 * in the first run Roscore, (as you would AFTER you source your ros installation setup file)
    usally "source /opt/ros/noetic/setup.bash"  replace noetic if your using  different ros1 !!! not ROS2 !!!
 * In second run roserial with your uno and servo connected (using correct port) remeber to "source /opt/ros/noetic/setup.bash" first
 * In third run Joy_node  with your game controler conected (remember the port) remeber to "source /opt/ros/noetic/setup.bash" first
 * In fourth run "rosrun servo_controle servo_controle_node" Take note: "source /opt/ros/noetic/setup.bash" and then source your "_ws/devel/setup bash"

There's a youtube vid 
