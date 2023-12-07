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
7. open putty `sudo putty` -> copy the ip number -> go to SSH -> X11 -> Enable X11 forwarding
8. use the username `pi` and password `raspberry`
