# АНАЛИЗ ДАННЫХ И ИСКУССТВЕННЫЙ ИНТЕЛЛЕКТ [in GameDev]
Отчет по лабораторной работе #1 выполнил(а):
- Токарев Алексей Владиславович
- РИ210942
Отметка о выполнении заданий (заполняется студентом):

| Задание | Выполнение | Баллы |
| ------ | ------ | ------ |
| Задание 1 | * | 60 |
| Задание 2 | * | 20 |
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
Ознакомиться с основными операторами зыка Python на примере реализации линейной регрессии.

## Задание 1
### Написать программы Hello World на Python и Unity.
Ход работы:
Вывод в консоль любой строчки в Python осуществляется с помощью функции print().
Так выглядит вывод в Google Colab:
![image](https://user-images.githubusercontent.com/106770342/192844425-e0460388-5669-4fb8-a770-d325c2bf1790.png)

скрипт вывода текста в Unity:
![image](https://user-images.githubusercontent.com/106770342/192846131-cd26bb79-be56-4628-96e9-50f87b284cfb.png)
Вывод в консоль "Hello World" в Unity:
![image](https://user-images.githubusercontent.com/106770342/192846214-f363c787-c499-4b1a-a821-dcacef55eb95.png)


## Задание 2
### Пошагово выполнить каждый пункт раздела "ход работы" с описанием и примерами реализации задач
- Произвести подготовку данных для работы с алгоритмом линейной регрессии. 10 видов данных были установлены случайным образом, и данные находились в линейной зависимости. Данные преобразуются в формат массива, чтобы их можно было вычислить напрямую при использовании умножения и сложения.

```py

In [ ]:
#Import the required modules, numpy for calculation, and Matplotlib for drawing
import numpy as np
import matplotlib.pyplot as plt
#This code is for jupyter Notebook only
%matplotlib inline

# define data, and change list to array
x = [3,21,22,34,54,34,55,67,89,99]
x = np.array(x)
y = [2,22,24,65,79,82,55,130,150,199]
y = np.array(y)

#Show the effect of a scatter plot
plt.scatter(x,y)


```
Подготовка и первичная визуализация данных:
![image](https://user-images.githubusercontent.com/106770342/192848206-7ca799b2-1268-481e-9ca6-e130a81331a8.png)


- Определите связанные функции. Функция модели: определяет модель линейной регрессии wx+b. Функция потерь: функция потерь среднеквадратичной ошибки. Функция оптимизации: метод градиентного спуска для нахождения частных производных w и b.

```py

In [ ]:
#The basic linear regression model is wx+ b, and since this is a two-dimensional space, the model is ax+ b

def model(a, b, x):
    return a*x + b

#Tahe most commonly used loss function of linear regression model is the loss function of mean variance difference
def loss_function(a, b, x, y):
    num = len(x)
    prediction=model(a,b,x)
    return (0.5/num) * (np.square(prediction-y)).sum()

#The optimization function mainly USES partial derivatives to update two parameters a and b
def optimize(a,b,x,y):
    num = len(x)
    prediction = model(a,b,x)
    #Update the values of A and B by finding the partial derivatives of the loss function on a and b
    da = (1.0/num) * ((prediction -y)*x).sum()
    db = (1.0/num) * ((prediction -y).sum())
    a = a - Lr*da
    b = b - Lr*db
    return a, b

#iterated function, return a and b
def iterate(a,b,x,y,times):
    for i in range(times):
        a,b = optimize(a,b,x,y)
    return a,b

```

loss_function и model связанные функции, optimize и model тоже, optimize и iterate также
```py

In [ ]:
a = np.random.rand(1)
print(a)
b = np.random.rand(1)
print(b)
Lr = 0.000001

#For the first iteration, the parameter values, losses, and visualization after the iteration are displayed
a,b = iterate(a,b,x,y,1)
prediction=model(a,b,x)
loss = loss_function(a, b, x, y)
print(a,b,loss)
plt.scatter(x,y)
plt.plot(x,prediction)
```

Итерация 1:

```py

In [ ]:
a,b = iterate(a,b,x,y,1)
prediction=model(a,b,x)
loss = loss_function(a, b, x, y)
print(a,b,loss)
plt.scatter(x,y)
plt.plot(x,prediction)
```
Итерация 2:
![image](https://user-images.githubusercontent.com/106770342/192851649-15af6d7c-e874-49b9-a812-4151170087cf.png)


```py

In [ ]:
a,b = iterate(a,b,x,y,2)
prediction=model(a,b,x)
loss = loss_function(a, b, x, y)
print(a,b,loss)
plt.scatter(x,y)
plt.plot(x,prediction)
```
Итерация 3:
![image](https://user-images.githubusercontent.com/106770342/192852031-86970884-f02d-44e6-af2e-7832dde00c66.png)

```py
In [ ]:
a,b = iterate(a,b,x,y,3)
prediction=model(a,b,x)
loss = loss_function(a, b, x, y)
print(a,b,loss)
plt.scatter(x,y)
plt.plot(x,prediction)
```
Итерация 4:

![image](https://user-images.githubusercontent.com/106770342/192854673-af127e3e-2da4-491e-83b0-fe3e49b965cd.png)


```py
In [ ]:
a,b = iterate(a,b,x,y,4)
prediction=model(a,b,x)
loss = loss_function(a, b, x, y)
print(a,b,loss)
plt.scatter(x,y)
plt.plot(x,prediction)
```

Итерация 5:
![image](https://user-images.githubusercontent.com/106770342/192854895-a1923ca8-265f-464d-a06b-c9370b4041c3.png)
```py
In [ ]:
a,b = iterate(a,b,x,y,5)
prediction=model(a,b,x)
loss = loss_function(a, b, x, y)
print(a,b,loss)
plt.scatter(x,y)
plt.plot(x,prediction)
```
Итерация 10000:
![image](https://user-images.githubusercontent.com/106770342/192855850-9be00807-707a-4591-ba93-774188c2465a.png)
```py
In [ ]:
a,b = iterate(a,b,x,y,10000)
prediction=model(a,b,x)
loss = loss_function(a, b, x, y)
print(a,b,loss)
plt.scatter(x,y)
plt.plot(x,prediction)
```

## Задание 3
### Должна ли величина loss стремиться к нулю при изменении исходных данных? Ответьте на вопрос, приведите пример выполнения кода, который подтверждает ваш ответ.

Ответ: Величина loss стремиться к нулю при изменении исходных данных, чем больше итераций, тем меньше loss, потому что метод ищет модели с минимальным значением отклонения.

Вот первые 5 итераций. Видно как величина loss с значения 2701.362722222572 плавно падает до 2489.678463133785. К десятитысячной итерации loss уже равен 190.36446701975595.
![image](https://user-images.githubusercontent.com/106770342/192860357-0eec4b6f-8db4-49c5-bc13-8429daf0598b.png)

### Какова роль параметра Lr? Ответьте на вопрос, приведите пример выполнения кода, который подтверждает ваш ответ. В качестве эксперимента можете изменить значение параметра.
Параметр Lr является шагом для градиентного спуска и "скоростью обучения" для алгоритма линейной регрессии. 

При Lr = 0.000000001:
![image](https://user-images.githubusercontent.com/106770342/192861302-6a31acef-99f1-45f5-b191-b721262ee2bd.png)

При Lr = 0.001:
![image](https://user-images.githubusercontent.com/106770342/192861509-95bb2af1-2405-4849-973b-96df24e23458.png)

При Lr = 0.000001:
![image](https://user-images.githubusercontent.com/106770342/192861636-52cd39d3-0541-47bf-ad01-51201b0e0d6a.png)

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
