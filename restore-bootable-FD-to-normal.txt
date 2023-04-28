1. Open your terminal then type gnome-disks
2. Locate your FD and make sure check the device /dev/sdc
   -> command sudo fdisk -l
   (then locate your FD based on memory and get the dev loc)
3. unmount your FD sudo unmount /dev/sdc* (Optional)
4. sudo wipefs --all /dev/sdc (the FD device loc)
5. To create partition of FD sudo cfdisk /dev/sdc
6. Pick dos, new, primary, write(able to write to the FD), type yes and quit
7. Turn the FD to vfat and rename it with
   -> sudo mkfs.vfat -n 'Name of the FD' /dev/sdc1
   (because one we have partion the FD)
