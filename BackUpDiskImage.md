Now that you configured your Raspberry Pi, it is wise to backup your configuration in case something got wrong in the later configuration.
So you don't need to redo everything from the beginning.

######1. Shutdown your Raspberry Pi :

`sudo shutdown`

Get the SD Card out of the Pi and put it back to your Mac/Linux/Windows PC

######2. Backup the Raspberry Pi image to your computer : 

On Mac type : 
`sudo dd if=/dev/rdisk1 of=/path/to/backup.img bs=1m`

or to reduce the amount of space :
`sudo dd if=/dev/rdisk1 bs=1m | gzip > /path/to/backup.gz`

Then put the SD Card back in the Raspberry Pi and plug it back on.

Your backuped image file is now safe on your computer.
If you want to get back to it, you only have to burn that image to a microSD card with Etcher, following the step 1.
Or you can use the `dd` command and just swap the `if` (input file), and `of` (output file) parameters:
`sudo dd if=/path/to/backup.img of=/dev/rdisk1 bs=1m`




