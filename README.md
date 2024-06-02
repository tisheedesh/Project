### Проект по анализу данных: предсказание цены колец.
Вашему вниманию предоставляется проект, в котором мы анализируем данные о кольцах с сайта ювелирной компании [SOKOLOV](https://sokolov.ru/). На данный момент мы спарсили данные, сделали их предобработку и начали анализ и визуализацию признаков. В дальнейшем планируем выявить какие-либо закономерности, выдвинуть гипотезы, проверить их, а также построить модель предсказания цены колец (Линейная регрессия). Среди текущих гипотез можно выделить: 1) проверка маркетинговой политики бренда - есть подозрение, что скидки, представленные на сайте, крайне искуственно задаются резким завышением старой цены; 2) вес драгоценных камней в цене кольца максимален; 3) линейные размеры колец слабо влияют на цену; 3) каждая количественная характеристика положительно влияет на цену кольца; 4) число значимых признаков сократится из-за эластичности цены кольца по характеристикам драгоценных камней и металлов.


Предварительное разделение работы по разделам:
1. [Парсинг](parser.ipynb)
2. [Предобработка данных](Предобработка_данных.ipynb)
3. [EDA(Exploratory Data Analysis)](EDA.ipynb)
4. [Таблицы с данными](Data/)

# Парсинг
С сайта [SOKOLOV](https://sokolov.ru/) нам удалось спарсить даные по почти 10К кольцам с различными характеристиками. Без проблем, конечно, не обошлось - парсинг занял долгое время и в какой-то момент упал, но нам удалось восстановить процесс и спарсить остаток данных. По итогу мы получили таблицу с почти 10К объектов и уже были готовы предобрабатывать данные:

# Предобработка данных
В файле [Предобработка данных](Предобработка_данных.ipynb) мы описали весь процесс, тут опишем всё кратко. Описание признаков выглядит вот так:
Артикул - артикул кольца на сайте.
Бренд - бренд кольца (здесь - у всех SOKOLOV).
Для кого - для кого предназначено кольцо (пол, возраст).
Примерный вес - вес кольца в граммах.
Тип металла - из какого металла сделано кольцо.
Проба - процент содержания драгоценного камня в сплаве (где 1000 - 100%).
Покрытие - специальная обработка для увеличения срока годности изделия и изменения внешнего вида путем покрытия металла другим металлом.
Номер страницы - так как кольца были отсортированы по полулярности, мы подумали, что можно как-то связать номер страницы (может выступать измерителем популярности кольца) с чем-либо еще. Данную гипотезу проверим позже.
Ширина кольца - ширина самого кольца без вставки.
Ширина - ширина кольца с учетом вставки.
Высота - высотка вставки.
Длина - длина вставки.
Коллекция - в основном какие-то коллаборации (например, SOKOLOV x LOLITA).
Цена со скидкой, Цена без скидки - целевые переменные (будет выбрана только одна для предсказания)
Форма вставки - какой формы вставка драгоценного(-ых) камня(-ей).
Количество - количество камней в данной вставке.
Цвет - цвет камня.
Вес - вес всех камней во вставке (в каратах, 1 карат = 0.2 г)
Цветность - порядковая характеристика: чем меньше число, тем прозрачнее и ценнее камень.
Чистота - порядковая характеристика: чем меньше число, тем лувчше и ценнее камень
Огранка - порядковая характеристика механической обработки камня: А - очень хорошая, Б - хорошая, В - средняя, Г - плохая.
Размеры вставки - ширина вставки.

Нехитрыми манипуляциями преобразовали типы данных в датасете и в целом подготовили его к дальнейшей работе.

# Модели
В файле мы попробовали построить регрессию разными способами и предсказывать цену кольца в зависимости от его характеристик. Вышло плохо, ошибка около 25К рублей. Попробовали также обучить классификатор на разделение колец по популярности, но там результаты совсем смешные получились.

# Выводы:
Данные, которые мы получили, достаточно тяжело анализировать - на самом сайте "формат" данных имеет некоторые отличия от кольца к кольцу, порой встречаются ошибки в данных, а порой и вовсе не содержит значений и данные пропущены. Также было тяжело работать с кольцами, в которых есть несколько разных камней - мы так и не придумали, как с ними работать, поэтому выкинули их. 



