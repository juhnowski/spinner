# spinner
Запуск на Ubuntu 16.10 Server
1) sudo apt-get install aptitude
2) sudo aptitude install plymouth
3) sudo aptitude install plymouth-themes-spinner - для подстраховки, он уже установлен
4) подменить содержимое каталога /usr/share/plymouth/themes/spinner клоном git clone ...
5) sudo update-alternatives --config default.plymouth - для подстраховки, если была установлена какая другая тема
6)  Изменяем файл: /etc/default/grub
  GRUB_CMDLINE_LINUX_DEFAULT = "quiet splash"
  GRUB_GFXMODE=640x480
7) sudo update-grub2
8) sudo update-initramfs -u
9) перезагрузка

Запуск на XUbuntu/Ubuntu
1) sudo aptitude install plymouth plymouth-themes-all
2) sed -i 's/quiet/quiet splash/g' /etc/default/grub
3) plymouth-set-default-theme -l
4) cd /usr/share/plymouth/themes/spinner
заменить содержимое каталога клоном
5) plymouth-set-default-theme -R spinfinity
6) update-grub2
7) update-initramfs -u
8) перезагружаемся

если не заработает, то в файле /etc/default/grub надо 
раскомментировать строчку:
GRUB_GFXMODE