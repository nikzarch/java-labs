# Assignment №2:  Dictionary in assembly
---
Лабораторная работа №2: словарь на assembler


## Задание

Необходимо реализовать на ассемблере словарь в виде связного списка.
Каждое вхождение содержит адрес следующей пары в словаре, ключ и значение. 
Ключи и значения &mdash; адреса нуль-терминированых строк.

Словарь задаётся статически, каждый новый элемент добавляется в его начало. 
С помощью макросов мы автоматизируем этот процесс так, что указав с помощью новой конструкции языка новый элемент он автоматически добавится в начало списка, и указатель на начало списка обновится. Таким образом нам не нужно будет вручную поддерживать правильность связей в списке. 

Создайте макрос `colon` с двумя аргументами: ключом и меткой, которая будет сопоставлена значению.
Эта метка не может быть сгенерирована из самого значения, так как в строчке могут быть символы, которые не могут встречаться в метках, например, арифметические знаки, знаки пунктуации и т.д. После использования такого макроса можно напрямую указать значение, сопоставляемое ключу. Пример использования:

```nasm
section .data

colon "third word", third_word
db "third word explanation", 0

colon "second word", second_word
db "second word explanation", 0 

colon "first word", first_word
db "first word explanation", 0 
```


В реализации необходимо предоставить следующие файлы:

- `lib.asm` - библиотека ввода-вывода из первого задания
- `lib.inc` - заголовочный файл к библиотеке ввода-вывода
- `colon.inc` - заголовочный файл с определением макроса `colon`
- `dict.asm` - реализация функции `find_word` для поиска в словаре
- `dict.inc` - заголовочный файл для функции поиска в словаре
- `words.inc` - определене словаря, который будет использоваться в тестах
- `main.asm` - реализация простейшего консольного интерфейса для поиска в словаре

