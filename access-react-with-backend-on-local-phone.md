# Access your React and Backend application on your local phone

## If your on LxQT - you preinstalled Firewalld


## Setup your React and Backend on public zones
1. Open GUI Firewalld
2. Select Zones tab and select public.
3. On Ports tab, add your React port like 3030 and the protocal is tcp
3. Add your Backend port like 3000 and the protocal is tcp

## Access your application on local phone with your local ip address
1. Find your wireless lan connection with (wlan# or example wlan0)
2. Open a terminal and write `ifconfig` and find the inet of wlan0 my ip address is 192.168.1.7
3. On your phone, open a mobile browser and access your local ip address with React port. Sample http://192.168.1.7:3030
4. I hope this tutorial helps you and happy coding!
