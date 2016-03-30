{name}Marcelo Felman{/name}{company}Microsoft{/company}{title}Стек технологий LAMP{/title}{cat}2{/cat}{date}30.03.2016{/date}{desc}Cегодня мы рассмотрим процедуру установки программной среды LAMP на платформу Azure с использованием виртуальных машин. {/desc}

Если у вас нет учетной записи Microsoft Azure, подпишитесь на [бесплатную пробную версию](https://bit.ly/Azure_Trial_CEE_RU) и получите получите ресурсы Azure на 200 долларов США в течение месяца, или же примите участие в программе [BizSpark](http://www.microsoft.com/bizspark) (если вы представляете стартап) при этом вы можете получить до 120 тысяч долларов для использования ресурсов Azure. 

Перед настройкой параметров вашего сервера вам будет необходимо определиться с размером виртуальной машины и местом расположения регионального датацентра, который будет использоваться в качестве хоста этой виртуальной машины. Я рекомендую ознакомиться с содержанием [данной](https://azure.microsoft.com/en-us/pricing/details/virtual-machines/) страницы, где можно узнать больше о ценах на сервисы Azure, а также о имеющихся региональных датацентрах. Как обычно, мы начнем наш обзор с процедуры входа на портал Azure [http://manage.windowsazure.com](http://manage.windowsazure.com/) использованием данных идентификации нашей Учетной записи *Microsoft*.

![1](https://c.s-microsoft.com/ru-ru/CMSImages/ambientelampazure_1.png?version=c52e9da6-b14b-c448-e3fb-4ecfd2c9333b)

Затем перейдите по пунктам меню **Virtual Machines > Images > Browse VM Depot
("Виртуальные машины > Изображения > Просмотр хранилища виртуальных машин"**)
![2](https://c.s-microsoft.com/ru-ru/CMSImages/ambientelampazure_2.png?version=9c98fccb-896a-9980-ee0f-b2c83b2a2721)

После этого нам будет необходимо найти желаемую версию стека **LAMP**. В моем случае я выбрал последнюю доступную версию (5.6.0.0, библиотека Bitnami). Теперь щелкните кнопку **next ("далее")**. 
![3](https://c.s-microsoft.com/ru-ru/CMSImages/ambientelampazure_3.png?version=c2a94626-b33f-b398-7b87-daaad23db2bf)

Я выберу центр обработки и хранения данных **Brazil South** (в моем контексте он обеспечивает наименьшее время задержки при обработке данных). **Finish ("Завершить")**. 

![4](https://c.s-microsoft.com/ru-ru/CMSImages/ambientelampazure_4.png?version=b76f1b5b-7b6c-6aa8-6dff-59a893e713d2)
![5](https://c.s-microsoft.com/ru-ru/CMSImages/ambientelampazure_5.png?version=dc44a8de-0487-e1e9-a72d-bbd2136efba1)

Теперь нам нужно создать образ выбранной нами виртуальной машины, который был бы ассоциирован с нашей учетной записью. Сначала нам будет необходимо зарегистрировать этот образ; затем на основе данного образа мы создадим виртуальную машину. 
Для этого нужно выполнить следующую последовательность действий: 

![6](https://c.s-microsoft.com/ru-ru/CMSImages/ambientelampazure_6.png?version=94337bf0-b886-704c-507e-b08d20d8e9de)
![7](https://c.s-microsoft.com/ru-ru/CMSImages/ambientelampazure_7.png?version=4db8a389-4ac6-0b91-a024-788d83c566cd)
Теперь образ зарегистрирован. Можно приступить к созданию сервера на основе данного образа.Щелкните пункт меню **New ("Новый")**, после чего выполните указанную ниже последовательность действий: 

![8](https://c.s-microsoft.com/ru-ru/CMSImages/ambientelampazure_8.png?version=21651899-db7e-507c-ce3a-645d7a35fbec)
Теперь мы видим, что в списке образов появилась программная среда **LAMP**; мы выбираем ее и нажимаем кнопку **next ("далее")**. 

![10](https://c.s-microsoft.com/ru-ru/CMSImages/ambientelampazure_9.png?version=9b6c6ef1-d9c6-6b70-b4e3-6be5dacb6a3b)

![11](https://c.s-microsoft.com/ru-ru/CMSImages/ambientelampazure_10.png?version=5e7de1b0-88c8-9fcd-61ea-d3fcb1c190eb)

![12](https://c.s-microsoft.com/ru-ru/CMSImages/ambientelampazure_11.png?version=1a42ed19-04e8-3471-510a-891f85c79814)

![13](https://c.s-microsoft.com/ru-ru/CMSImages/ambientelampazure_12.png?version=3e4b0c3b-c21d-d0f7-9a69-175664f797b8)
Для запуска процесса создания виртуальной машины щелкните кнопку **finish ("завершить").** 
![14](https://c.s-microsoft.com/ru-ru/CMSImages/ambientelampazure_13.png?version=046753ef-79c1-44df-1e5a-bd05a6014830)

Теперь виртуальная машина создана. Мы можем управлять ее работой с использованием команд **Панели управления ("Dashboard")**. Я подключусь к ней с использованием протокола SSH; это позволит мне управлять работой сервера (хотя для этих же целей можно использовать и протокол RDP, либо другие поддерживаемые протоколы (см. список)). 
![15](https://c.s-microsoft.com/ru-ru/CMSImages/ambientelampazure_14.png?version=1df6edb3-6886-853a-6617-8f82a2125483)

Теперь мы добавим **конечную точку ("endpoint").** 

![16](https://c.s-microsoft.com/ru-ru/CMSImages/ambientelampazure_15.png?version=324074ec-a9f1-2e2b-c6a6-34e0f9b6de7f)
![17](https://c.s-microsoft.com/ru-ru/CMSImages/ambientelampazure_16.png?version=2de99d27-767c-a356-3281-721f2480d23d)
![18](https://c.s-microsoft.com/ru-ru/CMSImages/ambientelampazure_17.png?version=13d2bf2d-8900-9ec3-2e87-e4613979224d)
Сразу же после создания **конечной точки ("endpoint")**, мы подключимся к ней с использованием инструмента [PuTTY](http://www.chiark.greenend.org.uk/~sgtatham/putty/download.html) (наши параметры выделены желтым цветом). 

![19](https://c.s-microsoft.com/ru-ru/CMSImages/ambientelampazure_18.png?version=d17f26b5-1279-d014-83f3-8b12dab32d50)

Нам потребуются те же самые параметры доступа пользователя, которые мы указали и при создании виртуальной машины. 
![20](https://c.s-microsoft.com/ru-ru/CMSImages/ambientelampazure_19.png?version=d67e87ab-c032-c709-f0a9-ee0c6044475c)
Все компоненты стека (Apache, MySQL, PHP) установлены по адресу [bitnami@demoLAMP:/home/bitnami/stack$](bitnami@demoLAMP:/home/bitnami/stack$). Кроме того, при обработке образа библиотеки Bitnami были также установлены компоненты Git, Ruby, SQLite. Довольно удобно. 
![21](https://c.s-microsoft.com/ru-ru/CMSImages/ambientelampazure_20.png?version=a1e718cf-6f1a-2e08-13b5-8b528622f901)

Теперь все готово! Мы можем начинать работу в нашей среде **LAMP**.
