# Аналитика объявлений недвижимости
<a href="https://github.com/merekesabitov/Real-Estate-Ad-Analytics/blob/main/Real-Estate-Ad-Analytics.ipynb" style="float: right;">Открыть проект</a>

Проект посвящен анализу архива объявлений о продаже квартир в городе А и ближайших населенных пунктах за несколько лет. Целью является изучение факторов, влияющих на рыночную стоимость недвижимости. Задача состоит в том, чтобы выделить ключевые параметры для создания автоматизированной системы, которая будет выявлять аномалии в данных и предотвращать случаи мошенничества. 

Данные по каждой квартире разделены на две категории:
1. Введенные пользователями вручную.
2. Автоматически сгенерированные на основе картографической информации (например, расстояние до центра города, аэропорта, ближайшего парка или водоема).

---

**Этапы выполнения проекта:**

**Шаг 1. Загрузка и первичное знакомство с данными**  
Загружен файл с данными, и изучена общая информация о датасете **real_estate_ads.csv**.

**Шаг 2. Предобработка данных**  
1. **Заполнение пропущенных значений:**  
   Были изучены пропущенные значения, определены логичные замены для некоторых из них (например, если не указано количество балконов — заменено на 0). Для других типов данных, где замена невозможна, пропуски оставлены, так как отсутствие значения также является важным сигналом.

2. **Приведение данных к нужным типам:**  
   В некоторых столбцах был изменен тип данных, с объяснением, какие именно столбцы требовали изменений и почему.

**Шаг 3. Добавление новых столбцов:**  
В таблицу были добавлены следующие параметры:
- Цена квадратного метра.
- День недели, месяц и год публикации объявления.
- Этаж квартиры: первый, последний или другой.
- Соотношение жилой и общей площади, а также отношение площади кухни к общей.

**Шаг 4. Исследовательский анализ данных:**  
1. Изучены параметры: площадь, цена, число комнат, высота потолков. Построены гистограммы для каждого из параметров.
2. Проанализировано время продажи квартиры: построена гистограмма, рассчитаны среднее и медиана. Описано, сколько обычно занимает продажа квартиры, когда процесс можно считать быстрым, а когда — необычно долгим.
3. Удалены редкие и выбивающиеся значения с описанием найденных особенностей.
4. Анализ факторов, влияющих на стоимость квартиры, включал:
   - Зависимость цены от площади, числа комнат, удаленности от центра.
   - Влияние этажа (первый, последний, другой) на стоимость.
   - Влияние даты размещения (день недели, месяц, год).
5. Выбраны 10 населенных пунктов с наибольшим количеством объявлений. Рассчитана средняя цена квадратного метра в этих населенных пунктах. Выделены населенные пункты с самой высокой и низкой стоимостью жилья.
6. Проанализированы квартиры с указанием расстояния до центра города. Создан новый столбец с расстоянием до центра в километрах и построен график зависимости цены от удаленности. Определена граница центральной зоны.
7. Изучены квартиры в центре города с анализом площади, цены, числа комнат, высоты потолков, а также факторов, влияющих на стоимость (число комнат, этаж, удаленность от центра, дата размещения). Сравнены выводы для центра города и всего города.

**Шаг 5. Общий вывод**  
Написан общий вывод на основе проведенного анализа и полученных результатов.

---

**Оформление работы:**  
Задание было выполнено в **Jupyter Notebook**, где код был оформлен в ячейках типа **code**, а текстовые пояснения — в ячейках типа **markdown** с применением форматирования и заголовков.

---

**Описание данных:**

- **airports_nearest** — расстояние до ближайшего аэропорта в метрах (м)
- **balcony** — число балконов
- **ceiling_height** — высота потолков (м)
- **cityCenters_nearest** — расстояние до центра города (м)
- **category** — тип населенного пункта (город, село, деревня, поселок)
- **days_exposition** — количество дней, на протяжении которых было размещено объявление (от публикации до снятия)
- **first_day_exposition** — дата публикации объявления
- **floor** — этаж квартиры
- **floors_total** — всего этажей в доме
- **is_apartment** — является ли квартира апартаментами (булев тип)
- **kitchen_area** — площадь кухни в квадратных метрах (м²)
- **last_price** — цена на момент снятия с публикации
- **living_area** — жилая площадь в квадратных метрах (м²)
- **locality_name** — название населённого пункта
- **open_plan** — свободная планировка (булев тип)
- **parks_around3000** — количество парков в радиусе 3 км
- **parks_nearest** — расстояние до ближайшего парка (м)
- **ponds_around3000** — количество водоемов в радиусе 3 км
- **ponds_nearest** — расстояние до ближайшего водоема (м)
- **rooms** — количество комнат
- **studio** — является ли квартира студией (булев тип)
- **total_area** — общая площадь квартиры в квадратных метрах (м²)
- **total_images** — количество фотографий квартиры в объявлении

**Пояснение:**  
Апартаменты — это нежилые помещения, не относящиеся к жилому фонду, но имеющие необходимые условия для проживания.
