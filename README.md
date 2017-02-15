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

