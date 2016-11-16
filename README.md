# spinner - кастомизация темы
# Запуск на Ubuntu 16.10 Server
* sudo apt-get install aptitude
* sudo aptitude install plymouth
* sudo aptitude install plymouth-themes-spinner - для подстраховки, он уже установлен
* подменить содержимое каталога /usr/share/plymouth/themes/spinner клоном git clone ...
* sudo update-alternatives --config default.plymouth - для подстраховки, если была установлена какая другая тема
* Изменяем файл: /etc/default/grub
  * GRUB_CMDLINE_LINUX_DEFAULT = "quiet splash"
  * GRUB_GFXMODE=640x480
* sudo update-grub2
* sudo update-initramfs -u
* перезагрузка

# Запуск на XUbuntu/Ubuntu
* sudo aptitude install plymouth plymouth-themes-all
* sed -i 's/quiet/quiet splash/g' /etc/default/grub
* plymouth-set-default-theme -l
* cd /usr/share/plymouth/themes/spinner
* заменить содержимое каталога клоном
* plymouth-set-default-theme -R spinfinity
* update-grub2
* update-initramfs -u
* перезагружаемся
* если не заработает, то в файле /etc/default/grub надо раскомментировать строчку в /etc/default/grub: GRUB_GFXMODE