---
tags:
  - aws
  - issue
---
If an EC2 instance can't be reached via SSH, there is an option to connect via the EC2 serial console to recover. If you know the password for any user, simply try to log in using the EC2 serial console. Otherwise, follow the instructions below to restore the password for the root user.

## Root Password Recovery
1. Stop the instance.
2. Detach the volume from the instance (navigate to `volumes` -> select the volume -> click `actions` -> choose `detach`).
3. Attach the volume to another instance to which you have access (navigate to `volumes` -> select the volume -> click `actions` -> choose `attach`).
4. Mount the volume:
	```sh
	$ lsblk
	NAME MAJ:MIN RM SIZE RO TYPE MOUNTPOINT
	nvme1n1 259:0 0 10G 0 disk
	nvme0n1 259:1 0 8G 0 disk
		-nvme0n1p1 259:2 0 8G 0 part /
		-nvme0n1p128 259:3 0 1M 0 part
	# Let's assume that nvme0n1 is our volume; we need to mount its root part nvme0n1p1
	$ mkdir /mount_dir && mount /dev/nvme0n1p1 /mount_dir
	```
5. Remove the password:
	To remove the password, modify the `/etc/passwd` file. An example line in the `/etc/passwd` file looks like this:
	```
	root:x:0:0:root:/root:/bin/bash
	```
	The 'x' in this line means that the password is actually stored as a hash in the shadow file. You can simply remove it like this:
	```
	root::0:0:root:/root:/bin/bash 
	```
 6. Detach the volume from the helper instance (navigate to `volumes` -> select the volume -> click `actions` -> choose `detach`).
 7. Attach the volume back to the broken instance (navigate to `volumes` -> select the volume -> click `actions` -> choose `attach`).
 8. Start the instance.
 9.  Log in with the EC2 serial console using the `root` user and a blank password.
 10. Change the root password:
	```
	root@machine# passwd
	New password: [desired password]
	Retype new password: [desired password]
	```
	