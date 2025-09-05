## I installed Ubuntu os faced issues with GRUB.
#### After installation os is not booting with disk
#### I tried with changin booting option, but it not showing any booting device
sudo fdisk -l
sudo mount /dev/sdXZ /mnt/boot/efi
for i in /dev /dev/pts /proc /sys; do sudo mount --bind $i /mnt$i; done
sudo chroot /mnt
grub-install --target=x86_64-efi --efi-directory=/boot/efi --bootloader-id=ubuntu
update-grub
exit
sudo reboot

## After installation success and booting with disk Os.
#### i am able to ping from my laptop, but connot able to do ssh
sudo systemctl status ssh
sudo apt update
sudo apt install openssh-server -y
sudo systemctl enable ssh
sudo systemctl start ssh
sudo systemctl status ssh
ssh username@192.168.1.100

