# Kali RPi set up
To set up your own Kali Raspberry Pi pentesting station get the latest
Kali for Raspberry Pi image here:

https://www.offensive-security.com/kali-linux-arm-images/

Then you are all set if you have a keyboard and monitor.  If you want to enable
a SSH server and VNC server run the steps below.  After the last step the RPi
will restart and on boot after that you will be able to connect via either SSH
or VNC from your laptop/desktop without needing a monitor going forward.

#### Terminal steps
```
apt-get update
apt-get install openssh-server unzip vim
update-rc.d -f ssh remove
update-rc.d -f ssh defaults
systemctl enable ssh.service

# Copy the vnc-startup.sh file from this directory locally
# that script will setup vnc server to start on boot
chmod +x vnc-startup.sh
./vnc-startup.sh
```
