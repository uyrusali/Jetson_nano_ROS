# Capture Video with GPSD tags using Jetson Nano


## Installationn

ros-desktop-full is computationally heavy for embedded systems such as Jetson Nano. So we install ros-melodic-dektop
Follow this tutorial for the installation:

https://www.stereolabs.com/blog/ros-and-nvidia-jetson-nano/

After installing ros-melodic-desktop with

```$ sudo apt install ros-melodic-desktop ```

We have to install rosdep seperately as rosdep is not automatically installed after 2020 (see: https://github.com/ros-infrastructure/rosdep/issues/745)

```$ sudo apt install python-rosdep```

## Creating a ROS Catkin Workspace

Kept following above tutorial for catkin workspace creation.


## USB_Cam to BAG

https://stackoverflow.com/questions/65295577/how-to-create-rosbag-file-using-usb-camera-provide-camera-images-as-sensor-msgs

Clone the usb_cam repository into ```catkin_ws/src```

```
$ cd ~/catkin_ws/src
$ git clone https://github.com/ros-drivers/usb_cam
```
Install the dependencies for usb_cam

```
$ rosdep install --from-paths /path/to/your/catkin_ws/src --ignore-src
```

Now, build the Catkin wororkspace with usb_cam package:

```
$ cd ~/catkin_ws/
$ catkin_make
```
Run usb_cam node after the successful build. First start roscore if it is not running on a seperate terminal

```
$ roscore
```
Then we can first run usb_cam node and the rviz to make sure that usb_Cam is working

```
$ rosrun usb_cam usb_cam_node
$ rosrun rviz rviz
```
