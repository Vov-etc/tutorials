<meta charset="utf-8">
#Предисловие
**Vim** - очень мощный редактор, даже без использования плагинов. 
Я смогу рассказать далеко не всё, иначе никто не дочитает это до конца.
***
##.vimrc
*Мооожно*, конечно, совсем не настраивать **vim**, но я не советую
таким заниматься.
###Что делает .vimrc
Это просто набор команд, которые выполняются при каждом запуске **Vim**<br>
Их можно исполнять и в процессе редактирования, так: 

**`: command`**
###Что можно делать
*    Опции, которые можно включать-выключать<br>
    Эти опции пишем после ключевого слова `set`
    +     `tabstop=N` - делает ширину отступа
                    (который появляется при нажатии `tab`), равным N
                    
    +   `shiftwidth=N` - делает величину сдвига (о них я позже расскажу)
                       равной N
                       
    +   `expandtab` - заменяет табы пробелами (Если таб уже где-нибудь стоит, его не трогает)
    
    +   `nu` - от слова *number* - показывает номера строк
    
    +   `autoindent`, `smartindent` - 
                две разных схемы расстановки отступов при переносах строк.
                Попробуйте обе, выберите, какая больше нравится
    +   `smarttab` - убирает весь отступ при нажатии backspace, если вы стираете отступ
    
    +   `hlsearch` - подсвечивает все вхождения того, что вы ищете
    
    +   `colorcolumn=N` - Рисует красный фон у каждого символа, который N-тый по счёту в своей строке
        Используется, как ограничитель (писать строчку дальше - некрасиво, перейди на другую)
    +   `wrap` - Включает автоматические переносы (интересная штука)
    
    +   `wrapmargin=N` - делает перенос (тот, про который предыдущая команда)
            Если до конца строки осталось меньше N символов. Стоит попробовать, чтобы понять
    +   `textwidth=N`  - делает перенос, если строка длиннее N символов.
    +   `laststatus=2` - включает вам строку состояния
    
    +   `statusline=String` - настраивает строку состояния из пред. команды
        Наберите **`:help statusline`**, чтобы прочитать про это больше.
        <br>Для неё можно поставить некоторые плагины, например, powerline.
*    сочетания клавиш
    
    В **vim** можно поставить на любое сочетание клавиш что угодно
    
    Любую команду или последовательность команд, которую можно выполнить в **vim**
    
    Для этого надо писать так:<br>
    *`[niv]map сочетание команда`*<br> ([abc] - a, b или с, я часто буду так писать)
    Записывая сочетания, всё, кроме пробела, пишем как есть
    
    Эта первая буква показывает, в каком режиме вы хотите использовать сочетание
    
    +     `n - Normal`
    +    `i - Insert`
    +    `v - Visual`
    
    Пробел, Ctrl, Shift, Tab, F1-F12 = `<Space>, <C>, <S>, <Tab>, <F1> .. <F12>`
    
    Много модификаторов пишем в одних `<>`
    
    Например, 
    `<C-S-F6>` 

* * *

##Редактор
###movement
*    **General**
    +    `hjkl` - двигаетесь влево, вниз, вверх, вправо соотв.
    
    +    `web` - двигаетесь в начало следующего слова, в конец следующего, в начало предыдущего соотв.
        
         Cлова - последовательности букв, цифр и _
    
    +    `WEB` - То же, только для больших слов.
            Большие слова разделены пробелами и переносами строк, остальное - часть большого слова

*     **scrolling**

    *    `gg, [[` - начало файла
    
    *    `G, ]]` - конец файла
    
    *    `HML` - перемещает курсор в верх, в центр и в низ экрана соотв.
    
    *    `Ctrl-b, Ctrl-u` = Page Up, Page Down

*    **in line**
    *    `f<symbol>` -- Находит следующее после курсора вхождение символа в строке, где курсор
    
    *    `F<symbol>` -- Находит предыдущее ...
    
    *    `;`     -- Повторяет последнее действие такого поиска, ищет в ту же сторону.
    
    *    `,`     -- Ищет в другую сторону.
    
    *    `0`     -- Начало строки
    
    *    `$`     -- Конец строки
    
    *    `^`     -- Первый непробельный символ
    
