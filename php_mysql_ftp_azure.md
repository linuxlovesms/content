{name}Marcelo Felman{/name}{company}Microsoft{/company}{title}Создание веб-сайта с использованием технологий PHP, MySQL и FTP{/title}{cat}2{/cat}{date}30.03.2016{/date}{desc}В этой статье мы узнаем, как создать облачный веб-сайт всего за 15 минут{/desc}

В этой статье мы узнаем, как создать облачный веб-сайт всего за 15 минут с использованием простой последовательности шагов, приведенных ниже. 

Если у вас еще нет подписки на сервис Azure, вы можете подписаться на [бесплатную пробную версию](https://bit.ly/Azure_Trial_CEE_RU) и получить ресурсы Azure на 200 долларов США в течение месяца. 

Итак. Когда ваша учетная запись будет активирована, войдите на портал Azure по адресу: 

[https://manage.windowsazure.com](https://manage.windowsazure.com/)

Как только вход будет выполнен, вы увидите нечто подобное показанному ниже – просто, наверное, у вас список в окне будет поменьше (у меня уже активировано много сервисов). 

![pic1](https://c.s-microsoft.com/ru-ru/CMSImages/sitiowebphp_1.png?version=066e0e5f-008d-ad11-b9d3-1b5d60ae5ba3)

Сначала нам нужно создать хостинг для веб-сайта. 

Перейдите по пунктам меню **New > Compute > Web App > Create Custom ("Новый > Расчет > Веб-приложение > Создать по запросу пользователя")**. Вы увидите на экране нечто подобное тому, что показано ниже: 

![pic2](https://c.s-microsoft.com/ru-ru/CMSImages/sitiowebphp_2.png?version=2a15ccfc-9fc4-2982-940c-e985f263632f)

Как можно видеть, имя нашего веб-сайта будет определять URL-адрес, структура которого по умолчанию выглядит так: *myURL*.azurewebsites.net. Если вам необходимо разместить ваш веб-сайт на особом собственном домене ([www.mydomain.com](http://microsoft.opennessatcee.com/ru-cee/azureboxes/2016/02/29/website-php-mysql-ftp/www.mydomain.com)), то далее по тексту вы сможете найти пояснение, как это можно сделать. 

**Пример**: В качестве имени сайта я выбрал mfelman-phpsite, следовательно, мой адрес будет выглядеть так: mfelman-phpsite.azurewebsites.net. Кроме того, я являюсь владельцем адреса [www.marcelofelman.com.ar](http://microsoft.opennessatcee.com/ru-cee/azureboxes/2016/02/29/website-php-mysql-ftp/www.marcelofelman.com.ar) и хочу обеспечить к нему доступ. Все это можно сделать; позже мы увидим как. 

Итак, теперь в окне, показанном выше, мы выбираем опцию **Create a new MySQL database ("Создать новую базу данных MySQL")e**. Если вы уже создали базу данных и хотите подключиться к ней, это также можно сделать (мы увидим это далее). 

![pic3](https://c.s-microsoft.com/ru-ru/CMSImages/sitiowebphp_3.png?version=67afc98b-37a6-60a3-7c4f-63dcea56e272)

**ПРИМЕЧАНИЕ**: Убедитесь в том, что база данных и веб-сайт располагаются в одном и том же регионе. Это важно для обеспечения наивысшего быстродействия. 

Я выбрал регион Southern Brazil ("Южная Бразилия"). В моем контексте он обеспечивает наименьшее время задержки при обработке данных. Выбирайте наиболее близко географически расположенный к вам регион. 

![pic4](https://c.s-microsoft.com/ru-ru/CMSImages/sitiowebphp_4.png?version=d0fc985b-7e24-db7b-fde5-fd797e0835bb)

В зависимости от используемого вами репозитория программного кода выбирайте опцию, наиболее отвечающую вашим запросам. Для того, чтобы обеспечить соответствие условиям наиболее общего случая, я выполню развертывание системы с использованием протокола **FTP** (и, следовательно, мне не придется ставить отметку у опции Publish from Source Control.). 

**Примечание**: Если вы не используете никакого репозитория программного кода, я бы предложил вам не ставить отметку у опции Publish from Source Control и создать веб-сайт с использованием протокола FTP (как сделал и я). 
![pic5](https://c.s-microsoft.com/ru-ru/CMSImages/sitiowebphp_5.png?version=11dbc948-c551-dbff-6385-c555790389b1)

Теперь, для того чтобы задать параметры доступа пользователя, используемые для имплементации системы, необходимо выполнить следующую последовательность действий: 

![pic6](https://c.s-microsoft.com/ru-ru/CMSImages/sitiowebphp_6.png?version=1162c618-f76d-4c6e-a482-132551c7ffbd)

![pic7](https://c.s-microsoft.com/ru-ru/CMSImages/sitiowebphp_7.png?version=935293d9-a23c-e66f-43df-69982a9618ad)

![pic8](https://c.s-microsoft.com/ru-ru/CMSImages/sitiowebphp_8.png?version=86a39406-afb0-d67c-9124-025609fc491f)

![pic9](https://c.s-microsoft.com/ru-ru/CMSImages/sitiowebphp_9.png?version=2ca038e9-cf69-47b7-ca39-7f138eb3098d)


После этого скопируйте ссылку **FTP HOST NAME** и откройте ее в Проводнике Windows ("Мой компьютер") или в другом FTP-клиенте, с которым вы предпочитаете работать. Вы можете скопировать имя пользователя из раздела **DEPLOYMENT / FTP USER** (отмечено желтым). 

![pic10](https://c.s-microsoft.com/ru-ru/CMSImages/sitiowebphp_10.png?version=2ce71a78-e469-dd39-2afd-6d074b0c4357)

Теперь мы выбираем пункты меню **site > wwwroot**, где расположены файлы нашего веб-сайта: 

![pic11](https://c.s-microsoft.com/ru-ru/CMSImages/sitiowebphp_11.png?version=38de0b19-2446-23a9-e4c7-b30d1d730cd8)

Просто вставьте сюда ваш файл. В качестве простого теста я только что создал файл с расширением .php (воспользовавшись для этого Блокнотом) – в котором я написал слово "Hello!" Попытайтесь сделать то же самое и вставьте файл с расширением .php в папку, указанную выше. 

![pic12](https://c.s-microsoft.com/ru-ru/CMSImages/sitiowebphp_12.png?version=f4c8a443-3a82-a68e-d3c5-0582fe45851c)

*(Знаю, знаю... Мне нравятся крупные значки. Не судите меня строго...)*

![pic13](https://c.s-microsoft.com/ru-ru/CMSImages/sitiowebphp_13.png?version=fe233983-6ec9-1ab4-a181-af183dab7f2b)


Готово. Теперь откройте ваш браузер и перейдите по адресу<ваш веб-сайт>.azurewebsites.net; вы должны увидеть нечто наподобие показанного ниже: 

![pic14](https://c.s-microsoft.com/ru-ru/CMSImages/sitiowebphp_14.png?version=6b053adf-c773-5068-d305-489f6a67e035)

##Подключение к базе данных MySQL

Ну что ж, все, что мы сделали, оказалось чрезвычайно простым. Давайте теперь добавим подключение к базе данных; это тоже не должно вызвать у нас затруднений. Для того, чтобы получить информацию о подключении, мы вернемся на портал и щелкнем опцию. 
**View connection strings.** 

![pic15](https://c.s-microsoft.com/ru-ru/CMSImages/sitiowebphp_15.png?version=a2e8356b-d3cc-c173-5336-22d23919455f)
Ищите следующие поля: 
![pic16](https://c.s-microsoft.com/ru-ru/CMSImages/sitiowebphp_16.png?version=5db28d32-3b75-a4a3-e91e-e6ceda4d423e)

И заменяйте специфическую информацию о подключении в вашем программном коде, как показано ниже: 

![pic17](https://c.s-microsoft.com/ru-ru/CMSImages/sitiowebphp_17.png?version=d4c7569c-610d-fa90-76bb-53aa3be44188)
Затем мы напишем небольшой кусок программного кода, чтобы подтвердить его работоспособность: 
![pic18](https://c.s-microsoft.com/ru-ru/CMSImages/sitiowebphp_18.png?version=5490f5bc-491c-0b0d-f41c-5095d55d5f70)

Ниже я поместил указанную последовательность команд (на случай, если вы захотите ее скопировать):

    <?php 
    // 
    $host = "Server"; 
    $user = "User"; 
    $pwd = "Password"; 
    $db = "Database"; 
    try{ 
    `$conn = new PDO( "mysql:host=$host;dbname=$db", $user, $pwd); `
    $conn->setAttribute( PDO::ATTR_ERRMODE, PDO::ERRMODE_EXCEPTION ); 
    $sql = "CREATE TABLE registration_tbl( 
    id INT NOT NULL AUTO_INCREMENT, 
    PRIMARY KEY(id), 
    name VARCHAR(30), 
    email VARCHAR(30), 
    date DATE)"; 
    $conn->query($sql); 
    } 
    catch(Exception $e){ 
    die(print_r($e)); 
    } 
    echo "<h3>Table created!</h3>"; 
    ?>

Теперь, как мы уже делали раньше, скопируйте и вставьте эту последовательность команд в виде файла в папку *wwwroot* (расположенную в пути *FTP*): 

![pic19](https://c.s-microsoft.com/ru-ru/CMSImages/sitiowebphp_19.png?version=adf435b4-7d37-e510-1be9-e965c9108c7f)

Выберите опцию.*Yes to All ("Подтвердить все").* 

![pic20](https://c.s-microsoft.com/ru-ru/CMSImages/sitiowebphp_20.png?version=2b737e4e-3c39-b63c-e8bf-b8a74767f308)

Оказалось, все просто. Если мы снова попытаемся выполнить вход в систему, мы должны увидеть сообщение об ошибке, потому что мы пытаемся создать таблицу, которая уже существует, верно? 

![pic21](https://c.s-microsoft.com/ru-ru/CMSImages/sitiowebphp_21.png?version=a649dcb1-86eb-095a-287e-17431badf75e)
Отлично. Таблица создана и сайт работает. Описанная ниже последовательность действий поможет вам войти в панель управления вашего веб-сайта: 
![pic22](https://c.s-microsoft.com/ru-ru/CMSImages/sitiowebphp_22.png?version=e7e44610-ead6-4fb9-de53-464312b4b1af)
![pic23](https://c.s-microsoft.com/ru-ru/CMSImages/sitiowebphp_23.png?version=fe2aacf9-137d-1e3f-1d68-9a3c922ab1ea)


Здесь показана панель управления вашей базы данных MySQL (в онлайн режиме). Обратите внимание на множество интересных и полезных параметров вашей базы данных, которые вы можете отслеживать в режиме реального времени. 

![pic24](https://c.s-microsoft.com/ru-ru/CMSImages/sitiowebphp_24.png?version=cd355e77-0d68-63d1-6a2d-88d06d55d5ec)
Теперь вам нужно выстроить ваш сайт; однако, это уже не является предметом курса обучения по работе с сервисом Azure. 

##Персонализированные домены
Если вы выбрали для своего сайта уровень ценовой политики, не являющийся "бесплатным" ("free"), то вы можете с легкостью связать ваш сайт с вашим персонализированным доменом. Выберите ваш веб-сайт в панели Azure, затем щелкните кнопку *Manage domains ("Управление доменами")* и следуйте появляющимся на экране простым инструкциям.
