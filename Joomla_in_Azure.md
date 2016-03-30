{name}Branko Straub{/name}{company}Microsoft{/company}{title}Сайт Joomla! за 15 минут{/title}{cat}2{/cat}{date}29.03.2016{/date}{desc}Сегодня расскажем как запустить сайт Joomla! на Azure{/desc}

Прежде всего необходимо зарегистрировать действующую подписку Microsoft Azure. Если у вас ее нет, [подпишитесь](https://bit.ly/Azure_Trial_CEE_RU) на бесплатную пробную версию, следуя инструкциям по регистрации. Пробная версия Azure предоставляет кредит $ 200 на услуги Azure в течение месяца, но для этого потребуется ввести код своей действующей кредитной карты, чтобы подтвердить личность (со счета снимается плата в размере $ 1, которая позже возвращается на карту). 

Стартапы и студенты могут получить постоянный бесплатный доступ в Azure присоединившись к программам [Bizspark](http://www.microsoft.com/bizspark) или [Dreamspark](https://www.dreamspark.com/) соответственно. Обратите внимание, что, хотя служба SendGrid является бесплатной для рассылки до 25000 писем в месяц, Azure Marketplace все равно потребует ввести данные действующей кредитной карты. 

##Настройка Azure
Если у вас есть готовая учетная запись, перейдите по ссылке [https://manage.windowsazure.com](https://manage.windowsazure.com/), заем найдите раздел **Web Apps** и нажмите **Create a Web App**. 

![pic1](https://c.s-microsoft.com/ru-ru/CMSImages/joomla1.png?version=6d9f8765-bf29-7a05-1d73-ea6742a8867c)

Выберите **WebApp** а затем **From Gallery**. 

![pic2](https://c.s-microsoft.com/ru-ru/CMSImages/joomla2.png?version=f0790ca2-00eb-f864-32b9-32b5d0beeac1)

Выберите CMS в левой части меню, после чего появятся доступные системы управления контентом (CMS). Выберите **Joomla!** и нажмите next: 

![pic3](https://c.s-microsoft.com/ru-ru/CMSImages/joomla3.png?version=8bedeee4-3fc1-9408-d029-4c2d3824645f)

Приступим к настройке параметров сайта: 
Необходимо изменить адрес URL и регион. Выберите URL и ближайший регион (исходя из времени задержки). 

![pic4](https://c.s-microsoft.com/ru-ru/CMSImages/joomla4.png?version=30011b6c-1a79-f498-8dbd-d8679d62cd75)
Продолжаем установку сайта: 
**Load Sample Data**: Данная опция позволяет создать сайт с данными по умолчанию (предварительными данными). 
**Website Name**: имя, которое вы хотите дать сайту 
В конце установите пароль администратора и добавьте контактный адрес электронной почты. 

![pic5](https://c.s-microsoft.com/ru-ru/CMSImages/joomla5.png?version=8ce6c60c-8ff2-da26-061c-61633dfed6f8)
Задайте имя для сервера баз данных, его расположение (то же, что и для веб-сайта) и примите условия и обязательства. 

![pic6](https://c.s-microsoft.com/ru-ru/CMSImages/joomla6.png?version=d5423ffe-ede5-b3eb-dfbe-9055e2fd1e1e)
Через несколько минут вы увидите, что сайт Joomla! создан и доступен для входа. 

![pic7](https://c.s-microsoft.com/ru-ru/CMSImages/joomla7.png?version=9e4204fd-9554-0d5c-401e-b178e870a352)
![pic8](https://c.s-microsoft.com/ru-ru/CMSImages/joomla8.png?version=b0f952cd-b86b-71b7-424d-5b44eb46b559)

Теперь, когда сайт создан, можно использовать множество способов публикации своего контента, начиная с FTP подключения к непрерывному развертыванию через Git, Dropbox, Visual Studio онлайн, и т.д. Я предпочитаю пользоваться **WebMatrix**. 


##Настройка сайта

Нажмите на сайт, а затем **WebMatrix**: Пакет установки также можно скачать с сайта [www.webmatrix.com](http://microsoft.opennessatcee.com/ru-cee/azureboxes/2016/03/01/joomla-site-in-15-minutes/www.webmatrix.com) website. 

![pic9](https://c.s-microsoft.com/ru-ru/CMSImages/joomla9.png?version=b70947b2-b33e-4fcd-a25f-0857e28456ef)

Начните установку **WebMatrix**: 

![pic10](https://c.s-microsoft.com/ru-ru/CMSImages/joomla10.png?version=4d0eb9cd-e974-4220-59fe-9c2fe4c0018f)

После завершения процесса установки откройте WebMatrix и войдите с помощью вашей учетной записи Azure. 
Появится запрос о загрузке копии вашего сайта или работы онлайн. Для данного примера я выбрал вариант "Edit live site directly" (Редактировать сайт напрямую), другой вариант позволяет скачать весь сайт и работать с ним, используя localhost. 

![pic11](https://c.s-microsoft.com/ru-ru/CMSImages/joomla11.png?version=74713c87-e5a5-d839-62cc-d9c347a78204)
Теперь в WebMatrix у вас есть доступ ко всем файлам сайта. 

![pic12](https://c.s-microsoft.com/ru-ru/CMSImages/joomla12.png?version=f2169fd1-9954-5a21-4b9d-b4f2a3a99242)

##Настройка сайта
Управление содержимым сайта осуществляется довольно просто через панель администрирования Joomla. Первое, что нужно сделать, это войти в систему как администратор: Admin, * пароль* 

![pic13](https://c.s-microsoft.com/ru-ru/CMSImages/joomla13.png?version=01c567c0-1983-b381-4402-285b4c8a5f6b)

После входа появится панель управления Joomla: 

![pic14](https://c.s-microsoft.com/ru-ru/CMSImages/joomla14.png?version=686ee6d5-b58a-69fb-6084-01ae3e74c5e3)

Из этой панели кроме прочего можно управлять контентом, закачивать расширения, шаблоны, создавать пользователей, изменять язык, и т.д. 

В итоге ваш сайт может выглядеть примерно так: 

![pic15](https://c.s-microsoft.com/ru-ru/CMSImages/joomla15.png?version=ea21dd7b-17d4-a18c-7a90-31e7eaf296e4)
Не забывайте о том, что, поскольку данный сайт работает в облаке Microsoft Azure, из панели управления Azure вы можете проверять статистику сайта, настраивать резервное копирование и многое другое.
