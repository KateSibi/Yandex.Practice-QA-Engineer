## Задание 1: Теория тестирования

<details>
<summary>Вопросы / Ответы</summary>

<details>
<summary>1. Почему практики тест-дизайна нельзя применять сразу после получения требований?</summary>

> Прежде чем применять техники тест-дизайна, необходимо проанализировать тестируемый объект. Изучить его документацию, пообщаться с разработчиками, узнать как он работает и как спроектирован. Зная информацию о продукте, получится определить какие техники необходимо использовать для определенного вида тестирования. И, использую полученные знания, необходимо составить набор тестов (чек-листов/тест-кейсов). 
</details>

<details>
<summary>2. В какой ситуации классы эквивалентности и граничные значения могут существовать по отдельности? Аргументируй свой ответ и приведи примеры.</summary>

> Класс эквивалентности может быть представлен в виде диапазона и набора значений.  
Диапазон – интервал чисел с границами: например, 1 – 10. В данном случае можно выделить граничные значения: 1 и 10; 0 и 11; 2 и 9  
Набор значений – множество значений: например список праздников. В данном случае нельзя выделить ГЗ.  
Исходя из выше сказанного, можно сделать вывод, что КЭ и ГЗ могу существовать по отдельности.  
</details> 

<details>
<summary>3. Что такое эквивалентность? Что такое класс эквивалентности?</summary>
  
> Эквивалентность – это равноценность объектов.  
Классы эквивалентности - это разделение данных на наборы/диапазоны, с которыми тестируемое приложение должно работать одинаково.
</details>

<details>
<summary>4. Можно ли исключить проверку в середине диапазона в пользу проверок на границах, входящих в диапазон? Аргументируй свой ответ.</summary>

> Нельзя, т.к.  это разные тесты - метод эквивалентного разбиения и проверка граничных значений.  
Суть техники эквивалентного разбиения в том, чтобы разделить данные на КЭ и из каждого класса выбрать одно значение для проверки. В то время как проверка граничных значение основана на проверке значений на границах КЭ.
</details>

<details>
<summary>5. Представь, что тебе нужно протестировать форму: у каждого поля есть валидатор. Результат работы формы зависит от комбинации данных в полях. Какие практики тест-дизайна следует применить и почему? Аргументируй свой ответ.</summary>
  
> 1. Позитивные и негативные проверки  
Позитивные проверки – чтобы проверить, что приложение работает без ошибок согласно требованиям.  
Негативные проверки – чтобы проверить, что приложение продолжает работать без ошибок и реагирует так, как описано в требованиях.
> 2. Применение техник КЭ и ГЗ  
– выделить КЭ: диапазон/набор (чтобы протестировать, что приложение одинаково обрабатывает эквивалентные значения)  
– у КЭ с типом диапазон определить ГЗ (чтобы исключить появление ошибок на границах КЭ)
Таким образом количество проверок будет сведено к минимум, но при этом будут проверены валидные и невалидные данные
> 3. Таблица принятия решений – данный метод позволит проверить различные комбинации
> 4. Попарное тестирование  – проверка всех комбинаций пар параметров. Если пара параметров вызвала ошибку в комбинации с другими параметрами, с большой вероятностью та же пара вызовет ошибку и в другой комбинации. Поэтому достаточно протестировать только уникальные пары вариантов.
</details>

<details>
<summary>6. Какими способами можно оптимизировать количество проверок при работе с таблицами принятия решений? Аргументируй свой ответ.</summary>
  
> Для оптимизации количества проверок необходимо исключить зависимые параметры (чем больше зависимых параметров, тем меньше проверок). В случает если тестируется приложение с большим количеством параметров и их значений, то эффективныее использовать технику попарного тестирования. 
</details>

<details>
<summary>7. Опиши, чем чек-лист отличается от тест-кейсов. Приведи примеры, где применяют и то, и другое.</summary>
> Чек-лист отличается от тест-кейса степенью подробности. В чек-листе нет подробных шагов кейса, для использования чек-листа при тестировании очень много информации нужно держать в голове и знать логику работы приложения на отлично.  
При разработки документации для нового продукта эффективнее один раз уделить немного больше времени на проверку и написать по ней тест-кейсы и чек-листы, чтобы потом экономить время при следующих проверках.
</details>

<details>
<summary>8. Как правильно составить баг-репорт? Какие элементы баг-репорта — обязательные? Почему?</summary>

  > Правила оформления записей в баг-трекере в каждой компании свои — это зависит как от политики компании, технологии разработки, используемного баг-трекера, типа проекта и много чего еще. Но в любом случае хороший баг-репорт обладает определенными характеристиками:  
