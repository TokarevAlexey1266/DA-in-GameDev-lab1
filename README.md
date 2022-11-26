# АНАЛИЗ ДАННЫХ И ИСКУССТВЕННЫЙ ИНТЕЛЛЕКТ [in GameDev]
Отчет по лабораторной работе #4 выполнил(а):
- Токарев Алексей Владиславович
- РИ210942
Отметка о выполнении заданий (заполняется студентом):

| Задание | Выполнение | Баллы |
| ------ | ------ | ------ |
| Задание 1 | * | 60 |
| Задание 2 | # | 20 |
| Задание 3 | # | 20 |

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
Ознакомиться с основами перцептрона.

## Задание 1
### в проекте юнити реализовать перцептрон, который умеет производить вычисления: OR, AND, NAND, XOR.
Ход работы:
Разбираем логику  OR, AND, NAND, XOR:
![image](https://user-images.githubusercontent.com/106770342/204089428-e51dd43f-a95c-4ca8-ab8a-7005de2d063c.png)



Создаем 3D Unity проект:
![image](https://user-images.githubusercontent.com/106770342/204089492-bc0647ae-c6ee-47d0-bb22-52a4da45bbeb.png)



Создем пустой объект и присоединяем к нему перцептрон-файл:
![image](https://user-images.githubusercontent.com/106770342/204089708-756fcf89-8731-49c8-8b6d-b6395b635720.png)
![image](https://user-images.githubusercontent.com/106770342/204089724-f3b4f658-7aab-4e5e-9103-f9cb69d3c471.png)



Вводим данные логики OR в ts:
![image](https://user-images.githubusercontent.com/106770342/204089998-59d2b913-94e7-4b69-906d-2e682e6e2631.png)


Запусукаем и видим, что при 1 и 3 попытках была 1 ошибка, при 2 попытке было 2 ошибки, а после ошибок не было, то есть перцептрон "научился" производить вычисления OR, это мы видим в консоле в последних 4 строчках теста:
![image](https://user-images.githubusercontent.com/106770342/204090044-52629114-7b4b-4eab-a0af-7725a97b8a59.png)
![image](https://user-images.githubusercontent.com/106770342/204090055-87fb630e-1df9-4c4c-85f4-a7528c3c14ff.png)




Вводим данные логики AND в ts:
![image](https://user-images.githubusercontent.com/106770342/204090744-381a069d-3cf1-404e-8c9d-0bb71bb2a31c.png)


Запусукаем и видим, что ошибки были, но после 7ой попытки ошибок не было, то есть перцептрон "научился" производить вычисления AND, это мы видим в консоле в последних 4 строчках теста:
![image](https://user-images.githubusercontent.com/106770342/204090888-6961ef9e-fcbf-42a8-9294-0033236e1319.png)
![image](https://user-images.githubusercontent.com/106770342/204090901-040a7e25-0b42-4f9f-92de-11786eff67ea.png)





Вводим данные логики NAND в ts:
![image](https://user-images.githubusercontent.com/106770342/204091487-8e1484f5-7752-473e-899a-449776efd263.png)

Запусукаем и видим, что ошибки были, но после 7ой попытки ошибок не было, то есть перцептрон "научился" производить вычисления NAND, это мы видим в консоле в последних 4 строчках теста:
![image](https://user-images.githubusercontent.com/106770342/204091592-989ebd95-a3e7-462d-a725-2ac07e7bcf23.png)
![image](https://user-images.githubusercontent.com/106770342/204091597-47298e38-9bf7-4acb-9a03-a3ac8b3da347.png)






Вводим данные логики XOR в ts:
![image](https://user-images.githubusercontent.com/106770342/204091727-d799c4ee-8df4-4f76-8fd7-e1a6643e3698.png)

Запусукаем и видим, что при попытке произвести вычисления XOR количество ошибок варьруется от 2 до 4, но с увеличением количества попыток, ошибки не уходят. И соответсвенно тесты решаются не правильн:
![image](https://user-images.githubusercontent.com/106770342/204092203-b9d671d9-08ff-4b92-abd8-f481e2efd466.png)



## Задание 2
### Пошагово выполнить каждый пункт раздела "ход работы" с описанием и примерами реализации задач






## Задание 3
### Должна ли величина loss стремиться к нулю при изменении исходных данных? Ответьте на вопрос, приведите пример выполнения кода, который подтверждает ваш ответ.





## Выводы

Абзац умных слов о том, что было сделано и что было узнано.

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
