### Как сделать подпись с названием сектора и процентом в круговой диаграмме? {#pie-chart-note}

Создайте подпись с помощью вычисляемого поля:

`[<name>] + ' ' + str(int([<value>]/sum([<value>] TOTAL)*100)) + '%'`

Где:

- `<name>` — поле, по которому будет определяться название сектора;

- `<value>` — поле, значение которого должно отображаться в виде процента.

**Как устроена формула?**

1. Фрагмент `([<value>]/sum([<value>] TOTAL)*100` вычисляет долю сектора в виде процента.

1. Вычисленное значение округляется функцией [INT](../../../datalens/function-ref/INT.md).

1. Значение переводится в строку функцией [STR](../../../datalens/function-ref/STR.md) для создания подписей к диаграмме.

1. Название сектора, вычисленное значение и символ `%` объединяются строку оператором сложения `+`.

**Пример**

Формула: `[Category] + ' ' + str(int([Sales]/sum([Sales] TOTAL)*100)) + '%'`

См. [изображение](https://storage.yandexcloud.net/doc-files/pie-chart.png).