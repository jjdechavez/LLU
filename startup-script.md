Create your script, example:
nvim /usr/local/sbin/my-script.sh

Turn it to excutable by:
sudo chmod +x /usr/local/sbin/my-script.sh

Create systemd service:
sudo nvim /etc/systemd/system/my-script.service
```
[Unit]
Description=Startup Local DynamoDB

[Service]
ExecStart=/home/{user}/.config/plasma-workspace/env/dynamo-java.sh

[Install]
WantedBy=multi-user.target
```

Check service running with:
sudo systemctl status my-script.service

Enable it:
sudo systemctl enable my-script.service

start it:
sudo systemctl start my-script.service