1. ID – eникальный номер баг-репорта  
2. Заголовок – cуть ошибки  
3. Шаги воспроизведения – пошаговая инструкция, как воспроизвести баг  
4. Результаты – описание ОР и ФР  
5. Окружение – ОС, браузеры или версии приложений, в которых возникает ошибка  
6. Приоритет – критичность ошибки и срочность её исправления  
</details>

<details>
<summary>9. По каким правилам составляют заголовок баг-репорта? Что будет, если составить заголовок неправильно?</summary>
  
> Заголовок баг-репорта – это та часть репорта, которую разработчики видят первой. Он должен представлять собой краткое описание бага. 
Общие заголовки вроде "Поиск не работает" не очень полезны. Что именно не работает? Система выдаёт результаты, не соответствующие запросу? Поиск длится слишком долго? Вариант "При нажатии на кнопку поиска функция не срабатывает" более информативен. Хорошие заголовки снижают вероятность появления дублирующихся репортов, а также позволяют разработчику быстрее найти нужный ему отчет.
</details>

<details>
<summary>10. Из чего состоит клиент-серверная архитектура приложения? Кратко опиши функциональность каждого элемента.</summary>
  
> Клиент-серверная архитектура – это способ организации работы приложений, в котором выделяют следующие три элемента:
> 1. Клиент – приложение, с которым работает пользователь. Клиентов может быть много  
> 2. Сервер – система, к которой обращаются клиенты, чтобы получить данные  
> 3. Сеть – система из нескольких устройств, которая помогает клиенту и серверу обмениваться данными  
> Схематично работу КСА можно представить:  
> Клиент → Сервер → БД  
> БД → Сервер → Клиент  
</details>

<details>
<summary>11. Опиши этапы обработки запроса после того, как в адресную строку браузера вводят URL: https://yandex.ru.</summary>
  
> Когда вводится запрос в адресную строку в браузере, инициируется запрос к DNS-серверу (Domain Name System – система доменных имен).
DNS-сервер возвращает браузеру IP-адрес.  
IP-адрес – это уникальный идентификатор сервера, на котором находится нужная информация: например, 198.221.33.12. К нему обращается клиент.
</details>

<details>
<summary>12. Что такое кэш? Зачем он нужен? Какое правило нужно соблюдать при работе с кэшем в тестировании?</summary>
  
> Кэш (Cache Storage) – это данные веб-страниц, хранящиеся на компьютере после того, как открываются страницы: изображения, аудио-, видео-, CSS-, HTML-, JS-файлы.  
Он нужен, чтобы при следующем посещении веб-страница загрузилась быстрее: браузер возьмет файлы из локального хранилища, а не с сервера.
</details>

<details>
<summary>13. Ты знаешь, что есть протоколы HTTP и HTTPS. Чем отличаются HTTP и HTTPS? В каких случаях не стоит пользоваться HTTP? Из каких компонентов состоит HTTP запрос: за что отвечает каждый? Какие HTTP-методы ты знаешь? За что они отвечают? Приведи примеры применения разных методов. Что такое код HTTP-ответа? Какие коды бывают?</summary>
  
> 1. HTTP (HyperText Transfer Protocol – протокол передачи гипертекста) передает данные в незащищенном виде. На сайтах, которые отправляют данные по HTTP, можно перехватить и украсть личную информацию. Например, данные банковской карты.  
Чтобы обеспечить безопасность, применяют протокол HTTP c расширением защиты – HTTPS (HyperText Transfer Protocol Secure — протокол защищённой передачи гипертекста). Он шифрует соединение по криптографическим протоколам: так клиент и сервер смогут безопасно обмениваться данными.  

> 2. HTTP-запрос состоит из трех блоков:  
– стартовая строка (состоит из трех элементов: метода, пути до ресурса и версии протокола)  
– заголовки (доп. информация от фронтенда бэкенду)  
– тело сообщения (данные, которые передает фронтенд)  

> 3. HTTP-методы указывают действие: сервер принимает его в обработку. Самые распространенные:  
 – GET (запросить данные у бэкенда по определенному адресу)  
– POST (передать данные на бэкенд)  
– PUT (изменить данные на бэкенде)  
– DELETE (удалить данные на бэкенде)  

