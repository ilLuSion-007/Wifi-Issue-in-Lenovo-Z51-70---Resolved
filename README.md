# Wifi-Issue-in-Lenovo-Z51-70---Resolved

Wifi is not working away at new releases of linux distro's in Lenovo's Z51-70 and it is a step wise guidance to resolve the Wifi Issue in Lenovo Z51-70.

1. Download the tar.gz file named Wifi-70 from this link - <a href="https://1drv.ms/u/s!AhwCxtlb048AhEHjD37uuzUbkjhi" target="_blank">Wifi70.tar.gz</a> else from github clone or zip directly !

2. Extract the tar.gz file in your desired location/directory
(eg. /home directory)

tar -xzvf Wifi-70.tar.gz -C /home 

(input filename accordingly in terminal as per your downloaded file)

3. Go to the folder named - backports-20150731 in Wifi-70 directory through terminal (if it's internal content in zip file then extract them unless directly run) ; Just right click the folder and open in terminal
Then run the following command (We are just trying to compile the code here)

sudo make install

4. Once this is done go to the folder named ath10k-firmware-master in Wifi-70
Then run the following below commands

sudo cp -R ath10k/ /lib/firmware/

sudo bash -c 'echo "options ath10k_core skip_otp=y" > 
/etc/modprobe.d/ath10k.conf'

5. Now reboot the system. After reboot run the following command.
(it will throw error if you run without reboot)

sudo modprobe ath10k_pci
