About User (user means: name of the user)
1. Add to user - sudo adduser user (ask for password)
2. Delete user - sudo userdel user
3. See all the user - view /etc/passwd
4. Change password - sudo passwd
5. Change user - su - (username)

About Groups
1. Add to group - sudo groupadd samplegroup
2. Delete group - sudo groupdel samplegroup
3. Add user on group - sudo adduser username samplegroup
4. Remove the user on group - sudo deluser username:samplegroup
5. groups files info - view /etc/group

About Permissions (777)
7 - owner, 7 - group, 7 - everyone
4 - read, 2 - write, 1 - execute, 0 - nothing

1. change permission - sudo chmod 755 filename/folder -R

About Ownership
1. change the ownership of file/folder - sudo chown -R user file/folder
2. change group permission - sudo chgrp -R groupname file/folder

Reference:
https://www.youtube.com/watch?v=zRw0SKaXSfI
