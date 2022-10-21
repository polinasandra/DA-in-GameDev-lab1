# АНАЛИЗ ДАННЫХ И ИСКУССТВЕННЫЙ ИНТЕЛЛЕКТ [in GameDev]
Отчет по лабораторной работе #2 выполнил(а):
- Беспалова Полина Александровна
- РИ210910
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
- Код реализации выполнения задания. Визуализация результатов выполнения.
- Задание 2.
- Код реализации выполнения задания. Визуализация результатов выполнения.
- Задание 3.
- Код реализации выполнения задания. Визуализация результатов выполнения.
- Выводы.

## Цель работы
Познакомиться с программными средствами для создания системы машинного обучения и ее интеграции в Unity.

## Задание 1
### Реализовать систему машинного обучения в связке Python - Google-Sheets – Unity.
Ход работы:
- В созданный проект Unity я добавила ML Agent. Последовательно добавила .json – файлы:
![Скриншот 21-10-2022 153921](https://user-images.githubusercontent.com/113704972/197217620-dd07571d-91ab-408d-97c6-cdd8be945d42.jpg)

- Создала на сцене плоскость, куб и сферу. Создала простой C# скрипт-файл и подключила его к сфере:
![Скриншот 21-10-2022 153843](https://user-images.githubusercontent.com/113704972/197217939-bfe09059-e05f-45b7-8ff2-d4a5cd2614ed.jpg)
![Скриншот 21-10-2022 162137](https://user-images.githubusercontent.com/113704972/197217969-78004ee4-81f9-4805-953e-2f9db03c9f37.jpg)

- Объекту «сфера» добавила компоненты Rigidbody, Decision Requester, Behavior Parameters и настройла их:

![Скриншот 21-10-2022 172054](https://user-images.githubusercontent.com/113704972/197218140-7c15a0af-a30b-4d8f-ae46-9cf9e5dd02e2.jpg)
![Скриншот 21-10-2022 172100](https://user-images.githubusercontent.com/113704972/197218198-086e1a8e-8e87-4c6e-a13b-186c8fb40568.jpg)

- Запустила работу MLAгент'а:
![Скриншот 21-10-2022 175618](https://user-images.githubusercontent.com/113704972/197218409-2b0aa0a1-a66e-458e-bc1d-803782a3fc4e.jpg)
![Скриншот 21-10-2022 180115](https://user-images.githubusercontent.com/113704972/197218490-d8010fb8-4429-4966-b3fb-6ad0788f3161.jpg)

https://user-images.githubusercontent.com/113704972/197219286-b636851d-db3a-4e2d-8c2c-cb77c97fcdd5.mp4



- Затем я создала 3 копии модели, увеличила их и обучила:
- 9 копий: 
![Скриншот 21-10-2022 181847](https://user-images.githubusercontent.com/113704972/197218807-d31607f0-c1cc-4f6b-b2ec-58b2395ac1bc.jpg)

- 27 копий: 
![Скриншот 21-10-2022 182610](https://user-images.githubusercontent.com/113704972/197218865-beefe130-5317-49c4-96fc-cf7196cbf36f.jpg)

## Задание 2
### Подробно опишите каждую строку файла конфигурации нейронной сети, доступного в папке с файлами проекта по ссылке. Самостоятельно найдите информацию о компонентах Decision Requester, Behavior Parameters, добавленных на сфере.

Decision Requester запрашивает решение через регулярные промежутки времени, а Behavior Parameters определяет принятие решений объектов в котором мы указываем, какой тип поведения используется, будь то удалённый процесс обучения или модель, которая уже обучена.

```py
behaviors:
RollerBall: # id агента
trainer_type: ppo # режим обучения
hyperparameters:
batch_size: 10 # указываем, сколько происходит опытов на каждой итерации
buffer_size: 100 # сколько нужно опыта набрать перед обновлением модели
learning_rate: 3.0e-4 # начальная скорость обучения
beta: 5.0e-4 # обозначаем силу регуляции энтропии
epsilon: 0.2 # расхождения между старой и новой политиками после обновления
lambd: 0.99 # параметр регуляции, показывает, насколько агент полагается на value estimate
num_epoch: 3 # показывает при выполнении оптимизации, сколько проходов через буфер опыта совершается
learning_rate_schedule: linear # уменьшает скорость, показывает скорость обучения изменяется со временем
network_settings:
normalize: false # происходит отключание нормализации входных данных
hidden_units: 128 # сколько нейронов в скрытых слоях сети
num_layers: 2 # сколько скрытых слоёв в сети
reward_signals:
extrinsic:
gamma: 0.99 # коэффициент скидки для вознаграждений
strength: 1.0 # коэффициент, на который умножается данное вознаграждение
max_steps: 500000 # общее количество шагов, которые выполнятся до завершения обучения в среде
time_horizon: 64 # количество опыта для каждого агента, который нужно набрать, прежде чем добавлять его в буфер
summary_freq: 10000 # количество опыта, необходимого перед отображением статистики

```
## Задание 3 
### Доработала сцену и обучила ML-Agent таким образом, чтобы шар перемещался между двумя кубами разного цвета.
- Создала еще один таргет. Переписала код так, чтобы он работал под два таргета.

![Скриншот 21-10-2022 184616](https://user-images.githubusercontent.com/113704972/197221972-ca58789d-787f-4e64-bfbc-71d267dd9bdd.jpg)
![Скриншот 21-10-2022 193853](https://user-images.githubusercontent.com/113704972/197222355-9cc83e5c-c45d-4017-8462-273d72e99624.jpg)

- Обучила модели и запустила работу MLAгент'а:
![bandicam 2022-10-21 19-11-49-865](https://user-images.githubusercontent.com/113704972/197223201-4f0518fa-a93d-4bfe-8800-8bc42dfb88be.gif)
![Скриншот 21-10-2022 193903](https://user-images.githubusercontent.com/113704972/197222379-989280cc-47fa-45a2-9698-e95c7252ee76.jpg)

![Скриншот 21-10-2022 191356](https://user-images.githubusercontent.com/113704972/197225933-d9fedb57-a9d1-4de1-8bcd-098639854279.jpg)



## Выводы

В ходе работы я научилась работать с ML-агентом, поняла как пишется код для обучения моделей, научилась выводить результат обучения, а также заметила, что при увеличении количества копий модели, она быстрее обучается. 
Для себя я поняла, что игровой баланс занимается выяснением чисел, которые следует использовать в игре (например, равновесие между элеентами игры), он позволяет сделать игру более цельной, играбельной. 
Более того, я осознала, что правильность вычислений для машинного обучения необходима для корректной работы программы и, что тоже очень важно, для заинтересованности игрока в процессе, нужно уметь подсчитывать характеристики так, чтобы игроку было интересно играть и проходить уровни.

