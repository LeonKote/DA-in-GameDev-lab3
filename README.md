# АНАЛИЗ ДАННЫХ И ИСКУССТВЕННЫЙ ИНТЕЛЛЕКТ [in GameDev]
Отчет по лабораторной работе #3 выполнил(а):
- Папушев Роман Олегович
- РИ220947
Отметка о выполнении заданий (заполняется студентом):

| Задание | Выполнение | Баллы |
| ------ | ------ | ------ |
| Задание 1 | * | 60 |
| Задание 2 | * | 20 |
| Задание 3 | * | 20 |

знак "*" - задание выполнено; знак "#" - задание не выполнено;

Работу проверили:
- к.т.н., доцент Денисов Д.В.
- к.э.н., доцент Панов М.А.
- ст. преп., Фадеев В.О.

[![N|Solid](https://cldup.com/dTxpPi9lDf.thumb.png)](https://nodesource.com/products/nsolid)

[![Build Status](https://travis-ci.org/joemccann/dillinger.svg?branch=master)](https://travis-ci.org/joemccann/dillinger)

Структура отчета

- Данные о работе: название работы, фио, группа, выполненные задания.
- Цель работы.
- Задание 1.
- Код реализации выполнения задания. Визуализация результатов выполнения (если применимо).
- Задание 2.
- Код реализации выполнения задания. Визуализация результатов выполнения (если применимо).
- Задание 3.
- Код реализации выполнения задания. Визуализация результатов выполнения (если применимо).
- Выводы.
- ✨Magic ✨

## Цель работы
Разработать оптимальный баланс для десяти уровней игры Dragon Picker

## Задание 1
### Предложите вариант изменения найденных переменных для 10 уровней в игре. Визуализируйте изменение уровня сложности в таблице.

- Вариантом для изменения найденных переменных может быть их постепенное изменение на фиксированную величину. На движение дракона влияют переменные speed и leftRightDistance. На сбрасывание драконьих яиц влияют переменные timeBetweenEggDrops и chanceDirection. Основную роль в увеличении сложности играют переменные speed и timeBetweenEggDrops, чем выше значение переменной speed и меньше timeBetweenEggDrops, тем сложнее уровень.

- см. [таблицу](https://docs.google.com/spreadsheets/d/1ZdIA1MukD1KfCAd3r8EFCgiwco8qRzInJURjn5TL3ns/edit?usp=sharing).

## Задание 2
### Создайте 10 сцен на Unity с изменяющимся уровнем сложности.

- см. [каталог](https://github.com/LeonKote/DA-in-GameDev-lab3/tree/master/DragonPickerDefault) с проектом.
- см. [каталог](https://github.com/LeonKote/DA-in-GameDev-lab3/tree/master/DragonPickerDefault/Assets/_Scenes/_GameScenes) со сценами.

## Задание 3
### Решение в 80+ баллов должно заполнять google-таблицу данными из Python. В Python данные также должны быть визуализированы.

- см. [скрипт](https://github.com/LeonKote/DA-in-GameDev-lab3/blob/master/Anaconda/UnityDataScience.ipynb).
- см. [таблицу](https://docs.google.com/spreadsheets/d/1RXAWNEkP9pPxV4YLN0hyPUQ5I4HAYhYGgecIGiF5YKs/edit?usp=sharing).

```py

import gspread
gc = gspread.service_account(filename='unitydatascience-400416-98e6ba2ba08f.json')
sh = gc.open("UnityWorkshop3-2")
speed = 4
timeBetweenEggDrops = 2
leftRightDistance = 10
chanceDirection = 0.01
for i in range(1, 11):
    sh.sheet1.update(('A' + str(i)), str(i))
    sh.sheet1.update(('B' + str(i)), str(speed))
    sh.sheet1.update(('C' + str(i)), str(round(timeBetweenEggDrops, 1)))
    sh.sheet1.update(('D' + str(i)), str(leftRightDistance))
    sh.sheet1.update(('E' + str(i)), str(round(chanceDirection, 2)))
    speed += 1
    timeBetweenEggDrops -= 0.1
    leftRightDistance += 1
    chanceDirection += 0.01
    print(i)

```

## Выводы

В процессе работы я научился разработать оптимальный баланс для уровней игры. Я узнал, как находить и изменять переменные, которые влияют на сложность уровня, визуализировать изменения, как создавать сцены на Unity с изменяющимся уровнем сложности, а также как заполнять google-таблицу соответствующими данными из Python и визуализировать их.

| Plugin | README |
| ------ | ------ |
| Dropbox | [plugins/dropbox/README.md][PlDb] |
| GitHub | [plugins/github/README.md][PlGh] |
| Google Drive | [plugins/googledrive/README.md][PlGd] |
| OneDrive | [plugins/onedrive/README.md][PlOd] |
| Medium | [plugins/medium/README.md][PlMe] |
| Google Analytics | [plugins/googleanalytics/README.md][PlGa] |

## Powered by

**BigDigital Team: Denisov | Fadeev | Panov**
