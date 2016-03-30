{name}Branko Straub{/name}{company}Microsoft{/company}{title}Как создать собственный Minecraft сервер{/title}{cat}4{/cat}{date}30.03.2016{/date}{desc}В данной статье показано, как создать свой собственный сервер Minecraft в Azure{/desc}

##Запуск сервера в облаке Azure
Прежде всего необходимо зарегистрировать действующую подписку Microsoft Azure. Если у вас ее нет, [подпишитесь](https://bit.ly/Azure_Trial_CEE_RU) на бесплатную пробную версию, следуя инструкциям по регистрации. Пробная версия Azure предоставляет кредит $ 200 на услуги Azure в течение месяца, но для этого потребуется ввести код своей действующей кредитной карты, чтобы подтвердить личность (со счета снимается плата в размере $ 1, которая позже возвращается на карту). 

Стартапы и студенты могут получить постоянный бесплатный доступ в Azure присоединившись к программам [Bizspark](http://www.microsoft.com/bizspark) или [Dreamspark](https://www.dreamspark.com/) соответственно. Обратите внимание, что, хотя служба SendGrid является бесплатной для рассылки до 25000 писем в месяц, Azure Marketplace все равно потребует ввести данные действующей кредитной карты. 

После настройки учетной записи перейдите в портал управления Azure ([https://manage.windowsazure.com/](https://manage.windowsazure.com/)) для создания собственного сервера. После входа в портал должен появиться следующий экран:

![1](https://c.s-microsoft.com/ru-ru/CMSImages/minecraft1.png?version=12b40c68-94c3-f40b-1084-55a55c170575)

Нажмите кнопку “New”, после чего появится следующий экран, а затем выберите Compute / **Virtual Machine**, и далее **From Gallery**. 

![2](https://c.s-microsoft.com/ru-ru/CMSImages/minecraft2.png?version=20e32168-b0ed-b2c5-3020-44700f8661c9)

Чтобы создать сервер Minecraft выбираем Windows Server 2008 R2 SP1 и переходим к следующему шагу. 

![3](https://c.s-microsoft.com/ru-ru/CMSImages/minecraft3.png?version=d6302037-e595-b00f-e263-9e01dc1f10d6)

Сейчас необходимо установить параметры сервера.
- **Name**: Имя сервера, в данном случае Minecraft.
- **Tier**: выбрать Standard. 
- **Размер**: Изменяется в зависимости от количества размещаемых на данном сервере процессов и количества подключенных игроков. Сервера категории А1 должно быть вполне достаточно.
- **User**: для подключения к серверу необходимо имя.
- **Password**: Пароль для подключения к серверу.

 ** *Note**: Пароль должен содержать по крайней мере одну заглавную букву, одну цифру и один специальный символ, например, "Minecraf1". 

![4](https://c.s-microsoft.com/ru-ru/CMSImages/minecraft4.png?version=495be4dd-f086-502f-e815-028e1e7fe8a9)

Теперь необходимо продолжить настройку других параметров сервера: 
- **DNS Name**: Адрес, к которому будут подключаться игроки. Лучше всего использовать общее и легко доступное название.
- **Region**: укажите расположение сервера. Чем ближе располагается сервер, тем лучше, поскольку это означает меньшее время задержки (пинг).

Другие настройки можно оставить по умолчанию. 
Наконец, необходимо открыть порт, с которого будет доступен сервер Minecraft. В данном случае открываем порт с использованием протокола TCP с номером 25565, как показано ниже. 

![5](https://c.s-microsoft.com/ru-ru/CMSImages/minecraft5.png?version=79314b23-766b-d76a-b098-a4ec6bac117f)
На следующем экране показано краткое описание конфигурации сервера, запрашивающее активацию специальных функций. Оставляем все как есть. На следующем экране показаны все виртуальные машины из списка. Если все сделано правильно, появится надпись "**creating the virtual machine**" (создание виртуальной машины) и через несколько минут виртуальная машина будет готова к использованию. 

![6](https://c.s-microsoft.com/ru-ru/CMSImages/minecraft6.png?version=492dc1d7-70e7-6f39-5ad1-3fe366cf48ba)

После ее создания нажмите на виртуальную машину и перейдите на страницу "**Endpoints**". 

![7](https://c.s-microsoft.com/ru-ru/CMSImages/minecraft7.png?version=d6664ebc-d727-5f38-00c9-ad66ec1a5714)

Выберите созданный порт и нажмите Edit. 
Теперь частный порт должен быть "25565", в то время как публичный порт будет отличаться по умолчанию. Необходимо поменять его, чтобы убедиться, что они одинаковые. Таким образом, внешний порт меняется на 25565 и принимаются изменения. Это займет несколько секунд. После завершения можно перейти к следующему шагу. 

![8](https://c.s-microsoft.com/ru-ru/CMSImages/minecraft8.png?version=90633cc7-b5bb-7f69-94e7-ed777ecdc267)

После смены порта можно подключиться к виртуальной машине. Для этого необходимо вернуться в раздел "virtual machines" (виртуальные машины), выбрать свое устройство и нажать "Connect" (Соединить). Загрузится файл RDP, позволяющий подключиться к вашему серверу. 

![9](https://c.s-microsoft.com/ru-ru/CMSImages/minecraft9.png?version=d2bceb91-06cf-7bab-2250-5b2a54d4942f)

Откройте его и см. мастер Windows для удаленных подключений: 

![10](https://c.s-microsoft.com/ru-ru/CMSImages/minecraft10.png?version=b341691e-853e-e1a8-ac9a-c9da1d308617)

Нажмите **"connect"** (подключить), затем введите учетные данные (выбранные при создании виртуальной машины имя пользователя и пароль). Выберите **"use another account"** (использовать другую учетную запись) и введите свои учетные данные. 

![11](https://c.s-microsoft.com/ru-ru/CMSImages/minecraft11.png?version=b6ca0bed-8cd5-7bb3-552e-94a0a0060ddb)

*Примечание: Появится предупреждение о безопасности, поэтому нажмите Yes (Да). 

##Настройка сервера Minecraft
После подключения появится рабочий стол виртуальной машины. 

![12](https://c.s-microsoft.com/ru-ru/CMSImages/minecraft12.png?version=bcc9f669-7d01-6211-8731-2b351893fe6d)

Откройте браузер и перейдите к скачиванию сервера Minecraft по следующей ссылке: [https://minecraft.net/download](https://minecraft.net/download). 

![13](https://c.s-microsoft.com/ru-ru/CMSImages/minecraft13.png?version=1079260a-4184-b06b-73d0-a13c0d108c2f)

После загрузки скопируйте его для удобства в папку с названием "Minecraft" на рабочем столе: 

![14](https://c.s-microsoft.com/ru-ru/CMSImages/minecraft14.png?version=6782e399-bd40-65bf-5b8c-7547c5e57ff6)

После завершения данного шага появится следующее сообщение. 

![15](https://c.s-microsoft.com/ru-ru/CMSImages/minecraft15.png?version=6aa6dd13-736f-3f9b-ad6d-0664b886e120)

Для работы сервера Minecraft требуется **Java** Поэтому после нажатия ОК в сообщении об ошибке начнется загрузка страницы Java в Вашем браузере. Скачайте приложение и установите его. 

После этого необходимо перейти к настройке Java, чтобы наше приложение работало корректно. Выполните следующие действия: 

![16](https://c.s-microsoft.com/ru-ru/CMSImages/minecraft16.png?version=1626fc69-99e6-4bbc-eea1-6e8d12975de3)

![17](https://c.s-microsoft.com/ru-ru/CMSImages/minecraft17.png?version=ced69549-21cb-7e08-77d5-b5b796939fad)

Откройте **Control Panel.**

![18](https://c.s-microsoft.com/ru-ru/CMSImages/minecraft18.png?version=1b0e8a90-b572-227b-e32f-a70dc37b446d)

Click “**System**”, “**Advanced System Settings**” после чего нажмите кнопку “**Environment variables**”

![18](https://c.s-microsoft.com/ru-ru/CMSImages/minecraft19.png?version=11ddad54-dda3-81c2-86b6-c25e95637d62)

Щелкните “**New**” и введите следующие данные: 
**Name**: JAVA_HOME 
**Value**: C:\Program Files (x86)\Java\jre7 
Нажмите OK, повторите те же действия в другом окне и закройте его, приняв изменения. 

![19](https://c.s-microsoft.com/ru-ru/CMSImages/minecraft20.png?version=a728fccc-c1c5-8fd9-a946-03c44202a4e7)

Вернитесь к инсталляции сервера Minecraft. 

![20](https://c.s-microsoft.com/ru-ru/CMSImages/minecraft21.png?version=6879bbbf-c21a-1636-c66e-82086a932430)

Установка запустится, а затем закроется, создав следующие файлы. 
Введите файл с именем "**EULA**" (Лицензионное соглашение) и измените значение последней строки с "**FALSE**" (ЛОЖЬ) на "**TRUE**" (ИСТИНА). Сохраните и закройте файл. 

![21](https://c.s-microsoft.com/ru-ru/CMSImages/minecraft22.png?version=d4ad77e0-659c-dc5d-0add-02c4467911b9)

Вернувшись и открыв сервер Minecraft, вы увидите следующее. 

![22](https://c.s-microsoft.com/ru-ru/CMSImages/minecraft23.png?version=cf351f21-b5de-480a-9dbf-bf8f8c810321)

Закройте сервер и посмотрите на недавно созданные файлы. 

![23](https://c.s-microsoft.com/ru-ru/CMSImages/minecraft24.png?version=2130d567-4bb9-07eb-71a0-f1a244e98feb)

Изменим файл "server.properties". Выберите второй вариант и нажмите "OK". Вы должны увидеть следующее окно: 

![24](https://c.s-microsoft.com/ru-ru/CMSImages/minecraft25.png?version=735f50aa-d4e7-1f90-859c-abe9b289fa60)

Выберите “**Notepad**” а затем “Ok”. 

![25](https://c.s-microsoft.com/ru-ru/CMSImages/minecraft26.png?version=becb6f96-785d-830f-fd11-5cf67445113c)

Отредактируйте следующий текстовый файл: 

![26](https://c.s-microsoft.com/ru-ru/CMSImages/minecraft27.png?version=29e649f3-4069-1d88-bbe5-c4551b9e082b)

В параметре "**online-mode = true**" измените "**true**" на "**false**" и введите в "**server-ip =**" параметр с IP-адреса в верхней правой части рабочего стола сервера экрана (используйте значение "Internal IP" (внутреннего IP)). Сохраните изменения и закройте файл. Другие варианты в файле являются конфигурацией сервера; их можно свободно изучать. 
*** Примечание**: Если выключить, а затем включить виртуальную машину (сервер), внутренний IP-адрес может измениться, и в результате придется повторить последний шаг обновления настроек IP. 

##Начинаем играть!
Убедитесь, что ваш сервер работает. 
Откройте клиент Minecraft. Выберите "**add server**" и добавьте публичный IP-адрес или доменное имя сервера. В моем случае это выбранный ранее IP: **minecraftprueba.cloudapp.net**

![27](https://c.s-microsoft.com/ru-ru/CMSImages/minecraft28.png?version=bca44568-2603-469c-7b55-48fd1d78b6b0)

Если все сделано правильно, появится следующее окно: 


![28](https://c.s-microsoft.com/ru-ru/CMSImages/minecraft29.png?version=96985db7-d04a-e06f-3487-0cc73f965aea)

Подключитесь к серверу, и перед вами появится статистика игрока. 

![29](https://c.s-microsoft.com/ru-ru/CMSImages/minecraft30.png?version=082866ec-9268-dc37-ead6-c629ad13fc6d)

![30](https://c.s-microsoft.com/ru-ru/CMSImages/minecraft31.png?version=974145c2-3dd0-6dbf-106c-a9968fbc9d26)
