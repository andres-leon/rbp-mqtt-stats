# rbp-mqtt-stats
Allow Raspberry Pies to publish system data to a MQTT broker via a single Python script.

# STEP 1 - Update your Pi and then  install all needed dependencies

sudo apt-get update

sudo apt-get upgrade

sudo apt-get install build-essential python-dev python-pip

sudo pip install paho-mqtt

sudo pip install psutil

# STEP 1.a Reboot

sudo reboot

# STEP 2 - Copy the systemdata.py file

# STEP 3 - Run the file and make sure your see data printed on the terminal as a valid JSON dictionary.

python /home/pi/systemdata.py

it should output something like this:

{"datetimedatacollected": "2016-11-04 14:23:39", "cpuusage": 2.3, "virtualmem": 15.8, "boottime": "2016-11-04 11:33:47", "cputemp": 132.8, "diskusage": 38.6}

# STEP 4 - add the script as a cron job

sudo crontab -e

*/5 * * * * python /home/pi/systemdata.py

The above runs the script every 5 minutes. 
