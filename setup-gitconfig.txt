Git Configuration

To setup git config you can use:
git config --global user.name "John Doe"
git config --global user.email johndoe@example.com

Then it atomatically create on your home directory as .gitconfig
cat .gitconfig

[user]
        email = johndoe@example.com
        name = John Doe


We can set alias on git config by:

[alias]
        email = config --global user.email
        personal = config --global user.email johndoe@example.com
        work = config --global user.email johndoe.work@example.com


email - meaning display the set git user email result: johndoe@example.com
peronal - meaning display the set personal git user email result: johndoe@example.com
work - meaning display the set work git user email result: johndoe.work@example.com

Display the .gitconfig 
cat .gitconfig

[user]
        email = johndoe@exaple.com
        name = John Doe
[alias]
        email = config --global user.email
        personal = config --global user.email johndoe@example.com
        work = config --global user.email johndoe.work@example.com