> 4. HTTP-ответ состоит из трех блоков:  
– стартовая строка (включает версию протокола, код состояния, текст состояния)  
– заголовки (доп. информация о бэкенде и типе данных для фронтенда)  
– тело сообщения (бэкенд отдает результат выполнения запроса)  
Коды состояний могут быть:  
– 1хх - Информационные сообщения (102 - запрос принят, но обработка ещё не завершена)  
– 2хх - Сообщения об успехе (200 - ОК, запрос обработан успешно)  
– 3хх - Перенаправление (302 - запрошенный ресурс временно доступен по другому адресу)  
– 4хх - Клиентские ошибки (404 - страница, которую запросил клиент, не найдена на сервере)  
– 5хх - Ошибки сервера (500 - внутренняя ошибка сервера)  
</details>

<details>
<summary>14. Опиши, из каких компонентов может состоять URL. За что отвечает каждый из них?</summary>
  
> URL (Uniform Resource Locator - унифицированный указатель ресурса) – это адрес веб-ресурса. URL может состоять из следующих компонентов:
> 1. Схема (scheme) – протокол, по которому передаются данные
> 2. Логин:пароль (username:password) указывают серверу, какой пользователь к нему обратился
> 3. Символ @ (at коммерческое, «собака») отделяет логин:пароль и имя хоста:порт (hostname:port)
> 4. Имя хоста:порт (hostname:port) – доменное имя или IP-адрес сервера, к которому обращается пользователь
> 5. Путь (path) – месторасположение ресурса
> 6. Параметры запроса (query) – дополнительные параметры вида ключ=значение
> 7. Фрагмент текста (fragment), или якорь (anchor) – дополнительный указатель, он позволяет сразу попасть в нужную часть веб-страницы
</details>

<details>
<summary>15. Какие виды мобильных приложений бывают? В чём особенность каждого?</summary>
  
> Мобильные приложения бывают:
> 1. Веб-приложения используют клиент-серверную архитектуру и адаптированы под мобильные устройства. Такие приложения не нужно устанавливать.  Веб приложения являются адаптацией сайтов для пользователей мобильных устройств. Они создаются, чтобы посетители могли заходить на сайт в любое время, даже без доступа к компьютеру.
> 2. Нативные приложения нужно устанавливать: сначала скачивают установочный файл.  
Нативные приложения создаются для конкретной операционной системы (iOS, Android, Windows), могут работать независимо от подключения к интернету.
> 3. Гибридные приложения комбинируют свойства двух предыдущих: в основе «гибрида» - нативное приложение, его пишут отдельно под каждую платформу. Веб-содержание наполняют HTML, CSS и JavaScript - они могут быть едины для всех платформ.
> 4. Такие приложения имеют ограниченный доступ к аппаратной части смартфона (камера, микрофон, геолокация, адресная книга), требуют подключения к интернету, поскольку загружают контент из внешнего источника, размещенного на сервере.  
> У гибридных программ есть недостатки: сервисы оперируют малым объемом информации, а дизайн не адаптируется к размеру и расширению экрана, что может вызвать неудобства.
</details>

<details>
<summary>16. Чем эмулятор отличается от реального устройства? Кратко опиши недостатки и преимущества при тестировании.</summary>
  
> Эмулятор имитирует работу устройства с разными параметрами и функциональностью (например, можно задать определенную версию ОС и разрешение экрана):
> Преимущества:
> - Позволяют запускать приложение на виртуальном аналоге устройства
> – Могут использоваться в работе с автотестами.
>   Недостатки:
> - Имеется ряд ограничений, таких как работа с камерой, звонки, или бесконтактная оплата
> - Запуск эмуляторов и подготовка к работе обычно занимают две-три минуты, но если необходимо запустить сразу несколько эмуляторов, то это может стать проблемой на слабых ПК
> - Невозможно учесть такие факторы как перегрева/разряда аккумулятора и конфликт с другими приложениями

> Реальные устройства:
> Преимущества:
> - Максимально приближенная среда, что позволяет проверять приложение именно на тех моделях устройств и версиях прошивок, которыми пользуются пользователи
> - Возможность нормально работать с анимациями, бесконтактной оплатой, камерой и прочими специфическими кейсами
> Недостатки:
> - Высокая цена формирования: постоянно требуется обновлять модельный ряд.
> - Высокая стоимость поддержки: вздувшиеся батареи, порванные провода, разбитые экраны, брак и прочие неисправности
> - Невозможно купить все девайсы, на которые ставят приложение пользователи"
</details>

