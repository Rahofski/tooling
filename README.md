# tooling Rakhov Roman's report

# Вкладка Network

1. Профиль загрузки ресурсов лежит в папке har

2. Неоптимальные места:

- Дублирование ресурсов:

Сортируем ресурсы по колонке Name и ищем повторяющиеся

Был обнаружен скрипт advanced.4fdec4f0c66230612adf.js, загружающийся дважды.

![watch.js](./screenshots/duplication_1.jpg)

Скрипт watch.js загружается трижды

![watch.js](./screenshots/duplication_2.png)

- Лишний размер ресурса:

Сортируем ресурсы по колонке Size

Четыре фотографии, подгруженные в формате .webp, весят непозволительно много - от 2400 кБ!

![photos.webp](./screenshots/photos.jpg)

- Медленно загружающиеся ресурсы:

Сортируем ресурсы по колонке Time 

Все фотографии, представленные в пункте выше, загружаются от двух до шести секунд, что считается медленным

Также медленно загружается событие типа event - порядка 5 секунд

![event](./screenshots/event.jpg)

- Ресурсы, блокирующие загрузку:

Во вкладке Perfomance можно определить, блокирует ли ресурс загрузку, с помощью наведения на него курсора: у такого ресурса будет поле 'Render blocking'

Таких ресурсов было обнаружено несколько:

![block](./screenshots/block_1.jpg)
![block](./screenshots/block_2.jpg)
![block](./screenshots/block_3.jpg)


- Дополнительно:

Два неудачных ответа с бэка

![back_fail](./screenshots/back_fail.png)



# Вкладка Performance 

1. Файл профиля загрузки страницы находится в папке performance

2. Время от начала навигации:
FCP - 1220 ms
LCP - 1220 ms
DCL - 1720 ms
Load - 11600ms

![events_time](./screenshots/events_time.png)

3. DOM-элемент с LCP

Нажав на LCP в левой части экрана, видим следующую информацию:

![element_lcp](./screenshots/lcp_info.png)

По нажатию на p открывается параграф в верстке  с текстом:

![p_lcp](./screenshots/p_lcp.png)

4. Время на разные этапи обработки

Откроем раздел Summary в нижней части экрана и найдем там время:

Scripting: 687 ms
System: 422 ms
Rendering: 178 ms
Painting: 66 ms
Loading: 29 ms
Messaging: 2 ms

![step_time](./screenshots/step_time.png)


# Вкладка Coverage 

1. Скриншот вкладки загрузки страницы

![coverage_screeshot](./screenshots/coverage.png)

2. Объем неиспользованного CSS в килобайтах:

Объем неиспользованного css: 428 кБ

![unused_css](./screenshots/unusedcss.png)


Объем неиспользованного js: 1838 кБ

![unused_js](./screenshots/unusedjs.png)


