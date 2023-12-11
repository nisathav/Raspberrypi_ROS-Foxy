Connecting Raspberrypi with Linux using Ethernet
-----------------------------------------------
1. Create a `file named as ssh` in the `ROOT folder` of the chip
2. open network settings -> wired connection -> ipv4 -> select shared with other computer -> restart the computer
3. open terminal and type the command `sudo nano /etc/X11/Xwrapper.config`, change the following
   `allowed_users=anybody
   needs_root_rights=yes`
4. now connect the raspberrypi
5. open terminal and find the ip address of the raspberrypi. open network settings and find the ip address
6. `sudo apt-get install openssh-server openssh-client`
7. type in `arp -a` to find the ip address of the pi and use `ssh nisath@10.42.0.181`
8. setting up the network refer to this weblinks `https://articulatedrobotics.xyz/ready-for-ros-2-networking/` and for netplan tutorial refer `https://linuxconfig.org/netplan-network-configuration-tutorial-for-beginners`
9. when the host pc and pi is connected over same network we can access the pi through following method. find the host ip address `hostname -I` on the pi shell and type `SSH nisath@192.168.8.144`

Clone from github
---------------
1. create ssh key in your raspberry. `ssh-keygen` follow the instrcutions and copy the contents in the .pub folder. go to github and create a new SSH key
2. `git clone <ssh address of the repo>`

Power up LIDAR
-------------
1. connect the Lidar to the raspberry pi
2. clone the lidar repo `sudo apt install ros-foxy-rplidar-ros`
3. `ros2 run rplidar_ros rplidar_composition --ros-args -p serial_port:=/dev/ttyUSB0 -p frame_id:=laser_frame -p angle_compensate:=true -p scan_mode:=Standard` run the lidar package