<details>
<summary>17. Проверь, есть ли ошибки в JSON. Если да, напиши номер строки с ошибкой, опиши ошибку и предложи исправление.</summary>

![diploma-29](https://github.com/KateSibi/Yandex.Practice-QA-Engineer/assets/117051965/decd0cff-1119-4b7e-b789-a59baecfe849)

> **Строка 3:** Файл взять в " "
> **Строка 4:** после : поставить {
> **Строка 15:** после "save_as_doc" поставить :
> **Строка 21:** после "snow_print_option" вместо : и { поставить ,
> **Строка 28:** убрать }

</details>

<details>
<summary>18. Что такое реляционная база данных? Чем она отличается от нереляционной?</summary>
  
>Реляционная база данных (SQL) — база, где данные хранятся в формате таблиц, они строго структурированы и связаны друг с другом. В таблице есть строки и столбцы, каждая строка представляет отдельную запись, а столбец — поле с назначенным ей типом данных. В каждой ячейке информация записана по шаблону.
>Отличие между реляционной (SQL) и нереляционной (NoSQL) базой данных заключается в том, что реляционная база данных хранит данные в таблицах, в то время как нереляционная база данных хранит данные в формате ключ-значение, в документах или каким-либо другим способом без использования таблиц, таких как реляционная база данных.
</details>

<details>
<summary>19. Напиши, какие виды JOIN бывают. В чем особенность каждого?</summary>
  
> JOIN – оператор языка SQL, предназначенный для выбора данных из двух таблиц и включения их в один результирующий набор.
> В зависимости от того, какие правила объединения применяются, выделяются несколько типов оператора JOIN:
> - INNER JOIN или просто JOIN (внутреннее соединение): показывает только те записи, для которых нашлись пары. Остальные он просто не выведет.
> - LEFT JOIN (левое соединение): выводит все записи первой таблицы, а для не найденных пар из второй проставит значение NULL.
> - RIGHT JOIN (правое соединение): выводит все записи второй таблицы, а на место недостающей информации из первой таблицы подставит NULL.
> - FULL JOIN  или OUTER JOIN (внешнее соединение): работает как одновременно левый (LEFT) и правый (RIGHT) JOIN, и выводит все записи из обеих таблиц.
</details>

<details>
<summary>Исходные данные для заданий 20 – 22</summary>

Ты тестируешь сервис, который доставляет еду за 30 минут. Пока это маленький стартап, поэтому ты работаешь всего с четырьмя таблицами:  

`Orders` —  все доставленные заказы;  
`ORDERS_ID` — ID заказов, int;  
`USER_ID` — ID пользователей, int;  
`EMPLOYEE_ID` — ID сотрудников, int;  
`DELIVERY_TIME` — время доставки в минутах, int;  
`ITEMS` — список товаров, char;  

`Users` — пользователи;  
`USER_ID` — ID пользователей, int;  
`FULL_NAME` — полное ФИО пользователя, char;  
`PHONE` — номер телефона пользователя, char;  
`ADDRESS` — адрес пользователя, char;  

`Employees` — работники;  
`EMPLOYEE_ID` — ID сотрудника, int;  
`FIRST_NAM`E — имя сотрудника, char;  
`LAST_NAME` — фамилия сотрудника, char;  
`PHONE` — телефон сотрудника, char;  
`JOB_ID` — ID специализации, int;  

`Jobs` — типы работ в сервисе;  
`JOB_ID` — ID специализации, int;  
`JOB_TYPE` — тип специализации, char;  
`HOURS` — число рабочих часов в неделю, int;  
`SALARY` — зарплата сотрудника с данной специализацией в рублях, int;  

![diploma-33](https://github.com/KateSibi/Yandex.Practice-QA-Engineer/assets/117051965/f3921a20-6eab-4208-aab3-b6e7bb7d7cae)

</details>

<details>
<summary>20. В службу поддержки пришло много жалоб: заказы, в которых есть гречка, доставляют почти час, хотя сервис обещает успеть в 30 минут.</summary>

Проверь, действительно ли курьеры опаздывают. Выбери все заказы, где есть хотя бы один товар - «гречка» и время доставки свыше 30 минут. В результирующей таблице должны быть ID заказов и ID курьеров.  

В ответе приложи SQL-запрос.  

**Решение:**

```
SELECT Orders.ORDERS_ID, Orders.EMPLOYEE_ID 
  FROM Orders 
WHERE DELIVERY_TIME > 30 AND ITEMS =  '%гречка%'
```
</details>

<details>
<summary>21. Менеджер предложил добавить новую функциональность в продукт: мониторинг, который показывает самых активных клиентов за всё время работы компании.</summary>

Проверь, что список пользователей корректно выводится на экран. На этом этапе разработки достаточно проверить только ID клиентов.  
Выбери пять самых активных клиентов по количеству заказов.  
В результирующую таблицу выведи ID каждого пользователя и число заказов.  
Отсортируй данные по убыванию числа заказов, выбери пять самых активных клиентов.  

В ответе приложи SQL-запрос.  

**Решение:**

```
SELECT Users.USER_ID, COUNT(Orders.ORDERS_ID) as orders_cnt
  FROM Orders
GROUP BY USER_ID
ORDER BY orders_cnt DESC
LIMIT 5;
```
</details>

<details>
<summary>22. Из бухгалтерии пришёл баг-репорт: зарплаты сотрудников рассчитываются некорректно. Оказалось, что почти все ошибки в расчётах — в расчётных листах менеджеров.</summary>

Выведи список ID всех сотрудников, у которых в специализации содержится «менеджер», с зарплатой больше 70 000 рублей.  

В ответе приложи SQL-запрос.  

**Решение:**

```
SELECT Employees.EMPLOYEE_ID
  FROM Employees
INNER JOIN Jobs ON Employees.JOB_ID = Jobs.JOB_ID
WHERE Jobs.JOB_TYPE LIKE '%менеджер%' AND Jobs.SALARY > 70000;
```
</details>

<details>
<summary>23. Изучи три ситуации и ответь на вопрос: стоит ли писать автотесты в этом случае? Аргументируй свой ответ.</summary>

1) Проект существует давно, у него написано много ручных тестов.
2) Проект временный: продлится всего несколько месяцев.
3) Проект нестабилен: в функциональность часто вносят изменения.

