# NextCloud-on-BeagleBone
Making BeagleBone compatible with NextCloud


Starting Point:
->Setting up the BBB to connect to the Laptop using a serial connection.

->Installation of NextCloud 


Feb 8/9
Previously installed OS -Debian 7.8 
->Upgrade from 7.8  wheezy to 8.11 Jessie
-apt-get update
-apt-get upgrade

Change the /etc/sources.list all from wheezy to Jessie

-apt-get update
-apt-get upgrade
-apt-get dist-upgrade
-apt-get autoremove

Done.

Problems faced
Space running out in BBB.


Step 2:-
Downloading NextCloud and Unzipping it
 ->wget https://download.nextcloud.com/server/releases/nextcloud-11.0.1.zip
 ->unzip nextcloud-11.0.1.zip
 
 
 
 PROBLEMS
 Accidently ended up overwritting the eMMC.Lost all the important data and codes.No backup was taken.
 
 
 New Steps:-
 
 1)Flashing a new OS in the BBB.For now.
 
 Done with that
 Setting up Internet Connection in Beaglebone using USB tethering:-
 
 By default the BBB takes up the IP Adress 192.168.7.2 when we ssh into it.
 We need to assign 192.168.7.1 to USB Ethernet Device,(which can be found by running ipconfig on the host system)
 In my case it was enx1cba8cf07926 and route all packets from the BBB to this device using wireless connection which 
 again can be found from the ipconfig output and which in my case was wspln0
 
 Run the following commands on the host system
 
 sudo ifconfig enx1cba8cf07926 192.168.7.1
 sysctl net.ipv4.ip_forward=1
 iptables --table nat --append POSTROUTING --out-interface wlp2s0 -j MASQUERADE
iptables --append FORWARD --in-interface enx1cba8cf07926 -j ACCEPT


Run the following in the BBB terminal
route add default gw 192.168.7.1
echo "nameserver 8.8.8.8" >> /etc/resolv.conf

Moving to the start phase all over again 



