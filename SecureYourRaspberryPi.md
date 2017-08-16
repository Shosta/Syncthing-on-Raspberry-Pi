######Change the pi default password :
`sudo passwd pi`

This is one of the **most important** step.
If you don't change the default Raspberry Pi password, you let it open to hackers as the default user and password is known and hackers made some script to look for Raspberry Pi on the network with the default user and password.

######Create a new user :

Add it to the Sudo group

######Configure the SSH connection :



######Limit the SSH connection to your new user :
We use sshd master configuration file to disable root login and this will may decrease and prevent the hacker from gaining root access to your Linux box. We also see how to enable root access again as well as how to limit ssh access based on users list.
Disable SSH Root Login
To disable root login, open the main ssh configuration file /etc/ssh/sshd_config with your choice of editor.

######Change the SSH default port : 
Limit SSH User Logins
If you have large number of user accounts on the systems, then it makes sense that we limit remote access to those users who really need it. Open the `/etc/ssh/sshd_config file`.
`sudo nano /etc/ssh/sshd_config`

Add an AllowUsers line at the bottom of the file with a space separated by list of usernames. For example, user tecmint and sheena both have access to remote ssh.

AllowUsers tecmint sheena

######Change the SSH default port :

Change it from 22 (default for ssh) to a free one. 3321 should be ok.

Look for the line : 
What ports, IPs and protocols we listen for
Port 22

And Change Port 22 to Port 3321

Now to connect to your pi using ssh you have to specify the port :
`ssh yourname@yourRaspberryHostname -p yourNewSshPort` (3321 in the example).

If you have that error : 
>`Warning: the ECDSA host key for 'myserver' differs from the key for the IP address
that means that the ssh key in the known_hosts file changed (that’s indeed the case).`

So back up your ssh known_hosts file
`sudo cp ~/.ssh/known_hosts ~/.ssh/known_hosts.bak`

Then open the file and delete the former key :
`sudo nano ~/.ssh/known_hosts`

`ctrl-X then Y`

Then your ssh connection should be secure enough. 