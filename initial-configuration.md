# Pre-deployment Configuration

Now that installation is complete and the system has been rebooted, we need to login and update it.

![Login](/Images/Predeployment/Login.png)

<pre>
# login as a super user to save yourself a little time.

sudo su

# update your dependencies

apt update && apt full-upgrade -y
</pre>

## Network Configuration

You may have noticed that your updates failed with a "Temporary failure in resolving 'http.kali.org'"

![failed resolution](/Images/Predeployment/Failure_resolving.png)

You may even notice that pinging a random site will result in a DNS failure.

![failed ping](/Images/Predeployment/failed_ping.png)

Now, you may be tempted to run the typical `ifconfig -a` to check your network interfaces. However, if you look closely you may notice most of your network details are missing.

![ifconfig screenshot]()

Since we are building a pentesting toolkit, lets start to think like a hacker and use `ip addr` instead. This command will give you a more detailed look under the hood. 

If you look closely, you may notice your eth0 interface is DOWN.

![eth0 down](/Images/Predeployment/eth0_down.png)

Let's breathe some new life into your eth0 interface.

Run `ip link set eth0 up` and then another `ip addr` to check your progress thus far.

Congrats! Your eth0 has finally been flagged as UP. But wait, there is no IPv4 address. Oh no!

Don't fret. If you know anything about networking, we didn't assign a static IP to the VM. We'll let the DHCP server do the talking instead.

Now run `DHClient eth0` then `ip addr` again.

![successful connection]()

And voila! Your virtual machine now successfully displays an new IPv4 address.

In case you may not have noticed, `dhclient` works by requesting an IP address from a DHCP Server. During this request, a DHCP (Dynamic Host Configuration Protocol) discovry message is sent to the broadcast address of your network.

When the message is received by the server, it replies back to your machine (based on your MAC address of your network interface) with an offer message that tells your machine which IP is being offered to it.

The offer message is then received by your machine and then responds with a DHCP request message for the offered IP.  Next, the DHCP server replies with an acknowledgement message, letting you know that the IP can be used by your machine at this point. Then, your network interface is configured for the assigned IP and you can connect to other IP-based servers.

NOTE: If you're a Redhat or a CentOS use, you may be more familiar with `dhcpd`, but no need to worry as they are very similar. The only difference is that `dhclient` will exit immediately if no broadcast interfaces are found, whereas `dhcpd` will continue until an interface has been found.

If you would like to read up on more about either one of these packages, feel free to explore the manual, or "man" pages for short.

`man dhclient` or `man dhcpd`

## Priviledged User Access

As our first step into system security, we need to provide our user that we created during [installation](installing-kali-linux.md) with the keys to the car. 

First, create the authorized keys file under your user name to ensure the remote connection will be successful. If not, you will encounter an access error in the form of `Permission Denied (publickey)`.

Therefore, we need to place our public key in our user directory instead of root. The directory traversal will look a little like this /home/[username]/.ssh/authorized_keys. 

<pre>
Mkdir /home/user/.ssh/

touch /home/user/.ssh/authorized_keys && nano /home/user/.ssh/authorized_keys 
</pre>

Place the public key you created in this file, then save and exit.

Now back to the ACTION!

## Updates and Dependencies

`apt update && apt full-upgrade -y`

Next, we need to install the cloud-init package to enable the cloud provider to automatically configure the server for us.

<pre>
apt install -y cloud-init

sh -c "echo 'datasource_list: [ DataSourceConfigDrive, DigitalOcean, Nocloud, None ]' > /etc/cloud/cloud.cfg.d/99_digitalocean.cfg"

systemctl enable cloud-init --now
</pre>

And of course we need to install the open ssh package in order to enable remote acces to the server.

`apt install -y openssh-server && systemctl enable ssh.service --now`

For custom images, we must remove the root password and create a root ssh folder.

<pre>
passwd -d root

mkdir -p /root/.ssh/
</pre>

Now cleanse your palate and cut the lights off!

<pre>
apt autoremove

apt autoclean

rm -rf /var/log/*

history -c

poweroff
</pre>


[Turn the page.](deploying-vps.md)