#Linux на Azure - поддерживаемые дистрибутивы

Часть дистрибутивов, поддерживаемых в Azure, предоставляется партнёрами Microsoft, часть - сообществом. Для тех дистрибутивов, которых нет в галерее образов, можно воспользоваться [инструкцией](virtual-machines-linux-classic-create-upload-vhd.md) и загрузить подготовленный собственноручно образ. 

## Поддерживаемые дистрибутивы и версии ##

Linux Integration Services (LIS) для Hyper-V и Azure - модули, которые контрибьютятся Microsoft напрямую в upstream-kernel Linux. Эти драйвера могут встраиваться в ядро по умолчанию, либо, для старых дистрибутивов RHEL/CentOS загружаться [отдельно](http://go.microsoft.com/fwlink/?LinkID=403033&clcid=0x409). 

Azure Linux Agent уже предустановлен на образы из галереи Azure, исходные коды для него можно найти в соответствующем репозитории [GitHub](https://github.com/azure/walinuxagent).

Дистрибутив|Версия|Драйвер|Агент
---|---|---|---
CentOS by OpenLogic |CentOS 6.3+, 7.0+| CentOS 6.3: [LIS Download](http://go.microsoft.com/fwlink/?LinkID=403033&clcid=0x409)<p>CentOS 6.4+: In Kernel|Package: В <a href="http://olcentgbl.trafficmanager.net/openlogic/6/openlogic/x86_64/RPMS/">OpenLogic в "WALinuxAgent"<p><p>Исходники: [GitHub](https://github.com/Azure/WALinuxAgent)
[CoreOS](https://coreos.com/docs/running-coreos/cloud-providers/azure/)|494.4.0+ |In Kernel|Исходники: [GitHub](https://github.com/coreos/coreos-overlay/tree/master/app-emulation/wa-linux-agent)
Debian by Credativ |Debian 7.9+, 8.2+|In Kernel|Package: В репозитории в "waagent" <p><p>Исходники: [GitHub](https://github.com/Azure/WALinuxAgent)
Oracle Linux| 6.4+, 7.0+|In Kernel|Package: В репозитории в "WALinuxAgent"<p><p>Исходники: [GitHub](http://go.microsoft.com/fwlink/p/?LinkID=250998)
Red Hat Enterprise Linux |RHEL 6.7+, 7.1+|In Kernel|Package: В репозитории в "WALinuxAgent" <p><p>Исходники: [GitHub](https://github.com/Azure/WALinuxAgent)
SUSE Linux Enterprise |SLES 11 SP3+, SLES 12+ and  <p><p> SLES for SAP 11.3+ |In Kernel|Package: В [Cloud:Tools](https://build.opensuse.org/project/show/Cloud:Tools) в "WALinuxAgent"<p><p>Исходники: [GitHub](http://go.microsoft.com/fwlink/p/?LinkID=250998)
openSUSE |openSUSE 13.1+|In Kernel|Package: In [Cloud:Tools](https://build.opensuse.org/project/show/Cloud:Tools) в "WALinuxAgent" <p><p>Исходники: [GitHub](https://github.com/Azure/WALinuxAgent)
Ubuntu|Ubuntu 12.04, 14.04, 15.10 and 16.04|In Kernel|Package: В репозитории в "walinuxagent" <p><p>Исходники: [GitHub](https://github.com/Azure/WALinuxAgent)
## Партнеры

### OpenLogic
[http://www.openlogic.com/azure](http://www.openlogic.com/azure)

### CoreOS
[https://coreos.com/docs/running-coreos/cloud-providers/azure/](https://coreos.com/docs/running-coreos/cloud-providers/azure/)


### Credativ
[http://www.credativ.co.uk/credativ-blog/debian-images-microsoft-azure](http://www.credativ.co.uk/credativ-blog/debian-images-microsoft-azure)

### Oracle
[http://www.oracle.com/technetwork/topics/cloud/faq-1963009.html](http://www.oracle.com/technetwork/topics/cloud/faq-1963009.html)

### Red Hat
[http://www.redhat.com/en/partners/strategic-alliance/microsoft](http://www.redhat.com/en/partners/strategic-alliance/microsoft)

### SUSE
[http://www.suse.com/suse-linux-enterprise-server-on-azure](http://www.suse.com/suse-linux-enterprise-server-on-azure)

### Canonical
[http://www.ubuntu.com/cloud/azure](http://www.ubuntu.com/cloud/azure)