**Ответ:**
> 1) Если проект существует давно и имеет много ручных тестов, то имеет место автоматизация тестирования, т.к. это сократит время проведения тестов после выхода обновления
> 2) В случае временного проекта написания автотестов нецелесообразно, т.к. написать ручные тесты будет намного быстрее и проще
> 3) В случае нестабильного  также нецелесообразно написание автотестов, из-за частых изменений придется вносить правки в автотесты, эффективнее будет ручное тестирование"

</details>
</details>


## Задание 2: Веб-приложение Яндекс.Самокат

1) Разработай mindmap для формы заказа самоката. Отобрази логику работы и вёрстку.

[Mind-map для формы заказа](https://xmind.works/share/DH8YqywU)

2) Составь чек-лист по требованиям к экрану «Статус заказа».
   
[Чек-лист: Статус заказа](https://github.com/KateSibi/Yandex.Practice-QA-Engineer/files/12641373/-._.pdf)

3) Для экрана «Сделать заказ» составь проверки на валидацию полей.</summary>

[Чек-лист: Валидация полей](https://github.com/KateSibi/Yandex.Practice-QA-Engineer/files/12641380/-._.-.1.pdf)


## Задание 3: Мобильное приложение Яндекс.Самокат

### Задание
  
1) Обрати внимание на техническую информацию при запуске приложения.  
2) Изучи требования к приложению — [здесь](https://praktikum.notion.site/fbb847fa63244f5db3272bc8034ca7fd).  
3) Спроектируй тест-кейсы и протестируй функциональность, которая выделена жирным шрифтом. Не забудь написать кейсы и на вёрстку по макетам к этой функциональности. Макеты лежат в Figma [здесь](https://www.figma.com/file/kqLqPvSvjLVLomkdadkAnk/mobile?type=design&node-id=0-1&mode=design&t=tzhnMtaTtiMW8sOl-0).  
  
### Ответ

[Тест-кейсы проверки функциональности](https://github.com/KateSibi/Yandex.Practice-QA-Engineer/files/12641404/-.1.pdf)

## Задание 4: API приложения Яндекс.Самокат

### Задание

1) Обрати внимание на техническую информацию при запуске приложения.
2) Изучи требования к бэкенду и документацию к API. Требования к бэкенду — [здесь](https://praktikum.notion.site/20389c6a65da49fb8e22720c4356887c).
3) Разработай чек-лист и протестируй API по требованиям, которые выделены жирным шрифтом.

### Ответ
[Чек-лист API](https://github.com/KateSibi/Yandex.Practice-QA-Engineer/files/12641413/-.1.pdf)


