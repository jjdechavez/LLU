About SSH
- Secure Shell
- Networking Protocol
- Allows secure communications
- Can secure any network server
- Use to connect to server

To connect to the server with ssh
ssh username@serverhost

sample of serverhost: 
- 192.168.0.25
- 142.141.140.139
- junior.com
- example.com

SSH store on your .ssh folder

To create a new ssh use ssh-keygen -t rsa command.

To use the created ssh public key on server use ssh-copy-id root@serverhost command.

To setup ssh on your server
- on your local machine/host you need to create ssh with ssh-keygen -t rsa command
- copy the id_rsa.pub
- Theres 2 alternative way to copy the ssh id.pub
  1. You can use ssh-copy-id user@serverhost
  2. Store the id_rsa.pub on server ~/.ssh/authorized_keys folder 
    then use the command:
    cat ~/.ssh/id_rsa.pub | ssh demo@198.51.100.0 "mkdir -p ~/.ssh && chmod 700 ~/.ssh && cat >>  ~/.ssh/authorized_keys"
- Then your already setup!. You can connect to your server without password by using ssh that you generated!

Some tips:
- Copy file on your local host into your server
with scp ~/path-to-file/sample.txt user@serverhost:~/path-where-to-save/
sample: scp ~/test.txt jerald@192.168.3.29:~/Document
- When you have new server on digitalOcean 
  1. make sure to update the packages and software with sudo apt-get update && sudo apt-get upgrade -y
  2. create user with adduser command or check learn-user-groups-permission.txt file for more information.
    sample: adduser jerald
  3. Add/modify the created user on group sudo by usermod -aG <group-name> <user-name>
    sample: usermod -aG sudo jerald
  4. Try to connect on the server with ssh user:serverhost still failed because the stored authorized_keys is named/user was root not the created user
  5. Connect again as root on serverhost and mkdir .ssh and create authorized_keys file with mkdir .ssh && touch authorized_keys command.
  6. Paste again the id_rsa_do from localhost to serverhost .ssh/authorized_keys file
  7. try to connect the created user on serverhost. ssh jerald:192.168.3.29
  8. (Optional, but required) sudo nano /etc/ssh/sshd_config, then change yes to no the PermitRootLogin. (to avoid brute force attack)
  9. sudo systemctl reload sshd command to restart the sshd

  -Optional Step to connect to Github for cloning
  1. (Optional, but required) sudo chown -R jerald:jerald /home/jerald 
  2. create ssh for github by ssh-keygen -t rsa command. enter the file path /home/jerald/.ssh/id_rsa_github
  3. copy the id_rsa_github.pub to ssh github to access; then ssh-add /home/jerald/.ssh/id_rsa_github command to add the ssh identity
    - after the ssh-add and throws an error Could not open a connection to your authentication agent.
    - run the eval `ssh-agent -s` to activate the ssh-agent
    - run again the ssh-add /home/jerald/.ssh/id_rsa_github command; which return the Identity added: /home/jerald/.ssh/id_rsa_github
  4. you can clone the repo from github

  - Make sure the install nodejs on serverhost
  - To add the react project set to production
    1. run the build command of CRA with npm run build command
    2. remove the index.html on /var/www/html/index.html
    3. move the build react project on /var/www/html by sudo mv -v /home/jerald/sample-react/build/* /var/www/html/
    4. check on your browser with ip only without the port; sample 192.168.3.29 on browser and display the react project
    5. To add domain for the react project; Go to Networking DigitalOcean then make sure add the DNS record like ns1.digitalocean.com to ns3.digitalocean....
    6. Enter to the hostname just @ and will direct to droplet ubuntu/serverhost that created


Common Issue:
- When you already set the ssh id_rsa.pub on the hostserver and still you can't connect
  Make sure that you run ssh-add <file-path-id-private-key> command. sample: ssh-add ~/.ssh/id_rsa
