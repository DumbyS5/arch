# arch


[Základní instalace]
pacstrap /mnt -K base linux linux-firmware sudo nano grub git networkmanager

pro amd
amd-ucode

pro intel
intel-ucode

sudo systemctl enable NetworkManager.service
sudo systemctl start NetworkManager.service

[GRUB]
https://wiki.archlinux.org/title/GRUB

UEFI
grub-install --target=x86_64-efi --efi-directory=esp --bootloader-id=GRUB

UEFI + sec. boot (ještě netestováno)
To make use of CA Keys the command is

grub-install --target=x86_64-efi --efi-directory=esp --bootloader-id=GRUB --modules="tpm" --disable-shim-lock
To make use of shim-lock the command is

grub-install --target=x86_64-efi --efi-directory=esp --bootloader-id=GRUB --modules="normal test efi_gop efi_uga search echo linux all_video gfxmenu gfxterm_background gfxterm_menu gfxterm loadenv configfile tpm"



[Pokračilá instalace]

pacman -S - < configure.txt
sudo systemctl enable sddm

