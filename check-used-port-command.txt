
Run command:
sudo lsof -i -P -n | grep LISTEN

Which return:
systemd-r   936 systemd-resolve   13u  IPv4  29628      0t0  TCP 127.0.0.53:53 (LISTEN)
redis-ser  1131            root    6u  IPv4  33670      0t0  TCP 127.0.0.1:6379 (LISTEN)
sshd       1252            root    3u  IPv4  38066      0t0  TCP *:22 (LISTEN)
sshd       1252            root    4u  IPv6  38068      0t0  TCP *:22 (LISTEN)
apache2    1359            root    4u  IPv6  38211      0t0  TCP *:80 (LISTEN)
apache2    1385        www-data    4u  IPv6  38211      0t0  TCP *:80 (LISTEN)
