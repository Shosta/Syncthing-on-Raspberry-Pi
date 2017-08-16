This works for any network storage or Hard Drive.

I personnaly have a WD MyCloud NAS. It is the simplest and cheapest NAS device from Western Digital. 
![WD MyCloud NAS](./AutomountHardDrivesImages/MyCloud.jpg)

It is a very good device. But it doesn't have all the possibilities of more expensive NAS devices.
The Raspberry Pi is the perfect device to do bring a lot of excellent new features to it at the cheapest price.

######1. Configure the fstab file :
First, backup your fstab file if you mess something configuring it :
`sudo cp /etc/fstab /etc/fstab.bak`

######2. Create folder in the /mnt/ folder so that you can mount your network share in that folder
`sudo mkdir WDMyCloudShares`
`sudo nano /etc/fstab`

At the end of the file add the following lines :
>`//ShostaCloud/Remi/Vidéos/Films /home/remi/WDMyCloudShares/Videos cifs user=yourLogin,password=yourPassword,uid=remi,gid=remi,x-systemd.automount 0 0`
######TODO: Add a screenshot with the fstab properly modified.

Reboot to verify that it works properly :
`sudo reboot`

Wait for the reboot, then check the mounted volumes :
`df -h`
