Reset lost root/administrative password
1. Boot up make sure hold Shift (or Esc) to open GRUB
2.  Recovery mode
3.  Choose Root
4. To change password of the user
  -> passwd <user>
  -> Enter the new password of the user
  -> Retype the new password

User removed on group sudo
1. Boot up make sure hold Shift (or Esc) to open GRUB
2. Recovery mode
3. Choose Root
4. Enter the usermod by
  (Note: "usermod" means modify a user account, "-a" a flag means append the user, "-G" G flag means group. * means example)
  -> usermod -a -G <group> <user>
    * usermod -a -G sudo jerald
