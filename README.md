# Система информации об автобусных рейсах и билетах

**Use Cases для Web-приложения**

**Страницы:** 

**Домашняя страница**
На нее попадает человек как только зашел на сайт/приложение. 
+ На ней по центру располгаются для ввода откуда/куда, кол-во человек, дата, время. (нужно если человек хочет просто посмотреть есть ли автобусы и их цену и расписание)
+ Сверху справа находится кнопка входа(открывается pop-up с выбором регистрации или входа)
+ Чуть левее от нее находится кнопка маршруты(ссылка на страницу с перечнем всех маршрутов автобусов)

При поиске по фильтрам открывается табло расписаний по времени и маршрутами и ценам, кликнув на который можно узнать о автобусе и купить билеты(только после авторизации), а именно открывается окошко с полями(popup):
+ Номер маршрута
+ Имя водителя
+ телефон водителя
+ Кол-во оставшихся мест
+ всего мест в автобусе
+ цена билета
И кнопка "купить билет"
**Страница входа:**

На эту страницу попадают люди, уже зарегистрированные.
Вбивают
+ логин
+ пароль

Нажимают кнопку "Войти"
При успехе вылетают на домашнюю страницу, где вместо кнопки входа появляется кнопка кабинет
		
**Страница регистрации:**

На эту страницу попадают люди, еще незарегистрированные.
Поля: 
+ Логин
+ Пароль
+ Фамилия
+ Имя
+ Email(чтобы пройти верификацию)
(Если же это админ от компании, то у них свой уникальный ник, который в БД будет помечен как администратор, и по умолчанию будут предоставляться более расширенный контент)

После успешной регистрации они вылетают на домашнюю страницу, где также появляется кнопка кабинет

**«Кабинет»**

По сути, это личная страница каждого клиента/администратора
На ней отображаются поля заполненные при регистрации, помимо которых появляется:
+ адрес
+ телефон
 
Ниже будет сегмент "История покупок" для клиентов. В нем будут отображаться последние 5 покупок(Строчка будет состоять из таких элементов:маршрут, кол-во билетов, цена, дата), если нужна большая информаация, то открываем отдельную старницу.

Сегмент "Автобусы компании" доступен будет только администраторам. Необходимо будет тыкнуть на данную опцию, чтобы перейти на страницу специально для администраторов, где будут располагаться список автобусов, которыми владеет данная компания(откуда сам администратор)

Ниже для всех будет 3 кнопки:
+ Изменить инфо(при нажатии открывается страница изменения инфо)
+ Выйти из аккаунта
+ Удалить аккаунт

**Изменение информации**

Страница, схожая по полям со страницей регистрации + адрес + телефон

**История покупок** 

На ней открывается просто открывается инфо данного клиента по всем его покупкам в базе данных в хронологическом порядке

**Старница "Автобусы компании" для администраторов**
 
Сверху находится поисковое поле, чтобы было легче найти маршрут.
Ниже слева располагается кнопка "Добавить рейс", которая открывает страницу "Новый рейс".
Ниже располагается список всех маршрутов данной компании.

Найдя нужный рейс, админ видит две опции:
+ открыть его, вылетая на страницу "Коррекция маршрута"(Или если можно то достаточно сделать это через popup, чтобы меньше страниц было задействовано)
+ история данного маршрута с фильтром по дате и времени. Найдя нужный автобус, админ открывает его страницу информации("История маршрута")

**Новый рейс**
Эта страница предоставляется админам, для заполнения нового маршрута

Поля:
+ Номер маршрута
+ Откуда
+ Куда
+ Цена билета
+ Кол-во мест в одном автобусе
+ Список остановок(выпадающий список для заполнения)
+ Расписание автобусов

Расписание автобусов заполняется через форму:
+ Номер автобуса
+ Имя водителя
+ Его телефон(для связи клиентов с ним)
+ Время прибытия на каждую отсновку

(По умолчанию каждый автобус занесенный данным администратором будет считаться автобусом данной компании)

После всего заполнения появляется кнопка добавить маршрут и выкидывает обратно на страницу "Автобусы компании".


**"Коррекция Маршрута"**
(или страница или достаточно popup)

Тыкая на маршрут, администратору открывается информация о маршруте. Ниже появляется кнопка изменить или удалить маршрут.
При удалении он удаляется отовсюду. При изменении открываются поля как на странице "Новый рейс"

Дальше просто кнопка "Сохранить"

**История маршрута** 
Свеху фильтр по дате
дальше вылезает список автобусов по данной дате
Дальше в popup открывается инфо по автобусу(его номер, водитель, остановки): 
+ список пассажиров, ссылками на их профили(где есть личная информация для связи в случае ЧП)

**Страница Маршруты**

Сверху находится поисковая строчка по номеру рейчас, ниже фильтр по маршрутам как на домашней странице, плюс фильтр как самый скорый, и тд.
Ниже находится список, удовлетворяющий всем критериям и времени(если ничего не выбрано, то просто общий список)
Открыв любой маршрут(попап) можно увидеть автобусы и их время и список станций(базовый набор инфо: телефон, имя водителя, остановки по времени, цена билета, кол-во мест)

**Действия, доступные в этом приложении после авторизации:**

**Получение списка рейсов по датам, направлениям и промежуточным остановкам, информации о ценах билетов и наличии свободных мест**
На домашней странице выставляем нужное нам по фильтрам.

**Получение списка клиентов, в т.ч. ехавших определенным рейсом, любыми рейсами компании, заказавших билеты**
Данная операция только для администратора компании. Кабинет -> Автобусы компании -> Через поиск находит нужный маршрут -> История маршрута -> по нужной дате находим нужный автобус -> доп инфа -> список ехавших
**Получение истории заказов клиента**
Кабинет -> история покупок
**Заказ билетов на выбранный рейс между выбранными пунктами**
На домашней странице выставляем нужное нам по фильтрам, находим нужный рейс. Тыкаем на него, открывается попап, в котором нажимаем на купить билет
**Добавление и удаление рейса, чтение и редактирование данных о нем**
Доступно только администраторам
Кабинет -> Автобусы компании -> Через поиск находит нужный маршрут -> дальше выбираем нужный блок
+ Коррекция Маршрута (в нем мы можем удалить или изменить инфо о маршруте
+ Новый рейс (для добавления маршрута)
Для клиентов
Дом страница -> Маршруты -> поиск если нужно -> нужный попап
**Добавление и удаление клиента, чтение и редактирование данных о нем**
Дом старницы -> кабинет -> дальше три опции:
+ Изменить инфо(при нажатии открывается страница изменения инфо)
+ Выйти из аккаунта
+ Удалить аккаунт
Для админов в случае надобности Кабинет -> Автобусы компании -> Через поиск находит нужный маршрут -> История маршрута -> по нужной дате находим нужный автобус -> доп инфа -> список ехавших. Это если нужно как-то связаться с людьми по поводу происшествия на автобусе
