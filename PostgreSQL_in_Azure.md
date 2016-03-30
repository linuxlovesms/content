{name}J. Rodrigo Puca{/name}{company}Microsoft{/company}{title}База данных PostgreSQL на Linux{/title}{cat}0{/cat}{date}30.03.2016{/date}{desc}Сегодня мы расскажем об использовании PostgreSQL в Azure{/desc}

В данной статье мы опишем последовательность действий по установке базы данных PostgreSQL на виртуальной машине Microsoft Azure с дистрибутивом OpenSuse. 

![pic1](https://c.s-microsoft.com/ru-ru/CMSImages/postresqlazure_1.png?version=a443a5f4-0431-a51d-3d65-f6d7135bc639)

Перед началом каких-либо действий рекомендуется прочитать статью о том, как устанавливать виртуальную машину Linux на платформе Azure (вы можете прочитать об этом [здесь](http://www.microsoft.com/en-mt/azureboxes/lamp)). 

##Перед установкой

Перед установкой вам потребуется обеспечить наличие необходимых библиотек и других предварительных условий для работы с базой данных PostgreSQL. Для этого в консоли виртуальной машины выполните следующие команды:

`sudo zypper install make gcc readline-devel zlib-devel libxml2-devel`

![pic2](https://c.s-microsoft.com/ru-ru/CMSImages/postresqlazure_2.png?version=512756b2-b0b6-d720-28c4-9380e92fc126)

Мы можем также установить приложение 'wget', что обеспечит нам доступ к установочным пакетам:
`sudo zypper install wget`

![pic3](https://c.s-microsoft.com/ru-ru/CMSImages/postresqlazure_3.png?version=87ad7c1e-864a-f038-5d22-9be43fc878a8)

##Процедура установки

1) Загрузите [Установочные пакеты Postgres](http://ftp.postgresql.org/pub/source/) в локальную папку, используя для этих целей приложение [wget](https://www.gnu.org/software/wget/)
`azureuser@OSuse13:/> cd /usr/local `
`azureuser@OSuse13:/usr/local> sudo wget http://ftp.postgresql.org/pub/source/v9.3.4/postgresql-9.3.4.tar.gz`

2) Измените права доступа к загруженному файлу:
`azureuser@OSuse13:/usr/local> sudo chmod 777 postgresql-9.3.4.tar.gz`

![pic4](https://c.s-microsoft.com/ru-ru/CMSImages/postresqlazure_4.png?version=22ed0134-bc39-ea1b-5458-c23ea99449d2)

3) Распакуйте загруженный вами файл: 
`azureuser@OSuse13:/usr/local> sudo tar -zxvf postgresql-9.3.4.tar.gz`

![pic5](https://c.s-microsoft.com/ru-ru/CMSImages/postresqlazure_5.png?version=e511f0b3-8580-5ff8-6d64-5028a74e4549)

4) После того как содержимое файла будет распаковано, войдите в папку postgresql-9.3.4 
`azureuser@OSuse13:/usr/local> cd postgresql-9.3.4`

![pic6](https://c.s-microsoft.com/ru-ru/CMSImages/postresqlazure_6.png?version=c6c1dafd-3d83-8152-4e0c-535197293ad3)

5) Произведите конфигурирование пакета установки. Это можно сделать с помощью следующих команд: 
`azureuser@OSuse13:/usr/local/postgresql-9.3.4> ./configure `
`azureuser@OSuse13:/usr/local/postgresql-9.3.4> make `
`azureuser@OSuse13:/usr/local/postgresql-9.3.4> sudo make install`


![pic7](https://c.s-microsoft.com/ru-ru/CMSImages/postresqlazure_7.png?version=e9bfa6b9-e5a8-75b3-7e95-a2472fd03837)
![pic8](https://c.s-microsoft.com/ru-ru/CMSImages/postresqlazure_8.png?version=005fd4d8-6118-87fd-eeb1-4453d557f258)
![pic9](https://c.s-microsoft.com/ru-ru/CMSImages/postresqlazure_9.png?version=70c620fd-6478-4eea-2ea6-a95fb521ec4c)
![pic10](https://c.s-microsoft.com/ru-ru/CMSImages/postresqlazure_10.png?version=f7b357ca-654b-a8a6-8061-56723d2938a7)

6) Добавьте пользователя postgres и создайте для этого пользователя папку: 
`azureuser@OSuse13:/usr/local> sudo /usr/sbin/useradd postgres -p MiPASS `
`azureuser@OSuse13:/usr/local> sudo mkdir /home/postgres `
`azureuser@OSuse13:/usr/local> sudo chown postgres /home/postgres`

![pic11](https://c.s-microsoft.com/ru-ru/CMSImages/postresqlazure_11.png?version=3407c283-0ce4-fc9d-5c07-38315f648b7a)

7) Создайте данные подкаталога и обеспечьте пользователя postgres необходимыми правами доступа: 
`azureuser@OSuse13:/usr/local> sudo mkdir /usr/local/pgsql/data azureuser@OSuse13:/usr/local> sudo chown postgres /usr/local/pgsql/data`

![pic12](https://c.s-microsoft.com/ru-ru/CMSImages/postresqlazure_12.png?version=c1f9f38f-c60c-6f7c-51d6-0671f784992a)

8) Войдите в систему как пользователь postgres и запустите сервис с использованием команды initdb
`azureuser@OSuse13:/> su postgres `
`postgres@OSuse13:/> cd /usr/local/pgsql/bin` 
`postgres@OSuse13:/usr/local/pgsql/bin> ./initdb -D /usr/local/pgsql/data`

![pic13](https://c.s-microsoft.com/ru-ru/CMSImages/postresqlazure_13.png?version=bc1d6920-cf1b-3493-fcfa-b75a3498c50b)

9) Запустите сервер! 

Мы можем сделать это с использованием опции 'start' ("запуск") файла [pg_ctl](http://www.postgresql.org/docs/9.3/static/app-pg-ctl.html) с последующей проверкой состояния (команда 'status' ("состояние")) 
`postgres@OSuse13:/usr/local/pgsql/bin> ./pg_ctl start -D /usr/local/pgsql/data `
`postgres@OSuse13:/usr/local/pgsql/bin> ./pg_ctl status -D /usr/local/pgsql/data`

![pic14](https://c.s-microsoft.com/ru-ru/CMSImages/postresqlazure_14.png?version=b5884748-70b5-105e-e5ad-6057452303a2)

Вот и все!
