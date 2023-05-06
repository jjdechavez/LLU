To get a list of all listening TCP ports with lsof type:
sudo lsof -nP -iTCP -sTCP:LISTEN

The options used are as follows:
  -n - Do not convert port numbers to port names.
  -p - Do not resolve hostnames, show numerical addresses.
  -iTCP -sTCP:LISTEN - Show only network files with TCP state LISTEN.

Check particular Port:
sudo lsof -nP -iTCP:3306 -sTCP:LISTEN

Use netstat - To locate specific port
sudo netstat -ap | grep <PORT>

Sample
sudo netstat -ap | grep 8123
tcp        0      0 localhost:8123          0.0.0.0:*               LISTEN      9257/node


To kill the port
kill <pid> which locate with /... from the sample it is 9257


Sample to kill port
kill 9257
