{name}Marcelo Felman{/name}{company}Microsoft{/company}{title}Сервер SVN{/title}{cat}2{/cat}{date}29.03.2016{/date}{desc}В этой статье вы узнаете как создать сервер SVN в Azure{/desc}

##Создание виртуальной машины

Сначала нам нужно создать виртуальную машину. Если у вас еще нет подписки на сервис Azure, вы можете подписаться на [бесплатную пробную версию](https://bit.ly/Azure_Trial_CEE_RU) и получить ресурсы Azure на 200 долларов США в течение месяца. 

В портале управления Azure перейдите по пунктам меню New > Compute ("Новый > Расчет"), затем выберите требуемый образ и следуйте указаниям, которые будут появляться на экране. 

![1](https://c.s-microsoft.com/ru-ru/CMSImages/svnserverazure_1.jpg?version=27b13bf0-b70c-6aec-ad06-c2087ac7727d)
![2](https://c.s-microsoft.com/ru-ru/CMSImages/svnserverazure_2.jpg?version=2a6b63f7-8ef8-6206-91c0-3a0514b55520)
![3](https://c.s-microsoft.com/ru-ru/CMSImages/svnserverazure_3.jpg?version=612fa5ba-15f2-9822-a27f-4b1c560f6a9c)


Размер виртуальной машины может быть определен исходя из количества пользователей. В моем случае мне не требуется увеличивать исходный размер виртуальной машины (я буду ее единственным пользователем), поэтому я выбрал машину А1. Хорошая новость заключается в том, что размер виртуальных машин Azure может быть изменен в будущем без утраты функциональности машины, развернутой на конкретной платформе. 
![4](https://c.s-microsoft.com/ru-ru/CMSImages/svnserverazure_4.jpg?version=85d9b677-1c20-d9aa-aabb-64e5569e1fce)

Как правило, в качестве места локализации я выбираю "восточную часть Соединенных Штатов" ("eastern United States"), т.к. такое местоположение обеспечивает для меня наименьшее время задержки при обработке данных. Выбирайте самый близко расположенный к вам регион. 
![5](https://c.s-microsoft.com/ru-ru/CMSImages/svnserverazure_5.jpg?version=4dae7120-c0df-524e-487f-c378fc871b05)

Когда виртуальная машина будет создана, мы подключимся к серверу. 

##Вход на сервер

В портале управления Azure выберите свою виртуальную машину, а затем щелкните кнопку “connect” ("подключить"). 
![6](https://c.s-microsoft.com/ru-ru/CMSImages/svnserverazure_6.jpg?version=4ad8484f-9906-b4b3-d674-d046846fba4f)
![7](https://c.s-microsoft.com/ru-ru/CMSImages/svnserverazure_7.jpg?version=b0d511a8-1f8d-99ad-ce30-2304ba662326)
![8](https://c.s-microsoft.com/ru-ru/CMSImages/svnserverazure_8.jpg?version=92a7df64-f877-df25-0483-52f46cbb6847)

Нам потребуются те же самые параметры доступа пользователя, которые мы указали и при создании виртуальной машины. 
![9](https://c.s-microsoft.com/ru-ru/CMSImages/svnserverazure_9.jpg?version=80471ddf-4e67-3919-0bef-aba5c69444e3)

Теперь вход выполнен. 

##Установка приложения VisualSVN

Не хочу здесь никого обманывать. Я не сторонник использования консольных команд. Запускаю программу установки (в состав которой входит "мастер" установки) и во всех появляющихся окнах щелкаю кнопку "next" ("далее"). 
![10](https://c.s-microsoft.com/ru-ru/CMSImages/svnserverazure_10.jpg?version=f55a8ca9-8124-579b-e63f-b3a0aaa635fb)

Программа загружается со страницы загрузки VisualSVN: [http://www.visualsvn.com/server/download/](http://www.visualsvn.com/server/download/)

##Конфигурирование приложения VisualSVN

Как только приложение будет установлено, наша работа будет почти закончена. Мы можем добавлять пользователей, проекты и т.д. 
![11](https://c.s-microsoft.com/ru-ru/CMSImages/svnserverazure_11.png?version=3ffcc017-0968-738a-9390-10f9a44402a7)

Приведу небольшой пример, иллюстрирующий порядок добавления пользователя и проекта. 
![12](https://c.s-microsoft.com/ru-ru/CMSImages/svnserverazure_12.png?version=481d7b7a-8bb2-9885-99bd-b5ffb6bbc22c)
![13](https://c.s-microsoft.com/ru-ru/CMSImages/svnserverazure_13.png?version=6a7b0aa8-bdd4-3c87-fcf1-223e064c2e7a)

Теперь пользователь и репозиторий созданы. Давайте перейдем на сторону клиента. По привычке, я выбираю для использования приложение TortoiseSVN (мне удобно с ним работать). 

##Действия со стороны клиента

Щелкните правой кнопкой мыши, откроется новое окно проверки ("checkout"). С этим окном мы уже знакомы. 

Здесь важно отметить, что мы используем адрес облачного сервиса, выбранный нами ранее. 
![14](https://c.s-microsoft.com/ru-ru/CMSImages/svnserverazure_14.png?version=95fcb62e-c487-8f52-737a-3d74809cd9e2)
![15](https://c.s-microsoft.com/ru-ru/CMSImages/svnserverazure_15.png?version=4194fbfe-ecd5-66b5-8543-c6ffb7189928)

Не торопитесь 

Для того чтобы подключиться к виртуальной машине, нам нужно открыть брандмауэр конечной точки HTTPS на платформе Azure. Для этого мы отправляемся на сайт указанного сервиса, выбираем опцию конфигурирования настроек виртуальной машины, затем переходим к пункту меню Endpoints ("Конечные точки") и добавляем конечную точку: 
![16](https://c.s-microsoft.com/ru-ru/CMSImages/svnserverazure_16.png?version=e9cc3086-2279-58bc-1dd3-6c19d428cc1f)
Попытайтесь снова выполнить процедуру проверки: 
![17](https://c.s-microsoft.com/ru-ru/CMSImages/svnserverazure_17.png?version=7b6dfda1-4bc7-0789-3a06-53b453f572ac)
Готово! 
![18](https://c.s-microsoft.com/ru-ru/CMSImages/svnserverazure_18.png?version=d47ebe2f-80eb-81f0-8782-c17f2c7d775c)
Как видите, вся операция выполняется очень быстро и просто.
