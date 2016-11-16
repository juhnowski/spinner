# spinner
������ �� Ubuntu 16.10 Server
1) sudo apt-get install aptitude
2) sudo aptitude install plymouth
3) sudo aptitude install plymouth-themes-spinner - ��� ������������, �� ��� ����������
4) ��������� ���������� �������� /usr/share/plymouth/themes/spinner ������ git clone ...
5) sudo update-alternatives --config default.plymouth - ��� ������������, ���� ���� ����������� ����� ������ ����
6)  �������� ����: /etc/default/grub
  GRUB_CMDLINE_LINUX_DEFAULT = "quiet splash"
  GRUB_GFXMODE=640x480
7) sudo update-grub2
8) sudo update-initramfs -u
9) ������������

������ �� XUbuntu/Ubuntu
1) sudo aptitude install plymouth plymouth-themes-all
2) sed -i 's/quiet/quiet splash/g' /etc/default/grub
3) plymouth-set-default-theme -l
4) cd /usr/share/plymouth/themes/spinner
�������� ���������� �������� ������
5) plymouth-set-default-theme -R spinfinity
6) update-grub2
7) update-initramfs -u
8) ���������������

���� �� ����������, �� � ����� /etc/default/grub ���� 
����������������� �������:
GRUB_GFXMODE