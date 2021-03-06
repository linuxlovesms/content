{name}Vladimir Yunev{/name}{company}Microsoft{/company}{title}Развертывание Red Hat на Microsoft Azure{/title}{cat}0{/cat}{date}12.04.2016{/date}{desc}Развертывание Red Hat на Microsoft Azure{/desc}

Разработчики, которые создают решения на базе Red Hat могут легко
размещать свои решения в облачной платформе Microsoft Azure. Проще всего
это сделать с помощью виртуальных машин.

Для упрощения работы с виртуальными машинами в облаке Azure предлагается
площадка Azure Marketplace, в которой находятся сотни заранее
настроенных виртуальных машин с разным окружением и установленными
инструментами, включая операционные системы, базы данных, среды,
фреймворки, CMS и так далее.

Рассмотрим, как любой пользователь Azure может развернуть Red Hat за
несколько минут.

Поиск Red Hat в Azure Marketplace
=================================

> *Подразумевается, что у вас уже есть учетная запись Microsoft Azure.
> Если это не так, то воспользуйтесь бесплатным [триал-предложением по
> этой ссылке](https://azure.microsoft.com/ru-ru/free/).*

Перейдите на портал Microsoft Azure по ссылке <http://portal.azure.com>,
вы откроете панель управления облачными мощностями Microsoft Azure,
предоставленными вам по запросу (рисунок 1).

![](https://github.com/linuxlovesms/content/blob/master/media/rh1.png?raw=true)


*Рис.1 – Портал Microsoft Azure*

Нажмите на кнопку «Создать» для добавления нового компонента в свою
учетную запись. В нашем случае мы намереваемся добавить виртуальную
машину с Red Hat. Введите в строку поиска Red Hat. Вы получите полный
список доступных в Azure Marketplace конфигураций Red Hat на выбор
(рисунок 2).

![](https://github.com/linuxlovesms/content/blob/master/media/rh2.png?raw=true)


*Рис.2. – Список Red Hat в Azure Marketplace*

Выберите Red Hat Enterprise Linux 7.2 и в новом информационном окне
нажмите кнопку «Создать». Теперь вы перейдете к непосредственному
созданию виртуальной машины, выбранной из Azure Marketplace (рисунок 3).

![](https://github.com/linuxlovesms/content/blob/master/media/rh3.png?raw=true)


*Рис.3. – Создание виртуальной машины*

Создание VM с Red Hat
=====================

Чтобы создать виртуальную машину, в нашем случае с Red Hat на борту,
необходимо указать ряд параметров. В первую очередь ввести название
виртуальной машины. Затем имя пользователя (администратора) и пароль
доступа. Выбрать подписку Azure, если у вас их несколько.

Важный параметр, который необходимо указать – это группа ресурсов. В
целом, группа ресурсов – это просто объединение разных облачных ресурсов
– VM, хранилища, сетей – под одним именем для упрощения
администрирования. Поэтому, на данном этапе просто введите название для
группы.

Последний параметр, который нужно указать на первом шаге – расположение
виртуальной машины – по существу выбор одного из ЦОД Microsoft Azure,
которые расположены по всему миру. Ближайшие к России ЦОД – это Северная
или Западная Европа. Выберите один из них.

![](https://github.com/linuxlovesms/content/blob/master/media/rh4.png?raw=true)


*Рис.4. – Параметры первого шага создания виртуальной машины*

Нажмите «ОК» после ввода всех параметров. На втором шаге вам предложат
выбрать размер виртуальный машины. По умолчанию будут представлены
несколько типов машин, которые рекомендуются для данного типа решения.
Но вы всегда можете выбрать другой размер нажав на «Просмотреть все»
(рисунок 4).

![](https://github.com/linuxlovesms/content/blob/master/media/rh5.png?raw=true)


*Рис.4. – Выбор размера виртуальной машины*

Я предлагаю выбрать вам размер «A1 Базовый» как подходящий для
тестирования. После выбора нажмите кнопку «Выбрать», чтобы перейти к
третьему шагу.

На третьем шаге производится тонкая настройка развертывания. Здесь все
параметры можно оставить по умолчанию и вообще ничего не менять. Но если
требуется, что вы можете выбрать SSD-хранилище для VM, настроить
виртуальную сеть, безопасность, включить мониторинг, создать группу
доступности для отказоустойчивой работы VM (рисунок 5).

![](https://github.com/linuxlovesms/content/blob/master/media/rh6.png?raw=true)


*Рис.5. – Тонкие настройки развертывания VM*

Нажмите «ОК» после тонкой настройки для того, чтобы перейти к финальным
шагам и запуску виртуальной машины.

Вы получите информационное окно с перечислением ваших настроек (рисунок
6).

![](https://github.com/linuxlovesms/content/blob/master/media/rh7.png?raw=true)


*Рис.6. – Информационное окно с настройками*

Ознакомьтесь с информацией и нажмите «ОК» для того для того чтобы
запустить процесс развертывания вашей виртуальной машины с Red Hat на
борту.

Вы увидите информационное сообщение «Развертывание начато…» (рисунок 7).

![](https://github.com/linuxlovesms/content/blob/master/media/rh8.png?raw=true)


*Рис.7. – Развертывание начато*

Как только VM будет готова вы получите еще одно информационное
сообщение, а на портале откроется панель управления созданной VM
(рисунок 8). В общем случае, создание виртуальной машины занимает
несколько минут.

![](https://github.com/linuxlovesms/content/blob/master/media/rh9.png?raw=true)


*Рис.8. – Панель управления виртуальной машиной*

Поздравляю! Вы развернули свою машину с готовым Red Hat.

Управление развернутой виртуальной машиной
==========================================

Для того чтобы убедиться в работоспособности виртуальной машины первым
делом мы можем подключиться к ней по общедоступному адресу через SSH.

Вы можете найти общедоступный адрес в заголовке панели
администрирования. В моем случае это 52.169.165.229.

Вам может быть интересно то, как получить FQDN-адрес для своей машины в
виде доменного имени. По умолчанию для VM адрес не сопоставляется, но
его можно легко получить. Для этого перейдите в настройки VM (Все
параметры) на панели конфигурации. Затем выберите пункт «Конфигурация» и
в панели настройки укажите наименование для вашей VM, которое будет
включено в FDQN-путь (рисунок 9).

После сохранения настроек вы сможете использовать ссылку, которая будет
представлена в виде (мой случай)
<http://vyuredhat.northeurope.cloudapp.azure.com/>.

![](https://github.com/linuxlovesms/content/blob/master/media/rh10.png?raw=true)


*Рис.9. – Добавление FDQN-пути для виртуальной машины*

Этот же адрес вы теперь сможете использовать для доступа по SSH к вашей
виртуальной машине (рисунок 10), например:

*SSH vyunev@vyuredhat.northeurope.cloudapp.azure.com*

где vyunev – имя пользователя (администратора), которое вы указали при
создании VM.

Или просто используя адрес в любимом инструменте.

![](https://github.com/linuxlovesms/content/blob/master/media/rh11.png?raw=true)

*Рис.10. – Подключение к виртуальной машине по SSH*

Теперь вы можете настроить вашу VM с Red Hat так как душа пожелает!

Поддержка Red Hat для пользователей Azure
=========================================

Одной из особенностей развертывания виртуальных машин в Azure является
встроенная поддержка Red Hat. Вы можете получить ее из панели управления
виртуальной машиной (рисунок 11).

![](https://github.com/linuxlovesms/content/blob/master/media/rh12.png?raw=true)


*Рис.11. – Клиентская поддержка Red Hat в Azure*

Вы можете затем перейти по указанной ссылке и получить квалифицированную
официальную поддержку решений Red Hat в облаке Azure (рисунок 12).

![](https://github.com/linuxlovesms/content/blob/master/media/rh13.png?raw=true)


*Рис.12. – Портал поддержки пользователей Azure и Red Hat*

Заключение
==========

Мы рассмотрели простой пример того, как с помощью Azure и площадки Azure
Marketplace за считанные минуты можно развернуть окружение Red Hat и
получить доступ к готовой рабочей виртуальной машине.

Azure и Azure Marketplace предлагают запустить любые решения построенные
на любой технологии, в том числе для Linux и Windows. Вот лишь краткий
список того, что вы можете найти: Red Hat Enterprise Linux, Oracle
Linux, CentOS, CoreOS, Ubuntu, Suse, WordPress, Moodle, Red Hat, Jboss,
Redmine, SEO Panel, Parse, Git, GitLab, Red Hat, ModX, Memcached, LAMP
Stack, Jenkins, Node.js, SugarCRM, Ruby Stack, Ghost, Subversion,
ActiveMQ, Nginx Stack, Solr, Tomcat, JRuby, OwnCloud, MySQL, Drupal,
MongoDB, Piwik, Dolibarr, LAAP Stack, OpenProject, Plone, eXo, Mahara,
Zurmo, RoundCube, Mautic, ThinkUp, Prestashop, Tracks, phpBB, eZ
Publish, Joomla…

Продолжайте использовать Azure и размещать в облаке свои
opensource-решения. Поможет вам в этом подробный раздел с документацией
и ресурсами [по этой
ссылке](https://azure.microsoft.com/ru-ru/documentation/services/virtual-machines/linux/).
