### Примечание
Для задач может потребоваться выводить что-нибудь в одну строку (сначала одно число, а потом на той же строке другое)

Это делается с помощью `print(a, end='')`. Тут написано - выведи a, а после него ничего не выводи. (то есть, выведи пустую строку). Можно писать не `''`, а `' '`, или `'; `. По умолчанию там тот самый перенос строки, который записывается как `\n`. `end` - то, что выведется после последнего аргумента (ведь в `print` их можно много передавать).

## Простые задачи
### 1
Вывести `n`-е число Фиббоначи. F<sub>0</sub> = 0, F<sub>1</sub> = 1

|   Ввод    |    Вывод    |
|:---------:|:-----------:|
|    6      |     8       |

### 2
Вывести первые `n` чисел Ф.

|   Ввод  |   Вывод       |
|:--------|:--------------|
|    6    | 0 1 1 2 3 5   |

### 3
Перевести число из двоичной системы в десятичную

|   Ввод   |   Вывод       |
|:---------|:--------------|
| 10110011 | 179           |

## Средней сложности задачи

### 1

Раскрасить доску в шахматном порядке. Верхняя левая клетка - чёрная.
<table>
<tr>
<td>
Ввод</td>
<td> Вывод </td>
</tr>
<tr>
<td>
3<br>3</td>
<td>#*#<br>*#*<br>#*#</td>
</tr>
</table>

### 2

Дано `n` и затем `n` чисел. Найти максимум

| Ввод | Вывод      |
|:-----|:----------:|
| 3 <br>1<br>4<br>2   | 4          |

## 3

Вводятся 4 числа: a, b, c и d.

Найдите все целые решения уравнения ax<sup>3</sup> + bx<sup>2</sup> + cx + d = 0 на отрезке [-1000,1000] и выведите их в порядке *убывания*. Если на данном отрезке нет ни одного решения, то ничего выводить не нужно.

| Ввод    |   Вывод    |
|:--------|-----------:|
|0<br>1<br>0<br>-1| 1 -1|

## Сложные задачи

### 1

Заполнить табличку "Змейкой".
Вводятся ширина и высота

| Ввод   | Вывод      |
|:-------|-----------:|
| 4<br>3 | 1  2  3  4<br>  8  7  6  5 <br> 9 10 11 12|
| 5 <br>1| 1 2 3 4 5  |

## 2
Найти наибольший делитель числа, отличный от него самого

| Ввод | Вывод |
|-----:|------:|
| 60   |  30   |