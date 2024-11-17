# Практическое занятие №5.Вопросы виртуализации
## Задача 1. Исследование виртуальной стековой машины CPython. Изучите возможности просмотра байткода ВМ CPython.
```
11 0 LOAD_FAST 0 (x)
```
Эта команда загружает значение локальной переменной x в стек.
Эквивалентное выражение на Python: x
```
2 LOAD_CONST 1 (10)
```
Здесь загружается константа 10 в стек.
Эквивалентное выражение на Python: 10
```
4 BINARY_MULTIPLY
```
Умножает два значения на верхушке стека (значение из x и 10), результат будет помещен на верх стека.
Эквивалентное выражение на Python: x * 10
```
6 LOAD_CONST 2 (42)
```
Загружает константу 42 в стек.
Эквивалентное выражение на Python: 42
```
8 BINARY_ADD
```
Складывает два значения на верхушке стека (результат умножения x * 10 и 42) и помещает результат в стек.
Эквивалентное выражение на Python: x * 10 + 42
```
10 RETURN_VALUE
```
Эта команда возвращает значение, находящееся на верхушке стека, в качестве результата выполнения функции.
Эквивалентное выражение на Python: return (x * 10 + 42)