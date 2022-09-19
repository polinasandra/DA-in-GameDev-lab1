# АНАЛИЗ ДАННЫХ И ИСКУССТВЕННЫЙ ИНТЕЛЛЕКТ [in GameDev]
Отчет по лабораторной работе #1 выполнил(а):
- Беспалова Полина Александровна
- РИ210910
Отметка о выполнении заданий (заполняется студентом):

| Задание | Выполнение | Баллы |
| ------ | ------ | ------ |
| Задание 1 | # | 60 |
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
Ознакомиться с основными операторами зыка Python на примере реализации линейной регрессии.

## Задание 1
### Написать программы Hello World на Python и Unity:
Ход работы:
- Код и вывод программы на языке Python:
![Скриншот 19-09-2022 185326](https://user-images.githubusercontent.com/113704972/191034079-c9fd96ed-2e6f-4131-aa44-c6f5919661fa.jpg)
Демонстрация сохранения документа GoogleCollab на мой диск:
![Скриншот 19-09-2022 185341](https://user-images.githubusercontent.com/113704972/191034073-4b87c9b8-cdf9-4e40-a5da-eaf616e1161d.jpg)
- Для Unity:
 создаем новый объект, в Assets создаем C# Script и пишем код для вывода Hello, world!
![Скриншот 19-09-2022 184421](https://user-images.githubusercontent.com/113704972/191034577-da2b04b7-bae1-4b12-b9fd-7b64b9f742a2.jpg)
Добавляем наш скрипт в объект и запускаем код:
![Скриншот 19-09-2022 183913](https://user-images.githubusercontent.com/113704972/191034654-cfe6ed1b-92e8-4d33-98f8-06669882402e.jpg)
- Начинаю итерацию. Шаг 1: Инициализация и модель итеративной оптимизации

## Задание 2
### В разделе "Ход работы" пошагово выполнить каждый пункт с описанием и примеров реализации задачи по теме лабораторной работы.

- Произвожу подготовку данных для работы с алгоритмом линейной регрессии:
![Скриншот 19-09-2022 191154](https://user-images.githubusercontent.com/113704972/191054986-1ddbf97e-fa57-480c-b325-4e67ae8ce32f.jpg)

- Определяю связанные функции. Функция модели: определяет модель линейной регрессии wx+b. Функция потерь: функция потерь среднеквадратичной ошибки. Функция оптимизации: метод градиентного спуска для нахождения частных производных w и b.
![Скриншот 19-09-2022 192121](https://user-images.githubusercontent.com/113704972/191055044-ece15049-c9b4-4e48-95cc-6b4cf6c1c29f.jpg)

- Начинаю итерацию. Шаг 1. Инициализация и модель итеративной оптимизации:
![Скриншот 19-09-2022 204527](https://user-images.githubusercontent.com/113704972/191058485-0ad0caff-00ee-4bc5-bf79-927476020bf9.jpg)

- Шаг 2. На второй итерации отображается значения параметров, значения потерь и эффекты визулизации после итерации:
![Скриншот 19-09-2022 205002](https://user-images.githubusercontent.com/113704972/191059356-e9ec4249-bde7-42dc-a818-db6d7ac13659.jpg)


Шаг 3. Третья итерация показывает значения параметров, значения потерь и визуализацию после итерации:
![Скриншот 19-09-2022 205029](https://user-images.githubusercontent.com/113704972/191059394-99f7df2e-2796-48cd-a740-ac813ec13746.jpg)


Шаг 4. На четвёртой итерации отображаются значения параметров, значения потерь и эффекты визулизации:
![Скриншот 19-09-2022 205038](https://user-images.githubusercontent.com/113704972/191059427-e1c2641d-f6b7-4034-8c56-a0949303a331.jpg)


Шаг 5. Пятая итерация показывает значение параметра, значение потерь и эффект визуализации после итерации:
![Скриншот 19-09-2022 205049](https://user-images.githubusercontent.com/113704972/191059466-25ca7819-dc28-4f35-9fdb-55d8b89f62ce.jpg)

Шаг 6. 10000-я итерация, показывающая значение параметров, потери и визуализацию после итерации:
![Скриншот 19-09-2022 205207](https://user-images.githubusercontent.com/113704972/191059802-9f30dae2-b51a-41b8-91b4-a2d0be40c104.jpg)




## Задание 3
### Изучить код на Python и ответить на вопросы:

```py

import numpy as np
import matplotlib.pyplot as plt

x=[3,21,22,34,54,34,55,67,89,99]
x=np.array(x)
y=[2,22,24,65,79,82,55,130,150,199]
y=np.array(y)

plt.scatter(x,y)

def model(a,b,x):
    return a*x+b

def loss_function(a,b,x,y):
    num = len(x)
    prediction = model(a,b,x)
    return (0.5/num)*(np.square(prediction-y)).sum()

def optimize(a,b,x,y):
    num = len(x)
    prediction = model(a,b,x)
    da = (1.0/num) * ((prediction -y)*x).sum()
    db = (1.0/num) * ((prediction - y).sum())
    a = a-Lr*da
    b - b - Lr*db
    return a,b

def iterate(a,b,x,y,times):
    for i in range(times):
        a,b = optimize(a,b,x,y)
        return (a,b)

a=np.random.rand(1)
print(a)
b=np.random.rand(1)
print(b)
Lr = 0.0000001

a,b = iterate(a,b,x,y,1)
prediction = model(a,b,x)
loss = loss_function(a,b,x,y)
print(a,b,loss)
plt.scatter(x,y)
plt.plot(x,prediction)


```

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
