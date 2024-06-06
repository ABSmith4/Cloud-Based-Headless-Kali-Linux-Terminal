# Post-deployment Configuration

Looks like she's all set; Our baby is all grown up!

Now, you should be able to connect to our terminal normally.

`ssh [username]@[IP]` or if you're using a specialized public key `ssh /path/to/file [username]@[IP]`

## PIÈCE DE RÉSISTANCE 

The Kali Linux Developers create metapackages that give us the flexibility to install specific needs based on a particular usecase. To complete our project, we will need all the tools that do not require a graphical user interface.

`sudo apt install kali-linux-headless`

Feel free to check out more of the available [metapackages.](https://www.kali.org/tools/kali-meta/)

And lastly, we will create a local backup of the current state of our cloud image.

`fdisk -l` will display the name of your disk. Then, download the image of that disk with DD and SSH.

`ssh [username]@[IP] "dd if=[/name/of/disk] | gzip -l -" | dd of=kali_digital_ocean_image.gz`

They grow up so fast! (I could cry.) So long, farewell, to you my friend. Goodbye for now, until we meet again!