*    **useful**
    *    `%`    -- Переходит к парной скобке
    
    *    `[(' -- Переходит к открывающей скобке из той пары, внутри которой вы находитесь.
    *    `[)` -- К закрывающей
                
        Аналогично, `[{`

    *    `{` -- Предыдущая пустая строка. Если вы действительно расставляете пустые строки
        чтобы показать логику работы, это полезно.
    *    `}` -- Cледующая пустая строка.
    
    *    `<N>G` -- переходит на строку №<N>

    *   `gi` -- Идёт туда, где вы вышли из Insert mode и переходит в него

    *   `gd` -- Идёт к объявлению переменной

Эти все сочетания работают как в Normal mode, так и в Visual, и это удобно

* * *

##Важно!
`<N><movement>` - Повторить movement N раз
`<N><command>` - повторить команду N раз

* * *

### Editing
*    from Normal mode to Insert
    *    `i` -- Просто перейти
    *    `a` -- Сдвинуться вправо на один символ и перейти (Полезно, т.к. Escape сдвигает влево)
    *    `I` -- Пойти в начало строки и перейти
    *    `A` -- Пойти в конец строки и перейти
    *    `o` -- Вставить пустую строку после текущей, пойти туда и перейти (отступы работают)
    *    `O` -- Вставить ... ДО текущей ...
    *    `сс` -- очистить эту строку (останется пустая строка) и перейти
    *    `С` -- удалить всё до конца строки и перейти
    *    `с<movement>` -- удалить отрезок с концами (где был курсор, где сейчас курсор)
        и перейти
    *    `s` -- удалить символ и перейти
    *    `S` -- То же, что и cc
*    other
    *    `dd` -- Удалить текущую строку
    *    `d<movement>` -- удалить отрезок...
    *    `D` --  Удалить до конца строки
    *   `>>` -- Добавить слева shiftwidth пробелов
    *    `<<` -- Убрать слева max(shiftwidth, сколько есть) пробелов
    *    `yy` -- Скопировать текущую строку
    *    `y<movement>` -- скопировать отрезок...
    *    `p`  -- Вставить после курсора, если скопирована строка, вставит следующей строкой
    *    `P`  -- Вставить ДО курсора, если строка в буфере, то вставит до текущей
    *    `u`  -- Ctrl-Z
    *    `Ctrl-r` -- Ctrl-y
    *    `U`  -- Отменит все изменения, которые вы делали в этой строке недавно
    *    `x`  -- удалить символ
    *    `r`  -- заменить символ
    *    `diw` -- Удалить слово под кусором

* * *
##Время примеров!
`d3w` -- удалит 3 слова, считая от курсора
`3d3w` -- 3 раза удалит 3 слова

* * *

###Visual mode
*   `v` -- Выделяет подстроку
*   `V` -- Выделяет непрерывное множество строк
*   `Ctrl-V` -- Выделяет столбиком

Выделить что-нибудь быстро:

*   `viB` -- Выделяет блок {}
*   `viw` -- Выделяет текущее слово

Вы что-то выделили, можно делать следующее

*   `d` -- Удалить
*   `y` -- Копировать
*   `<`, `>` -- сдвигать
*   `J` -- Объединять в одну строку
*   `gq` -- Разбивать строки на много (попробуйте написать строку, не влезающую в одну строку)
*   `zf` -- (zip fold) - Cворачивает выделенный кусок. (Неважно, как вы выделяли, он свернёт строки)
*   `:<command>` -- Выполнит команду на выделенном куске. (Он напишет некие символы, не обращайте на них внимания)
*   :sort -- лексикографически отсортирует строки
*   :!<любая внешняя команда> -- передаст этой команде на ввод строки, вывод запишет вместо этих строк
    F.e.  :!tac -- развернёт

####Что можно делать с zip-ами
*   `zf` -- Свернуть
*   `za` -- Изменить состояние (если вы сворачивали какой-то кусок в этом сеансе редактирования, **Vim** запомнит
    Это и вы можете много раз сворачивать-разворачивать куски кода
*   `zo` -- Развернуть
*   `zc` -- Свернуть

###Insert mode
Обычно в Insert mode вы только пишете, но и здесь есть несколько shortcut-ов, упрощающих работу

*   `Ctrl-D` -- Удаляет один отступ с начала строки

*   `Ctrl-T` -- Добавляет отступ в начало строки

*   `Ctrl-I` = Tab           

*   `Ctrl-E` -- Пишет символ, который под курсором.

*   `Ctrl-Y` -- Пишет символ, который над курсором.

*   `Ctrl-W` -- Стирает до начала слова. (Если курсор в конце слова, стирает слово)

*   `Ctrl-U` -- Стирает до начала строки

*   `Ctrl-O` -- Одна команда как в Normal mode

*   `Ctrl-P` -- Подставляет предыдущее слово, начинающееся также

*   `Ctrl-N` -- Следующее слово, начинающееся также

##Поиск
Чтобы искать что-нибудь по всему файлу, пишите

В Normal mode, конечно

+   `/find` -- ищет подстроку find
+   `#` -- Переходит к предыдущему вхождению слова под курсором
+   `*` -- Переходит к следующему ...

##Замена

Большая тема, очень важная

Варианты:

*   `:s/find/replace/flags` -- заменит в текущей строке
*   `<Выделить строки>:s/find/replace/flags` -- заменит в выделении
*   `:%s/find/replace/flags` -- заменит во всём файле

###flags
*   `g` -- Не только первые вхождения
*   `c` -- Будет некий диалог подтверждения, полезно, если надо менять не все

###find
**Vim** Поддерживает регулярные выражения (строки, которым подходят сразу несколько)

####_Некоторые возможности_
*   `.` -- Один любой символ
*   `^` -- Начало строки
*   `$` -- Конец строки
*   `\w` -- буква
*   `\W` -- не-буква
*   `\s` -- пробельный символ (Таб или пробел)
*   `\S` -- непробельный символ
*   [ad-k] -- Один символ из множества {a, d, e, f, g, i, j, k}
    (можно писать знак `-` между символами, тогда в мн-во включаются все символы между ними)
*   [^ad-k] -- Один символ НЕ из множества {a, d, e, f, g, i, j, k}
    (`^` в начале множества - отрицание)
*   `*` -- любое количество того, что перед ней
    *   `.*` -- Любая строка
    *   `a*` -- Строка, состоящая из любого количества букв `a`, возможно, 0
    *   `[a-f]*` -- Строка, состоящая только из букв {a, b, c, d, e, f} (С повторениями, возможно не из всех)
*   \( \) -- Запоминает то, что внутри, и это можно использовать в замене<br>
    То, что было внутри первой пары \( \), можно получить как \1<br>
    Внутри второй - \2<br>
    ...

###Примеры
####Было
`abcdef`
####Применили
`$:s/\([a-d]*\)/\1x\1/`
####Стало
`abcdxabcdef`

*Это лишь малая часть, остальное написано в `man perlre`*