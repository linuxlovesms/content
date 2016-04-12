{name}Marcelo Felman{/name}{company}Microsoft{/company}{title}Нагрузочное тестирование веб-приложения{/title}{cat}2{/cat}{date}30.03.2016{/date}{desc}В этой статье вы узнаете как провести нагрузочное тестирование веб-приложения {/desc}

Прежде всего необходимо зарегистрировать действующую подписку Microsoft Azure. Если у вас ее нет, [подпишитесь](https://bit.ly/Azure_Trial_CEE_RU) на бесплатную пробную версию, следуя инструкциям по регистрации. Пробная версия Azure предоставляет кредит $ 200 на услуги Azure в течение месяца, но для этого потребуется ввести код своей действующей кредитной карты, чтобы подтвердить личность (со счета снимается плата в размере $ 1, которая позже возвращается на карту). 

Стартапы и студенты могут получить постоянный бесплатный доступ в Azure присоединившись к программам [Bizspark](http://www.microsoft.com/bizspark) или [Dreamspark](https://www.dreamspark.com/) соответственно. Обратите внимание, что, хотя служба SendGrid является бесплатной для рассылки до 25000 писем в месяц, Azure Marketplace все равно потребует ввести данные действующей кредитной карты. 

##Настройка среды для тестирования

Сначала необходимо создать в Azure виртуальную машину, на которой будут проводиться тесты. Для этого выполняются следующие действия: 

![1](https://c.s-microsoft.com/ru-ru/CMSImages/stresstestazure1.png?version=22c40c43-fea2-59db-1ae0-e817d765b8df)

![2](https://c.s-microsoft.com/ru-ru/CMSImages/stresstestazure2.png?version=089466b6-e1e9-0edf-40e1-7b214169ccbd)

В зависимости от типа испытаний, который требуется запустить, может потребоваться достаточно мощная машина. Для проведения серьезных тестов я выбираю формат A4. 

![3](https://c.s-microsoft.com/ru-ru/CMSImages/stresstestazure3.png?version=eccebbba-da90-6734-8e8e-a5fa351846bd)
Подключаемся с помощью удаленного рабочего стола (Remote Desktop) со следующими учетными данными. 

Twitter API
![4](https://c.s-microsoft.com/ru-ru/CMSImages/stresstestazure4.png?version=0af495af-85bd-7bd9-58ed-84dbaa838d8b)
![5](https://c.s-microsoft.com/ru-ru/CMSImages/stresstestazure5.png?version=4db5b68a-5cde-2d2f-9078-7c1df0c1c37c)
![6](https://c.s-microsoft.com/ru-ru/CMSImages/stresstestazure6.png?version=321fa7a6-e286-9119-d221-791b52af8f60)

После создания появится сервис, похожий на этот. Подключаемся к нему удаленно: 

![7](https://c.s-microsoft.com/ru-ru/CMSImages/stresstestazure7.png?version=21654a34-b702-1fa8-9691-cdc33b21e40d)

![8](https://c.s-microsoft.com/ru-ru/CMSImages/stresstestazure9.png?version=6b07f3d8-45da-c1a8-7043-f1d783fd3f3f)

![9](https://c.s-microsoft.com/ru-ru/CMSImages/stresstestazure10.png?version=8e941818-36ad-2d5d-faa7-f3d125b7cae4)

![10](https://c.s-microsoft.com/ru-ru/CMSImages/stresstestazure11.png?version=5d0e58b5-ad35-bd1d-7fb7-467e6e2e673f)

Теперь мы будем работать в виртуальной машине, работающей в Azure. Запускаем Visual Studio 

![11](https://c.s-microsoft.com/ru-ru/CMSImages/stresstestazure12.png?version=13e6c15e-bca1-ecc7-147f-1b239208949a)

![12](https://c.s-microsoft.com/ru-ru/CMSImages/stresstestazure13.png?version=5ea0e02b-f62c-da0d-7d82-902a26ed7aa6)

**Подписчики MSDN**: Вход осуществляется с помощью учетной записи Microsoft. Остальные должны заходить с учетной записью Visual Studio. 

Теперь необходимо перейти **File> New> Project** и выбрать Web Performance и Load Test Project 

![13](https://c.s-microsoft.com/ru-ru/CMSImages/stresstestazure14.png?version=e89efeb4-94eb-86ec-05b9-8543689eae2e)

Начнем с создания общего теста веб производительности (Web Performance Test) 

![14](https://c.s-microsoft.com/ru-ru/CMSImages/stresstestazure15.png?version=da4b847c-5322-589d-d45e-6a2633c01e84)

Здесь записываются сценарии теста. В данном случае мы осуществляем запись сценария посещения сайта в Visual Studio, а затем одновременно повторяем его десятки или даже тысячи раз. Действиями могут быть аутентификация, генерирование запросов, транзакции, и т.д. В моем случае использован простой пример, но вариаций очень много, в зависимости от ваших потребностей. 

Приступаем к записи сессии: 

![15](https://c.s-microsoft.com/ru-ru/CMSImages/stresstestazure16.png?version=892e52b2-0712-42bb-b156-f127d2b17274)
![16](https://c.s-microsoft.com/ru-ru/CMSImages/stresstestazure17.png?version=7d365d82-1652-4691-2f6f-5bde2d7a3b7e)

Здесь я приведу простейший пример только с одним запросом. 

![17](https://c.s-microsoft.com/ru-ru/CMSImages/stresstestazure18.png?version=748afe2d-25f1-d29b-d657-f4d1d402537f)

Прекрасно. Далее создаем автоматизированный случай посещения сайта пользователем. Затем можно смоделировать сотни одновременных посещений с входом на сайт: 

![18](https://c.s-microsoft.com/ru-ru/CMSImages/stresstestazure19.png?version=5c1152c5-8e9d-d839-6f2d-4ca038f4a3c8)

![19](https://c.s-microsoft.com/ru-ru/CMSImages/stresstestazure20.png?version=af10b88a-da7b-bd98-dcf6-3654b0283342)

![20](https://c.s-microsoft.com/ru-ru/CMSImages/stresstestazure21.png?version=14e91220-e59d-f711-04f9-4477c1a0df5c)

Добавляем созданный ранее веб-тест: 

![21](https://c.s-microsoft.com/ru-ru/CMSImages/stresstestazure22.png?version=c1ffd2ec-dfb7-643f-3ed0-2a5e09baf8a6)
![22](https://c.s-microsoft.com/ru-ru/CMSImages/stresstestazure23.png?version=19f9b514-0bb4-3e75-9a78-1b4f9a704b2d)

Как видно, мастер предоставляет множество вариантов. Вы можете создать волны нагрузки, постоянный трафик, установить длительность, разогрев и многое другое. Лучше всего подробности описаны в этой статье: [http://msdn.microsoft.com/en-us/library/vstudio/dd293540(v=vs.110).aspx .](http://msdn.microsoft.com/en-us/library/vstudio/dd293540%28v=vs.110%29.aspx) 
Итак, тест уже настроен и чтобы запустить его, нажимаем **Run** (Выполнить). 
Тем временем, я покажу вам, что я использовал для тестирования: 

![23](https://c.s-microsoft.com/ru-ru/CMSImages/stresstestazure24.png?version=a9a2f1bb-b453-ba51-3ac2-6c779a49ee8d)

![24](https://c.s-microsoft.com/ru-ru/CMSImages/stresstestazure25.png?version=fa98a13a-91a8-ae65-1505-d840874f748c)

Очень восхитительная программа, не правда ли:)? Единственное, что она делает, это циклическую нагрузку. Я закачиваю ее в веб-роль (web role) Azure: web role: 

![25](https://c.s-microsoft.com/ru-ru/CMSImages/stresstestazure26.png?version=4269dcb3-0515-a43c-009e-424f5b8d0d3b)

Теперь она работает. 

##Результаты

Сначала посмотрим на панель из Visual Studio. Появятся значения ключевых показателей, времени отклика страницы и прочие полезные для понимания работы приложения показатели. Я рекомендую попробовать самостоятельно, и в случае возникновения вопросов ознакомиться со следующей статьей: [http://msdn.microsoft.com/en-us/library/vstudio/ee923686(v=vs.110).aspx](http://msdn.microsoft.com/en-us/library/vstudio/ee923686%28v=vs.110%29.aspx)

![26](https://c.s-microsoft.com/ru-ru/CMSImages/stresstestazure27.png?version=bcc603ee-7e08-be5b-1bc2-0cd93e4cab79)
![27](https://c.s-microsoft.com/ru-ru/CMSImages/stresstestazure28.png?version=0f8b6ede-c88c-a415-e920-591aaf588b48)

Теперь приступим к наиболее интересной части - результатам "конечного пользователя" (end user). Как показано ниже, мое приложение начало нагружаться пользователями приблизительно в 12:45. Скачок **100 создаваемых каждую секунду запросов пользователей** увеличивает нагрузку процессора до 63,58%. 

![28](https://c.s-microsoft.com/ru-ru/CMSImages/stresstestazure29.png?version=73300f40-d2a4-2375-2b85-c032e9767357)

Однако мое приложение отвечало нормально, и полученные значения для времени отклика страницы, показали, что результат является приемлемым. Обратите внимание на некоторые аспекты для планирования выделенных ресурсов для приложения (capacity planning): симулируйте нагрузку на определенное количество пользователей, рассчитайте количество экземпляров, необходимых для стабильной работы сайта и проецируйте на более широкий масштаб. 
Теперь давайте создадим менее спокойный сценарий и запустим тот же тест, стараясь убить процессор. Запускаем тест с **5000 одновременных пользователей, (!) делающих запрос каждую секунду**.

![29](https://c.s-microsoft.com/ru-ru/CMSImages/stresstestazure30.png?version=9c1545ff-e9fa-cf00-2fa6-7b210c8391d7)

Как мы видим, время отклика сильно пострадало. Это плохо. 
И как мы видим, после завершения скачка, оно возвращается в нормальное состояние: 

![30](https://c.s-microsoft.com/ru-ru/CMSImages/stresstestazure31.png?version=04c0ff95-9d5a-661f-f5b6-676163d6f140)

Загрузка процессора показана ниже 

![31](https://c.s-microsoft.com/ru-ru/CMSImages/stresstestazure32.png?version=23811736-5743-30f5-efb2-9ab21f05d621)

Вот результаты нашего теста: 

![32](https://c.s-microsoft.com/ru-ru/CMSImages/stresstestazure33.png?version=4cc5d9fa-94fb-3543-2958-e22ace5f59fc)
![33](https://c.s-microsoft.com/ru-ru/CMSImages/stresstestazure40.png?version=f9375c3b-9e4d-9018-95ce-f403e6fe0043)

##Масштабирование

Я намеренно отключил в своих примерах автомасштабирование экземпляров сайта, чтобы знать максимальную мощность каждого из них. Теперь можно просто уввеличить количество экземпляров и определить, как они реагируют на тот же тест. Для этого я увеличу количество экземпляров до 2: 

![34](https://c.s-microsoft.com/ru-ru/CMSImages/stresstestazure34.png?version=3be31225-718e-3f1f-0ddf-9d5b7e94c2c4)

![35](https://c.s-microsoft.com/ru-ru/CMSImages/stresstestazure35.png?version=bf81b177-371e-df04-47be-8ec05dd8713c)

Теперь запустим тот же полный тест с 2 экземплярами. Кроме того, балансировка нагрузки настраивается на использование алгоритма Round Robin (т.е. отправку запроса чередуя экземпляры). 
Перед началом теста: 

![36](https://c.s-microsoft.com/ru-ru/CMSImages/stresstestazure36.png?version=790c6864-894f-6c7f-83c1-72dd83295748)

Во время теста: 

![37](https://c.s-microsoft.com/ru-ru/CMSImages/stresstestazure37.png?version=8254fcc5-b1d6-6f2c-13d5-091a82dbf2bd)

Похоже, что производительность опять пострадала. Тем не менее, в случае удваивания количества экземпляров время отклика сокращается на 50% (совпадение?). 

![38](https://c.s-microsoft.com/ru-ru/CMSImages/stresstestazure38.png?version=01b29247-48fd-9700-f0ce-a364604ec882)

Как видно из Azure: 

![39](https://c.s-microsoft.com/ru-ru/CMSImages/stresstestazure39.png?version=a1333a2a-fd5c-4d83-0262-14be0f8fbb58)

##Заключение

С помощью показанных методов можно узнать, в какой степени веб приложение может выдерживать внешнюю пиковую нагрузку. Это позволяет провести более точную (и фактическую) оценку того, сколько экземпляров нужно назначить приложению для поддержки заданного уровня обслуживания. Это особенно важно для приложений, требующих высокого уровня доступности. 

Главной же особенностью является то, что все это можно настроить с небольшими затратами, и менее чем за час, без установки или покупки программного обеспечения, пользуясь только возможностями облака Azure.
