{name}Vladimir Yunev{/name}{company}Microsoft{/company}{title}Открытая БД Tarantool от Mail.ru сертифицирована и размещена в Azure Marketplace{/title}{cat}0{/cat}{date}28.03.2016{/date}{desc}Представляем вашему вниманию статью о применении открытой БД Tarantool от Mail.ru в облаке Azure{/desc}

Уважаемые коллеги, у меня для вас отличные новости!

![image](https://habrastorage.org/getpro/habr/post_images/116/76b/f0b/11676bf0b9048d8aa4a8d7fd04e87039.png)

Открытая NoSQL-база данных [Tarantool](http://tarantool.org/), которую разрабатывает компания Mail.ru, была сертифицирована для облачной плафтормы Azure и опубликована в [Azure Marketplace](https://azure.microsoft.com/ru-ru/marketplace/virtual-machines/all/) для удобства и скорости развертывания.

Tarantool – это высокопроизводительный сервер приложений на базе Lua, интегрированный с NoSQL СУБД. База данных разрабатывается в виде открытого проекта под лицензией BSD компанией Mail.ru и сообществом разработчиков.

Крупнейшим кейсом использования Tarantool служит сама компания Mail.ru, которая с помощью этой БД обеспечивает работу 30 миллионов пользователей и 25 миллионов email в сутки. Другими пользователями Tarantool являются Badoo, Avito, Qiwi, Wallarm и так далее.

Подробнее о Tarantool вы можете узнать на официальном сайте [http://tarantool.org/](http://tarantool.org/ "http://tarantool.org/") и странице на Facebook [https://www.facebook.com/TarantoolDatabase/](https://www.facebook.com/TarantoolDatabase/ "https://www.facebook.com/TarantoolDatabase/").

<cut>

### Azure Marketplace

Мы уже [рассказывали о назначении Azure Marketplace](https://habrahabr.ru/company/microsoft/blog/264449/) и подробностях использования магазина как для разработчиков и ИТ-профессионалов для развертывания сложных сторонних решений, так и для независимых разработчиков ПО (ISV), желающих выйти на новые для себя рынки распространения своих решений.

Множество ISV уже сертифицировали свои решения для Azure и разместили их в Azure Marketplace, среди них Red Hat, Oracle, CoreOS, MariaDB, Elasticsearch и сотни других. Подробнее про некоторые можно прочитать в [этой статье](https://habrahabr.ru/company/microsoft/blog/278367/), а полный список решений всегда доступен на [официальном сайте Azure Marketplace](https://azure.microsoft.com/ru-ru/marketplace/virtual-machines/all/).

### Tarantool & Azure Marketplace

Мы рады сообщить, что теперь и решение Tarantool сертифицировано и доступно для пользователей Azure из Azure Marketplace. Вы можете найти описание решения на отдельной [странице в магазине](https://azure.microsoft.com/ru-ru/marketplace/partners/my-com/tarantool/).

> _Мы очень рады представить базу данных Tarantool сообществу разработчиков на облачной платформе Microsoft Azure. Azure Marketplace позволит упростить развертывание Tarantool в облачном окружении и снизить порог входа для разработчиков, которым необходимо надежное производительное решение на базе открытого кода для хранения и обработки данных._
> 
> _Tarantool - это база данных и кэш в одном флаконе. Он сочетает преимущества традиционных баз данных - надежное хранение, транзакции, вторичные индексы, серверный язык запросов - и при этом он работает с молниеносной скоростью кэша, позволяя достигать времени выполнения запроса в доли миллисекунды и пропускную способность в миллионы транзакций в секунду._
> 
> _- **Денис Аникин**, технический директор почтовых и облачных сервисов Mail.ru_

![](https://habrastorage.org/files/b1c/200/958/b1c2009583c848d28659ea60d3d9fe54.png)

Решение Tarantool, размещенное в Azure Marketplace, предлагается бесплатно, пользователь Azure оплачивает только вычислительные мощности, на которых он развернет базу данных. Напомню, что в Azure действует поминутная тарификация.

**Создание Tarantool в Azure**

Продемонстрирую, как легко и просто теперь развернуть БД Tarantool в Azure. На [странице решения в Azure Marketplace](https://azure.microsoft.com/ru-ru/marketplace/partners/my-com/tarantool/) щелкните на кнопку “Создание виртуальной машины”. Или выберите Tarantool в списке решений на портале своей учетной записи Azure.

![](https://habrastorage.org/files/6ce/959/8ee/6ce9598ee189417a99cfb195a28680d8.png)

Вы можете ознакомиться с описанием решения и для его развертывания нажать кнопку Create (Создать).

![](https://habrastorage.org/files/6a3/2eb/302/6a32eb3024c14ea58f03b1189372b39e.png)

Запустится мастер развертывания, который запросит у вас вводные параметры, такие как имя VM, имя и пароль пользователя для доступа по SSH, подписку и группу ресурсов, в которую следует развернуть решение, ЦОД Azure.

![](https://habrastorage.org/files/f84/2af/b27/f842afb275b64afca73b55653c337b7a.png)

На втором шаге вам будет предложено выбрать размер VM, на которой будет развернута БД Tarantool. Вы можете выбрать одну из предложенных VM или задать свой размер:

![](https://habrastorage.org/files/176/624/044/176624044c194e24a4b5b843c4fad4e4.png)

На третьем шаге можно сконфигурировать дополнительные опции и произвести тонкую настройку развертывания. Вы можете оставить все по умолчанию и перейти к шагу четыре.

![](https://habrastorage.org/files/9f9/aad/20b/9f9aad20bd1a4b7ba2c7a00cb25582e8.png)

Четвертый шаг знакомит вас с заданными параметрами, которые вам просто необходимо подтвердить. Просто нажмите “ОК” для перехода к финальной части.

![](https://habrastorage.org/files/764/8a3/946/7648a394692046699141e5ada273cb99.png)

Последним шагом вы должны ознакомиться с условиями приобретения и развертывания решения и запустить развертывание, нажав на кнопку Purchase (Приобрести).

![](https://habrastorage.org/files/88e/afa/255/88eafa2557844c1e8a42988f6300413c.png)

После этого будет запущен процесс развертывания решения БД Tarantool в вашей подписке с указанными параметрами.

![](https://habrastorage.org/files/73f/115/379/73f1153798484f95b41b788bc944ff0c.png)

Вам нужно просто подождать несколько минут, пока VM с настроенным Tarantool будет развернута и вы получите доступ к работающей виртуальной машине с готовой к работе БД Tarantool.

![](https://habrastorage.org/files/74e/67d/b4e/74e67db4e7944920af821b4ecc430b0c.png)

После этого вы можете подключиться по SSH к вашей машине с Tarantool:

![](https://habrastorage.org/files/427/1db/1c7/4271db1c75e94b9388633ce749b59821.png)

### Заключение

Мы рассмотрели развертывание нового решения БД Tarantool в облаке Microsoft Azure с помощью магазина Azure Marketplace. Благодаря сертификации и публикации в магазине, разработчики и ИТ-профессионалы теперь могут значительно проще и быстрее развертывать Tarantool в Azure, используя при этом официальные образы VM от создателя.

В следующих статьях мы еще вернемся к теме Tarantool в Azure.

### Полезные ссылки

Вы можете узнавать последние новости о платформе Azure и в том числе о Azure Marketplace в официальном блоге [http://azure.microsoft.com/blog](http://azure.microsoft.com/blog).

<iframe height="360" src="https://channel9.msdn.com/Series/Cloud-Azure-Introduction-to-the-web-services-for-development/azure-marketplace-russia/player" frameborder="0" width="650" allowfullscreen="allowfullscreen"></iframe>

Подпишитесь в Твиттере на канал [Microsoft Partner Apps](https://twitter.com/MSPartnerApps), чтобы узнавать больше о новых решениях и технологических новинках независимых разработчиков ПО.

Более 3300 разнообразных решений вы всего сможете найти на странице [Azure Marketplace](http://azure.microsoft.com/en-us/marketplace/).

</cut>
