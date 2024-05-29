# Preparing the Environment

## Download and Install [VirtualBox](https://www.virtualbox.org/wiki/Downloads)

Select your binary package based on your system platform.

## Obtain the ISO

By default, Kali Linux ISOs come with a desktop environment. For our purposes, we want to minimize file upload size and avoid wasting resources on a headless system. Instead of uninstalling or disabling the GUI, we will use a [netboot ISO](https://http.kali.org/kali/dists/kali-rolling/main/installer-amd64/current/images/netboot/) to install the virtual machine. Click on "mini.iso" to begin downloading to your local machine.

## Create the VM

* Create a new virtual machine setting the operating system to Debian 64-bit. 

![Operating System]({{"/Images/OS_setup.png" | relative_url }} )

Note: Check the box for unattended installation as we will not be using it.

![Disk Allocation]({{"/Images/Disk_allocation.png" | relative_url }} )

* Allocate at least 20 GB for the HDD.

Select finish to create the .vdi (virtual disk image) that will be uploaded into our cloud provider. Remember, it is important to make sure the image is dynamically allocated so do not check the "Pre-allocate Full-size" box. 

## Prepare the Iso and Initial Boot

* In order to boot into the installer when the VM starts, we need to attach the mini.iso into the storage controller.

![ISO Mount](/Images/iso-mount.png)
