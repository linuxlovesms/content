{name}Victor Gurylev{/name}{company}Intel{/company}{title}Настройка платы Intel Edison для Microsoft Azure IoT suite{/title}{cat}1{/cat}{date}28.03.2016{/date}{desc}В этом руководстве будет рассказано, как подключить плату Intel Edison к облачному сервису Microsoft Azure.{/desc}

![pic_title](https://habrastorage.org/files/655/3e6/b79/6553e6b797824cbba34ba93d082e7a4c.jpg)
Проверьте, что у вас установлена последняя версия образа на Intel Edison. Для этого следуйте [инструкциям](https://software.intel.com/en-us/iot/library/edison-getting-started) на сайте Intel. После этого вам надо будет [настроить последовательное соединение](https://software.intel.com/en-us/setting-up-serial-terminal-intel-edison-board). Затем вы сможете выполнить установку Azure IoT SDK, используя наши инструкции.
Перед тем, как начнёте:

- Настройте плату, используя configure_edison --setup
- Убедитесь, что плата Intel Edison находится в той же Wi-Fi сети.

Обратите внимание, что в соответствии с [инструкциями Microsoft](https://github.com/Azure/azure-iot-sdks/blob/master/c/doc/devbox_setup.md) для сборки Azure IoT SDK для Linux требуется cmake версии 3.x или выше.

##Установка Git на Intel Edison

Git это распределённая система контроля версий. Её надо будет установить, чтобы клонировать Azure IoT SDK и построить его локально. Для этого надо установить пакеты, которые включают Git. Intel Edison основанный на [Yocto](http://www.yoctoproject.org/docs/latest/adt-manual/adt-manual.html), использует менеджер пакетов opkg и по умолчанию не включает поддержку Git.

На Intel Edison в файл /etc/opkg/base-feeds.conf добавьте следующие строки:

`src/gz all http://repo.opkg.net/edison/repo/all`

`src/gz edison http://repo.opkg.net/edison/repo/edison`

`src/gz core2-32 http://repo.opkg.net/edison/repo/core2-32`

Это можно сделать, например, через встроенный редактор vi. 
`$ vi /etc/opkg/base-feeds.conf`

Если вы раньше не работали с vi, можете посмотреть [инструкции](https://www.cs.colostate.edu/helpdocs/vi.html). Если не можете выйти из программы, не поддавайтесь панике и не нажимайте Reset, просто нажмите Esc, затем «SHIFT»+«:» и напечатайте wq. Так вы сохраните текущий файл и выйдите из программы.

Затем обновите базу opkg:
`$ opkg update`


Вы должны увидеть следующее:

![pic1](https://habrastorage.org/files/b3f/751/88c/b3f75188cc7f432cb85b3c70a1c6f26c.jpg)

##Загрузка Azure IoT SDK на плату Intel Edison

Используйте Git на Intel Edison для клонирования репозитория Azure SDK следующими командами. Мы рекомендуем использовать папку по умолчанию /home/root:
`$ opkg install git`

`$ git clone git@github.com:Azure/azure-iot-sdks.git`

Если вас попросят добавить ключ RSA на ваше устройство, ответьте «yes».

##Альтернативный метод установки

Если по какой-либо причине вы не можете клонировать Azure IoT SDK непосредственно на вашу плату, сначала клонируйте репозиторий на ваш компьютер, а затем передайте файлы по сети на плату Intel Edison с использованием [FileZilla](https://filezilla-project.org/) или SCP.

Если вы используете FileZilla, определите адрес платы командой:
`wpa_cli status`

Используйте «sftp://адрес_платы», пользователя «root» и пароль от платы, чтобы установить соединение SFTP c FileZilla. После того, как вы это сделаете, вы можете копировать файлы непосредственно через сеть, используя drag-and-drop.

![enter image description here](https://habrastorage.org/files/0ff/a95/9e6/0ffa959e674b406dbade1b8b729b2661.png)

##Постройка Azure IoT SDK на Intel Edison

Надо убедиться, что Azure IoT SDK установлен правильно. Для этого надо построить приложение, основанное на SDK. Возьмем С-пример AMQP (AMQP – протокол обмена) и поменяем в нём параметры, чтобы они соответствовали нашему Azure IoT Hub и всё работало после сборки.
В файле /c/iothub_client/samples/iothub_client_sample_amqp/iothub_client_sample_amqp.c замените параметры в строке connectionString вашей информацией, как показано ниже (static const char* ….). Обязательно это сделайте, иначе пример не заработает.

`static const char* connectionString = “HostName=[YOUR-HOST-NAME];CredentialType=SharedAccessKey;CredentialScope=Device;DeviceId=[YOUR-DEVICE-ID];SharedAccessKey=[YOUR-ACCESS-KEY];`


В терминале зайдите в /c/build_all/linux и выполните следующие шаги:

`$ opkg install util-linux-libuuid-dev`

`$ ./build_proton.sh`

`$ ./build.sh`


##Обновите ldconfig кеш

Ещё нам надо построить [Qpid Proton](http://qpid.apache.org/releases/qpid-proton-0.5/) – библиотеку для посылки сообщений. И перед тем как мы выполним тестирование и постройку нашего примера на C, надо зарегистрировать полученную библиотеку при помощи [ldconfig](http://codeyarns.com/2014/01/14/how-to-add-library-directory-to-ldconfig-cache/). Чтобы это сделать, нам надо для начала выяснить, где находится библиотека Proton и затем скопировать её в папку /lib в Yocto.

Добавьте libqpid-proton.so.2 к разделяемым библиотекам. Для этого надо её найти, запустив в терминале следующую команду:

`$ find -name 'libqpid-proton.so.2'`
Скопируйте имя найденной директории в буфер обмена.

Замените [directory_to_libqpid-proton.so.2] результатом команды поиска из первого шага:
`$ cp [directory_to_libqpid-proton.so.2] /lib`


Эта команда автоматически обновит кэш:
`$ ldconfig`

Проверьте:
`$ ldconfig -v | grep "libqpid-p*"`

Если вы выполнили все операции правильно, то увидите в списке «libqpid-proton.so.2»
Мы добавили Qpid Proton к ldcache и можем построить пример С-проекта, основанного на Proton’е:

Вернитесь в папку /c/iothub_client/samples/iothub_client_sample_amqp/iothub_client_sample_amqp/linux
Запустите 
`make -f makefile.linux`

Затем 
`./iothub_client_sample_amqp`


Результат должен быть следующим:

`# ./iothub_client_sample_amqp 
hub_client/samples/iothub_client_sample_amqp/linux#
Starting the IoTHub client sample AMQP... 
IoTHubClient_SetNotificationCallback...successful.
IoTHubClient_SendTelemetryAsync accepted data for transmission to IoT Hub.
IoTHubClient_SendTelemetryAsync accepted data for transmission to IoT Hub.
IoTHubClient_SendTelemetryAsync accepted data for transmission to IoT Hub.
IoTHubClient_SendTelemetryAsync accepted data for transmission to IoT Hub.
IoTHubClient_SendTelemetryAsync accepted data for transmission to IoT Hub.
Press any key to exit the application.
Confirmation[0] received for message tracking id = 0 with result =
IOTHUB_CLIENT_CONFIRMATION_OK
Confirmation[1] received for message tracking id = 1 with result =
IOTHUB_CLIENT_CONFIRMATION_OK
Confirmation[2] received for message tracking id = 2 with result =
IOTHUB_CLIENT_CONFIRMATION_OK
Confirmation[3] received for message tracking id = 3 with result =
IOTHUB_CLIENT_CONFIRMATION_OK
Confirmation[4] received for message tracking id = 4 with result =
IOTHUB_CLIENT_CONFIRMATION_OK`
