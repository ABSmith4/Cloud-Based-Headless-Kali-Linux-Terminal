# Installing Kali Linux

## Initial Boot and Installation

![installer](/Images/Installer.png)

![Language](/Images/Language.png)

![Hostname](/Images/hostname.png)

Note: It's okay to leave the domain name and proxy blank, we won't need it.

![PW](/Images/password.png)

* Next, we will set up the first user, password, and then select the timezone.

![Partitioning](/Images/Partition.png)

* Select Manual Partitioning Method.

![Partition creation](/Images/Partition_disks.png)

Select SCSl3 (Small Computer System Interface 3)

In terms of our partition, SCSI3 ensures effecient, high-speed data transfers and improved connectivity an functionality of the system we are building.  

Note: The (0, 0, 0) stands for Controller 0, Disk 0, Partition 0. Therefore, it is the first controller, disk, and partition on that disk. 

![Partition Table](/Images/Create_partition_table.png)

* Select YES.

![pri/log](/Images/pri_log-partition.png)

* Select Partition pri/log.

![new partition](/Images/How-to-use-free-space.png)

* Create the new partition.

![max_size](/Images/partition_maxsize.png)

* Continue

![primary](/Images/Partition_type.png)

* Select 'Primary' and then 'Done'

![finishpart](/Images/finish_partition.png)

* Finish the partition and choose 'No' for the swap space warning.

![changes](/Images/write-changes-to-disk.png)

![install](/Images/Install-base-system.png)

* Write changes to the disk and install the base Kali system.

![Deselect](/Images/Deselect-All.png)

* Deselect All. We will configure the tools when the server is running in the cloud.

![bootloader](/Images/bootloader.png)

* Install the bootloader and choose location "/dev/sda".

Now that installation is complete, we have to unaattach the iso file from virtual box to prevent boot into installation on startup.

![unattach](/Images/remove-mini-iso.png)

![reboot](/Images/reboot.png)

* And Reboot.

Congratulations! You have successfully installed Kali Linux on this image.


[Turn the page.](initial-configuration.md)