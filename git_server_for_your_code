{name}Branko Straub{/name}{company}Microsoft{/company}{title}Сервер Git для вашего кода{/title}{cat}2{/cat}{date}30.03.2016{/date}{desc}В этой статье вы узнаете как создать сервер Git в Azure{/desc}

##Конфигурация сервиса Azure

Сначала мы займемся созданием нашей виртуальной машины на платформе Azure. В портале управления Azure ("Azure Management Portal") мы переходим по пунктам меню New > Compute > From Gallery ("Новый > Расчет > Из галереи"). 
![1](https://c.s-microsoft.com/ru-ru/CMSImages/git_1.png?version=f87c8bb8-ef49-e4a9-0276-6f4f8afe0816)

При изучении данного предмета мы остановим свой выбор на операционной системе **Ubuntu** версии **12.04 LTS** (Long Term Support) 
![2](https://c.s-microsoft.com/ru-ru/CMSImages/git_2.png?version=e674913d-1274-fa52-d69d-3df7d2accaaf)

Нам необходимо ввести требуемые данные: имя входа в систему, наименование машины, размер и т.д. 
![3](https://c.s-microsoft.com/ru-ru/CMSImages/git_3.png?version=4a81c315-6e1c-a2c8-a0af-b1a2f2833427)

##Конфигурация виртуальной машины

Как только виртуальная машина будет создана, я воспользуюсь утилитой PuTTY для выполнения удаленного подключения к терминалу моей виртуальной машины Ubuntu. 

[http://www.chiark.greenend.org.uk/~sgtatham/putty/download.html](http://www.chiark.greenend.org.uk/~sgtatham/putty/download.html)

![4](https://c.s-microsoft.com/ru-ru/CMSImages/git_4.png?version=1cb5ef09-33e5-4073-c432-de08688ea697)

Мы открываем утилиту PuTTY и вводим ранее выбранные IP-адрес или имя DNS: 
![5](https://c.s-microsoft.com/ru-ru/CMSImages/git_5.png?version=bbb5a9fa-27d6-bf89-479b-70213ea35584)

Если вы все сделали правильно, на экране появится предупреждение. Нажимаем "Yes" и идем дальше. 

![6](https://c.s-microsoft.com/ru-ru/CMSImages/git_6.png?version=1823a9f0-5ebc-69e7-aa49-67a4cb0bf7ce)
Теперь на экране появится запрос на ввод имени пользователя, а затем – ключа доступа; я использую в качестве имени пользователя "azureuser", а в качестве ключа доступа – нажатие клавиши [Symbol] 

![7](https://c.s-microsoft.com/ru-ru/CMSImages/git_7.png?version=332ef03f-151a-5594-67b1-c191c972da46)
Как только соединение будет успешно установлено, мы наберем следующие команды (в порядке, в котором они здесь перечислены): 

    sudo apt-get update 
    sudo apt-get dist-upgrade 
    sudo apt-get install git-core 
    $ azure login

Если в процессе выполнения любой из этих команд на экране появится запрос на подтверждение, введите "Y", а затем нажмите клавишу ввода. 
![8](https://c.s-microsoft.com/ru-ru/CMSImages/git_8.png?version=392d3fa3-bfb9-1a8c-101d-927ae496c978)
![9](https://c.s-microsoft.com/ru-ru/CMSImages/git_9.png?version=a7d54a6d-a8d2-61a5-61cf-039814108bf1)
Эти команды выполняют обновление вашей системы с последующей загрузкой сервера GIT. 

Затем мы запустим следующую команду: 

    sudo -s 
    adduser git #(нам будет предложено ввести данные пользователя)
    su azureuser #(мы выполним вход в систему под именем azureuser)
![10](https://c.s-microsoft.com/ru-ru/CMSImages/git_10.png?version=4acc351b-1ca4-0505-d082-cd9a8e085fec)
![11](https://c.s-microsoft.com/ru-ru/CMSImages/git_11.png?version=45ab27bc-68e7-b107-7ceb-cc8be41d83e4)

Как только данный этап будет завершен, мы продолжим работу, вводя следующие команды: 

    mkdir ~/repositories 
    sudo apt-get install acl 
    chmod 700 ~/repositories 
    sudo chown git:git ~/repositories

![12](https://c.s-microsoft.com/ru-ru/CMSImages/git_12.png?version=db7dc3fb-0b12-a135-14c9-bb7fab314702)

А теперь введем вот эти команды: 

    getfacl ~/repositories 
    sudo ln -s /home/$USER/repositories /git 
    ls -al /git

После завершения ввода всех указанных команд вам потребуется загрузить генератор ключей PuTTY ("PuTTY Key Generator"), который будет использоваться для аутентификации нашего подключения к виртуальной машине, а также, после того как такая аутентификация будет проведена – для проверки достоверности подключения к нашему Git-репозиторию. 

[http://www.chiark.greenend.org.uk/~sgtatham/putty/download.html](http://www.chiark.greenend.org.uk/~sgtatham/putty/download.html)

![13](https://c.s-microsoft.com/ru-ru/CMSImages/git_13.png?version=4df2c82a-c808-35f5-3556-479a2e8a0e93)

Мы запускаем генератор ключей и нажимаем кнопку Generate ("Генерировать"): 
![14](https://c.s-microsoft.com/ru-ru/CMSImages/git_14.png?version=a9f8a8cc-c0b2-7d0c-1b2e-eb3d57ae8803)

Для генерирования случайного ключа вам будет предложено выполнить движение мышью: 
![15](https://c.s-microsoft.com/ru-ru/CMSImages/git_15.png?version=453531b7-82a3-4dd8-5543-2cf943a9eb22)


Мы вводим пароль, а затем сохраняем секретный ключ: 
![16](https://c.s-microsoft.com/ru-ru/CMSImages/git_16.png?version=99d29d62-29a7-ece6-688c-5b4e19df15ec)

Сохраните свой секретный ключ на рабочем столе и скопируйте открытый ключ доступа: 
![17](https://c.s-microsoft.com/ru-ru/CMSImages/git_17.png?version=38801ed4-24ff-6caa-9b3f-e750602e9cb9)

Мы возвращаемся к нашему подключению к удаленному терминалу и запускаем следующую последовательность команд:

    sudo -s 
    mkdir /home/git/.ssh 
    echo "ssh-rsa 
    AAAAB3NzaC1yc2EAAAABJQAAAQEAp7c7YmVnqeHAtiDBmpoJ3TdlH0RzgXzVu89FNN5qbqgZtnHAmqmTWqtn2lrwcuZncAAdQZ7zjW6KI/7W3TYVu8WsFQbfm5puKq0jNGyPNs0IdukDmVnBNniHaC/cXwmgNbw12puuzFFKXlICIiZ9NDUWG9+3m8JkxaZc6jZajj6ZVZqA/K6HdXX3aUD38jmQmT7J5eleAskZa2H/st6gmBBI7kUranhJuvBBhiQaNQyRRD4CRGHrAEMzy1Zxh5d5Y/4nFHjxldS+tDmTG6Ki4g0MZwUCa8s7cH7ZGWgAlGNd+UcWUsRb4cU6GMLVTeHCwb81Odkof7rdkOAC7MQVGQ== rsa-key-20141018" >> /home/git/.ssh/authorized_keys

* Замените ключ на ваш собственный открытый ключ доступа. 
![18](https://c.s-microsoft.com/ru-ru/CMSImages/git_18.png?version=28b8408e-dc83-f50f-bb2b-75f589089dbe)

Завершите сеанс PuTTY. Теперь нам следует создать новое подключение. 

Давайте откроем пункт меню Advanced Options ("Расширенные опции"), затем Connection ("Подключение"), а затем – SSH > Auth ("SSH > Авторизация"). 

Давайте теперь нажмем кнопку Browse ("Просмотр") и выберем ранее сохраненный нами секретный ключ доступа: 
![19](https://c.s-microsoft.com/ru-ru/CMSImages/git_19.png?version=35ede639-1ad4-153a-976e-be9f8f2a8c10)

Как только мы выполним эту последовательность действий, мы увидим, что вошли в систему под именем "git"; в качестве ключа доступа, запрашиваемого системой, необходимо использовать ключ, который помог нам при генерировании нашего открытого ключа доступа (с помощью генератора ключей PuTTY): 
![20](https://c.s-microsoft.com/ru-ru/CMSImages/git_20.png?version=58fa65ef-0eb8-abe2-7353-21b02812e387)

Наконец, мы запускаем следующую последовательность команд: 

    cd /git 
    git init --bare myrepo.git

Настройки вашего ПК 

Давайте установим следующие программы: 

[http://msysgit.github.io/](http://msysgit.github.io/)

[https://code.google.com/p/tortoisegit/wiki/Download?tm=2](https://code.google.com/p/tortoisegit/wiki/Download?tm=2)

![21](https://c.s-microsoft.com/ru-ru/CMSImages/git_21.png?version=485f60ed-98cb-083e-11a8-8fcdd9561335)
![22](https://c.s-microsoft.com/ru-ru/CMSImages/git_22.png?version=2a7832cd-1a63-cbca-7222-2f2ce2da4535)

Как только вы установите приложение TortoiseSVN, щелкните правой кнопкой мыши на папке и выберите опцию gitClon 
![23](https://c.s-microsoft.com/ru-ru/CMSImages/git_23.png?version=e2bae4b7-9e55-07f4-faf4-9053564bfaa9)

Мы вводим наше имя DNS, использующееся при работе с сервисом Azure, и выбираем наш предварительно сгенерированный секретный ключ доступа: 
![24](https://c.s-microsoft.com/ru-ru/CMSImages/git_24.png?version=a314cbc8-11fc-dfaa-cce0-f3e7174a0174)

Затем нам будет предложено ввести пароль, который мы выбрали ранее для этого ключа, и, наконец, нам потребуется ввести имя пользователя. Мы выбираем имя git: 
![25](https://c.s-microsoft.com/ru-ru/CMSImages/git_25.png?version=23b6f3fa-fc73-83b9-a420-eb30af5e7363)
![26](https://c.s-microsoft.com/ru-ru/CMSImages/git_26.png?version=969ad77e-dde9-cb0c-9c8a-9412fb669b39)

Спасибо за внимание; я надеюсь, что эта статья оказалась для вас полезной. 

Любые вопросы и замечания горячо приветствуются.

