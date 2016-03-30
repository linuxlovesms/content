{name}Matias Tuduri {/name}{company}Microsoft{/company}{title}Миграция сайта Wordpress на платформу Azure{/title}{cat}2{/cat}{date}28.03.2016{/date}{desc}Сегодня расскажем о Wordpress и Azure{/desc}

##Создание нового сайта Wordpress на платформе Azure

Давайте сначала создадим новый сайт Wordpress, используя для этого средства платформы Azure. Для этого у вас должна быть активирована подписка Azure. Если у вас еще нет учетной записи Microsoft Azure, подписаться можно, воспользовавшись одним из следующих бесплатных способов:

- Подпишитесь на [бесплатную пробную версию](https://bit.ly/Azure_Trial_CEE_RU) и получите ресурсы Azure на сумму 200 долларов США

- Если вы студент, вы можете принять участие в программе [DreamSpark](https://www.dreamspark.com/)

- Для стартапов: вы можете принять участие в программе [BizSpark](http://www.microsoft.com/bizspark) (при этом вы получите до 120 000 долларов США для использования ресурсов Azure)

Примечание: Во время регистрации вам будет предложено ввести данные вашей кредитной карты, чтобы подтвердить, что вы имеете право на получение бесплатной версии сервиса. Предоставленная вами информация будет использована только для удостоверения вашей личности; вам ничего не нужно будет платить за использование сервиса Azure, если только вы сами позднее не измените условия подписки на платные.

Находясь на нашем портале Azure ([https://manage.windowsazure.com](https://manage.windowsazure.com/)), выберите опцию '+ NEW' и щелкните на поле 'WEB APP', а затем – 'GALLERY' ("Галерея").

![pic1](https://static.opennessatcee.com/azureboxes/content/wp-migration-ru/i_cb0ebfd19880e180_html_f7d673aa.png)

Выберите раздел '**Blogs**', а затем – опцию  '**WordPress**' и щелкните 'next' ("далее").

![pic2](https://static.opennessatcee.com/azureboxes/content/wp-migration-ru/i_cb0ebfd19880e180_html_baa15f66.png)

В поле 'ADDRESS URL' мы вписываем URL адрес нашего нового блога WordPress; это имя должно быть уникальным для домена 'azurewebsites.com'. Сайт WordPress требует использования базы данных формата MySQL; если у вас еще нет такой базы данных с рабочей конфигурацией, то данный процесс создаст эту базу для вас. Щелкните кнопку 'next' ("далее"), чтобы продолжить работу.

![pic3](https://static.opennessatcee.com/azureboxes/content/wp-migration-ru/i_cb0ebfd19880e180_html_e011ac63.png)

**(если у вас еще нет базы данных):**  

Здесь вы должны указать наименование вашей базы данных и регион размещения центра хранения данных, где ваша база данных будет храниться (важно выбрать тот же регион, что и при выполнении предыдущего шага, чтобы избежать задержек в работе при обработке запросов, пересылаемых между сайтом и базой данных).

Наконец, ознакомьтесь с условиями использования услуг компании ClearDB (поставщика вашей базы данных формата MySQL ) и, если вы согласны с ними, поставьте отметку в поле выбора и закройте окно диалога.

![pic4](https://static.opennessatcee.com/azureboxes/content/wp-migration-ru/i_cb0ebfd19880e180_html_2f7f7c9e.png)

После завершения предыдущего шага зайдите на портал Azure и проверьте состояние вашего нового веб-приложения, которым является блог, основанный на движке WordPress.

![pic5](https://static.opennessatcee.com/azureboxes/content/wp-migration-ru/i_cb0ebfd19880e180_html_30f1f2e1.png)

Для получения доступа к вашему новому блогу щелкните на колонке URL адреса.

Выберите удобный для вас язык, заполните анкету, введя в нее необходимую информацию, и щелкните на опции 'Install WordPress' ("Установить WordPress").



##Миграция вашего существующего сайта, созданного на платформе WordPress

Откройте панель управления существующего блога WordPress, который мы желаем экспортировать ('имя пользователя'.wordpress.com/wp-admin), выберите опцию 'Tools' ("Инструменты"), а затем – 'Export' ("Экспортировать").

![pic6](https://static.opennessatcee.com/azureboxes/content/wp-migration-ru/i_cb0ebfd19880e180_html_851b33a4.png)

Задайте экспорт всего контента и нажмите кнопку 'Download export file' ("Загрузить экспортируемый файл").

![pic7](https://static.opennessatcee.com/azureboxes/content/wp-migration-ru/i_cb0ebfd19880e180_html_716328c1.png)

Теперь откройте панель управления нашего нового блога WordPress, который мы создали на платформе Windows Azure, выберите опцию 'Tools' ("Инструменты"), а затем – ' Import' ("Импортировать").

![pic8](https://static.opennessatcee.com/azureboxes/content/wp-migration-ru/i_cb0ebfd19880e180_html_3f348607.png)

Выберите опцию импорта 'WordPress'

![pic9](https://static.opennessatcee.com/azureboxes/content/wp-migration-ru/i_cb0ebfd19880e180_html_9b647190.png)

и установите импортируемый элемент, щелкнув на опции 'Install Now' ("Установить сейчас").

![pic10](https://static.opennessatcee.com/azureboxes/content/wp-migration-ru/i_cb0ebfd19880e180_html_c7e60ae6.png)

В конце выполнения данной процедуры вы увидите окно, показанное ниже. Щелкните на кнопке 'Browse' ("Просмотреть"), чтобы загрузить файл, созданный ранее. Выберите опцию "Upload file and import" ("Выгрузить файл и импортировать").

![pic11](https://static.opennessatcee.com/azureboxes/content/wp-migration-ru/i_cb0ebfd19880e180_html_bc11f479.png)

Назначьте нового автора сообщений ("постов") и щелкните на кнопке 'Submit' ("Утвердить").

![pic12](https://static.opennessatcee.com/azureboxes/content/wp-migration-ru/i_cb0ebfd19880e180_html_a4b0336e.png)

После того как процесс импорта будет завершен, ваш сайт будет готов к просмотру!

![pic13](https://static.opennessatcee.com/azureboxes/content/wp-migration-ru/i_cb0ebfd19880e180_html_a3c11d18.png)

Наконец, ваш новый блог готов к использованию и содержит весь импортированный вами контент.

![pic14](https://static.opennessatcee.com/azureboxes/content/wp-migration-ru/i_cb0ebfd19880e180_html_c742a4ba.png)
