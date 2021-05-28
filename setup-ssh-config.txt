SSH Configuration

Create a file config on ~/.ssh/config

Then paste this:

# PERSONAL
Host personal
   HostName github.com
   User git
   IdentityFile ~/.ssh/personal_rsa

# WORK
Host work
   HostName gitlab.com
   User git
   IdentityFile ~/.ssh/work_rsa

Just update the IndentifyFile to assign the private ssh-key

To test it out:
ssh -T personal

Hi johndoe! You've successfully authenticated

ssh -T work

Welcome to GitLab, @johndoe!
