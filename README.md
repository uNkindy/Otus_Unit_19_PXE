### Домашнее задание №19 (PXE)
1. Подняты 2 виртуальные машины (ВМ): pxeserver, pxeclient. Vagrantfile взят из репозитория (virtlab/centos_pxe);
2. Написан [playbook](https://github.com/uNkindy/Otus_Unit_19_PXE/blob/main/playbook.yml), конфигурирующий ВМ pxeserver:
- устанавливаются необходимые репозитории;
- устанавливается необходимый пакет ПО на pxeserver (wget, epel-release, httpd, tftp-server, dhcp-server);
- скачивается образ CentOS-8.4.2105-x86_64-dvd1.iso;
- монтируется образ, копируются файлы в созданную диреторию /iso;
- копируется файл конфигурации hhtpd, запускается сервис httpd;
- создается tftp директория, туда копируется файл default (pxeserver munu);
- копируются необходимые для работы pxeserver в tftp сервер;
- запускается tftp сервер;
- копируется файл конфигурации dhcp и запускается сервер dhcp;
- копируется kick start file.