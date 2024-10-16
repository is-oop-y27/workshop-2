# Воркшоп 2

## Отрабатываемые материалы

SOLID, Порождающие паттерны

## Формулировка

Реализовать систему формирования и вывода статей.

## Функциональные требования

- Статья должна иметь название, параграфы, может иметь автора
- Параграф должен иметь заголовок, абзацы, может иметь заключение (футер)
- Параграфы могут иметь разное форматирование
- Необходимо иметь функционал редактирования статей (добавить параграфы, поменять название, автора)
- Необходимо иметь возможность вывода статей на консоль

## SOLID

SRP – сущности имеют свои ответсвенности: текст - формирование форматированной строки для вывода, параграф, статья –
композиция текстов.

OCP – Поддержать возможность добавления новых видов параграфов без изменения уже имеющихся классов (путем добавления
нового билдера под новый вид)

LSP – реализации текста не должны нарушать инвариант контракта, описываемого интерфейсом

ISP – интерфейсы должны описывать один функционал

DIP – в реализованной модели не должно быть лишних завязок на конкретные типы

## Сущности

### Параграф

Атрибуты:

- заголовок
- абзац текста (может быть несколько)
- заключение (футер)

Так как параграфы могут иметь разное форматирование, определение этого форматирование вынесем в билдеры. Соответсвенно,
для них будем делать абстрактные фабрики.

> Полиморфный билдер, абстрактная фабрика, фабричный метод

### Статья

Атрибуты:

- название
- параграфы
- автор (опционально)

Для статьи будем делать билдер.

Также, статья должна являться директором для своего билдера

> Билдер, директор

### Текст

Любое выводимое значение. Над текстом могут быть модификаторы. У текста может изменяться контент. Можно склонировать
текст, сохраняя форматирование, в дальнейшем изменив контент. Модификторы накладываются эксеншенами, возвращающими
конкретный тип.

> Прототип, будет дженерековым, для возможности изменений данных конкретных типов

# Links

[https://github.com/riezebosch/Crayon](https://github.com/riezebosch/Crayon)