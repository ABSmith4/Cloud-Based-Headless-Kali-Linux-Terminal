# Installing Kali Linux

## Initial Boot and Installation

![installer](https://github.com/ABSmith4/Cloud-Based-Headless-Kali-Linux-Terminal/blob/bec1385629fc92f7191e298ef23d9b2bfc532705/Images/Installer.png)

![Language](https://github.com/ABSmith4/Cloud-Based-Headless-Kali-Linux-Terminal/blob/bec1385629fc92f7191e298ef23d9b2bfc532705/Images/Language.png)

![Hostname](https://github.com/ABSmith4/Cloud-Based-Headless-Kali-Linux-Terminal/blob/bec1385629fc92f7191e298ef23d9b2bfc532705/Images/hostname.png)

Note: It's okay to leave the domain name and proxy blank, we won't need it.

![PW](https://github.com/ABSmith4/Cloud-Based-Headless-Kali-Linux-Terminal/blob/bec1385629fc92f7191e298ef23d9b2bfc532705/Images/password.png)

* Next, we will set up the first user, password, and then select the timezone.

![Partitioning](https://github.com/ABSmith4/Cloud-Based-Headless-Kali-Linux-Terminal/blob/bec1385629fc92f7191e298ef23d9b2bfc532705/Images/Partition.png)

* Select Manual Partitioning Method.

![Partition creation](https://github.com/ABSmith4/Cloud-Based-Headless-Kali-Linux-Terminal/blob/bec1385629fc92f7191e298ef23d9b2bfc532705/Images/Partition_disks.png)

Select SCSl3 (Small Computer System Interface 3)

In terms of our partition, SCSI3 ensures effecient, high-speed data transfers and improved connectivity an functionality of the system we are building.  

Note: The (0, 0, 0) stands for Controller 0, Disk 0, Partition 0. Therefore, it is the first controller, disk, and partition on that disk. 

![Partition Table](https://github.com/ABSmith4/Cloud-Based-Headless-Kali-Linux-Terminal/blob/bec1385629fc92f7191e298ef23d9b2bfc532705/Images/Create_partition_table.png)

* Select YES.

![pri/log](https://github.com/ABSmith4/Cloud-Based-Headless-Kali-Linux-Terminal/blob/bec1385629fc92f7191e298ef23d9b2bfc532705/Images/pri_log-partition.png)

* Select Partition pri/log.

![new partition](https://github.com/ABSmith4/Cloud-Based-Headless-Kali-Linux-Terminal/blob/bec1385629fc92f7191e298ef23d9b2bfc532705/Images/How-to-use-free-space.png)

* Create the new partition.

![max_size](https://github.com/ABSmith4/Cloud-Based-Headless-Kali-Linux-Terminal/blob/bec1385629fc92f7191e298ef23d9b2bfc532705/Images/partition_maxsize.png)

* Continue

![primary](https://github.com/ABSmith4/Cloud-Based-Headless-Kali-Linux-Terminal/blob/bec1385629fc92f7191e298ef23d9b2bfc532705/Images/Partition_type.png)

* Select 'Primary' and then 'Done'

![finishpart](https://github.com/ABSmith4/Cloud-Based-Headless-Kali-Linux-Terminal/blob/bec1385629fc92f7191e298ef23d9b2bfc532705/Images/finish_partition.png)

* Finish the partition and choose 'No' for the swap space warning.

![changes](https://github.com/ABSmith4/Cloud-Based-Headless-Kali-Linux-Terminal/blob/bec1385629fc92f7191e298ef23d9b2bfc532705/Images/write-changes-to-disk.png)

![install](https://github.com/ABSmith4/Cloud-Based-Headless-Kali-Linux-Terminal/blob/bec1385629fc92f7191e298ef23d9b2bfc532705/Images/Install-base-system.png)

* Write changes to the disk and install the base Kali system.

![Deselect](https://github.com/ABSmith4/Cloud-Based-Headless-Kali-Linux-Terminal/blob/bec1385629fc92f7191e298ef23d9b2bfc532705/Images/Deselect-All.png)

* Deselect all with spacebar. We will configure the tools when the server is running in the cloud.

![bootloader](https://github.com/ABSmith4/Cloud-Based-Headless-Kali-Linux-Terminal/blob/bec1385629fc92f7191e298ef23d9b2bfc532705/Images/bootloader.png)

* Install the bootloader and choose location "/dev/sda".

Now that installation is complete, we have to unaattach the iso file from virtual box to prevent boot into installation on startup.

![unattach](https://github.com/ABSmith4/Cloud-Based-Headless-Kali-Linux-Terminal/blob/bec1385629fc92f7191e298ef23d9b2bfc532705/Images/remove-mini-iso.png)

![reboot](https://github.com/ABSmith4/Cloud-Based-Headless-Kali-Linux-Terminal/blob/bec1385629fc92f7191e298ef23d9b2bfc532705/Images/reboot.png)

* And Reboot.

Congratulations! You have successfully installed Kali Linux on this image.

