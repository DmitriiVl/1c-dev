# Ответы на задание homework-2 

### Задание

1. Создайте пустую информационную базу, выполните базовые настройки

2. Создайте документы, справочники и реквизиты

3. Настройте интерфейс по умолчанию, задайте цветовую схему

## Процесс выполнения

### Создание и настройка базы

1. Создайте новую информационную базу и откройте ее в режиме Конфигуратор.

2. Установите свойства корня конфигурации:
    - Имя: ЛичныеФинансы
    - Синоним: Личные финансы
    - Авторские права: Ваша фамилия и имя
    - Версия: 0.0.0.1

### Создание справочников, документов и реквизитов

1. Создайте в группе Общие новый Определяемый тип **ДенежнаяСумма**, с типом Число (15, 2)

2. Создайте перечисление **ВидыЛичныхСчетов** со значениями Наличные, Банк

3. Создайте справочник **Валюты** с предопределенным элементом Рубль

4. Создайте справочник **ЛичныеСчета** с длиной наименования 150 и реквизитами:
    - ВидСчета - ПеречислениеСсылка.ВидыЛичныхСчетов
    - Валюта - СправочникСсылка.Валюты

5. Создайте справочник **СтатьиДвиженийДенежныхСредств** с длиной наименования 150 и включенной иерархией элементов. Создайте предопределенные элементы на верхнем уровне иерархии на свое усмотрение.

6. Создайте справочник **Номенклатура** с длиной наименования 150 и включенной иерархией групп и элементов.

7. Создайте документ **ПолучениеДохода** с реквизитами:
    - Счет - СправочникСсылка.ЛичныеСчета
    - СтатьяДохода - СправочникСсылка.СтатьиДвиженияДенежныхСредств
    - Сумма - ОпределяемыйТип.ДенежнаяСумма
    - Комментарий - Строка неограниченной длины

8. Создайте документ **ПереводМеждуСчетами** с реквизитами:
    - СчетСписания - СправочникСсылка.ЛичныеСчета
    - СчетЗачисления - СправочникСсылка.ЛичныеСчета
    - Сумма - ОпределяемыйТип.ДенежнаяСумма
    - Комментарий - Строка неограниченной длины

9. Создайте документ **Покупка** с реквизитами:
    - Счет - СправочникСсылка.ЛичныеСчета
    - СтатьяРасхода - СправочникСсылка.СтатьиДвиженияДенежныхСредств
    - РазделитьПоТоварам - Булево
    - Сумма - ОпределяемыйТип.ДенежнаяСумма
    - Комментарий - Строка неограниченной длины
    - Табличной частью ТоварыУслуги с колонками:
        - Номенклатура - СправочникСсылка.Номенклатура
        - Количество - Число (10, 0)
        - Цена - ОпределяемыйТип.ДенежнаяСумма
        - Сумма - ОпределяемыйТип.ДенежнаяСумма

### Настройка интерфейса

1. В группе Общие создайте подсистемы:
    - Финансы, с составом:
        - Документ ПолучениеДохода
        - Документ ПереводМеждуСчетами
        - Документ Покупка
    - Настройки, с составом:
        - Справочник Валюты
        - Справочник ЛичныеСчета
        - Справочник СтатьиДвиженийДенежныхСредств
        - Справочник Номенклатура

2. В корне конфигурации откройте свойство Интерфейс клиентского приложения, разместите панели так, как на ваш взгляд оптимальнее для работы с приложением. Можно запустить приложение, посмотреть получившийся результат и перенастроить.

3. В группе Общие создайте новый стиль, настройте для стиля цветовое оформление приложения на свой вкус. В корне конфигурации установите новый стиль в свойстве Основной стиль.  

### Решение  

Все задания выполнены, справочники и документы заведены:  

![CONFIG](assets/conf.jpg)  

Стиль интерфейса изменен и выглядит следующим образом:  

![IFACE](assets/newIface.jpg)  

Конфигурация и база данных выгружены и доступны по [ссылке](assets/) 



