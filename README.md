### Проект по анализу данных: предсказание цены колец.
Вашему вниманию предоставляется проект, в котором мы анализируем данные о кольцах с сайта ювелирной компании [SOKOLOV](https://sokolov.ru/). На данный момент мы спарсили данные, сделали их предобработку и начали анализ и визуализацию признаков. В дальнейшем планируем выявить какие-либо закономерности, выдвинуть гипотезы, проверить их, а также построить модель предсказания цены колец (Линейная регрессия). Среди текущих гипотез можно выделить: 1) проверка маркетинговой политики бренда - есть подозрение, что скидки, представленные на сайте, крайне искуственно задаются резким завышением старой цены; 2) вес драгоценных камней в цене кольца максимален; 3) линейные размеры колец слабо влияют на цену; 3) каждая количественная характеристика положительно влияет на цену кольца; 4) число значимых признаков сократится из-за эластичности цены кольца по характеристикам драгоценных камней и металлов.


Предварительное разделение работы по разделам:
1. [Парсинг](parser.ipynb)
2. [Предобработка данных](Предобработка_данных.ipynb)
3. [EDA(Exploratory Data Analysis)](EDA_качественные_характеристики.ipynb)
4. [Таблицы с данными](Data/)
