# АНАЛИЗ ДАННЫХ И ИСКУССТВЕННЫЙ ИНТЕЛЛЕКТ [in GameDev]
Отчет по лабораторной работе #4 выполнил(а):
- Беспалова Полина Александровна
- РИ210910
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
Ознакомиться с понятием перцептрона и понять, как он работает, используя код для него.

## Задание 1
### В проекте Unity реализовать перцептрон, который умеет производить вычисления:
Ход работы:
- Я просмотрела лекцию и выполнила аналогичные действия. Первое, что я сделала, это внесла данные для OR, последовательно меняя значения эпох, анализируя количество ошибок и сохраняя полученные данные. Вот, что у меня получилось:
![Скриншот 25-11-2022 144357](https://user-images.githubusercontent.com/113704972/203974771-5172ffb7-ac7c-49bd-b971-2e91e950f2ec.jpg)
Для 1 эпохи значения ошибок около двух. Обучение проходит пл:
![Скриншот 25-11-2022 145624](https://user-images.githubusercontent.com/113704972/203974784-cd5b3bc1-97b0-43c1-9734-6cb31d93bd85.jpg)
Для 2 эпохи также ещё не научился:
![Скриншот 25-11-2022 145800](https://user-images.githubusercontent.com/113704972/203974823-ed3e7b27-a166-485b-b951-71b18407229b.jpg)
Для 3 эпохи он уже начал нормально работать на некоторой итерации:
![Скриншот 25-11-2022 150110](https://user-images.githubusercontent.com/113704972/203974879-9c93447d-7ecb-4148-8c9a-dc4194658ea2.jpg)
Для 4 эпохи стало понятно, что этого хватило, чтобы полностью обучиться:
![Скриншот 25-11-2022 150332](https://user-images.githubusercontent.com/113704972/203974894-779c5c30-a669-4e35-a01e-ac95031bd0c0.jpg)
Также, я пробовала писать значения эпохи 6,8 и 10, увидела, что всё выполняется без ошибок. Все полученные данные я записывала, чтобы потом построить графики. Для операции OR сделала вывод, что для полного успешного обучения прецептрона достаточно 4 эпох.

- Далее я проверяла операцию AND:
Ошибки пропали лишь к 6 итерации. На 4 и остальных до неё они еще были:
![Скриншот 25-11-2022 150959](https://user-images.githubusercontent.com/113704972/203975738-53ce331b-6610-41e1-a572-df097df9b60c.jpg)
![Скриншот 25-11-2022 151731](https://user-images.githubusercontent.com/113704972/203975745-351bfa5a-aa42-4566-9ca2-ad281b7bc2f8.jpg)
![Скриншот 25-11-2022 152157](https://user-images.githubusercontent.com/113704972/203975750-0b631ae8-0588-4dc8-ac0e-3fa99d13c10b.jpg)
Сделаю вывод, что в принципе достаточно 6 эпох для успешного обучения, однако не всегда, так как данные были довольно разные.


- Следующей была операция NAND:
![Скриншот 25-11-2022 151851](https://user-images.githubusercontent.com/113704972/203976574-186923f6-9dad-4f35-a96e-ca5bd9da91a8.jpg)
![Скриншот 25-11-2022 151909](https://user-images.githubusercontent.com/113704972/203976578-1656f000-d8df-4d45-b48f-a7f1755a4c51.jpg)
Здесь достаточно было 4-х эпох.

- Последней была XOR:
![Скриншот 25-11-2022 144357](https://user-images.githubusercontent.com/113704972/203976701-c75edef3-a171-4034-bc8a-30120d23166e.jpg)
На данной операции я заметила, что, сколько бы эпох я ни выставляла, ошибки были, а перестали появляться лишь к 6-ой эпохе.

## Задание 2
### Построить графики зависимости количества эпох от ошибки обучения. Указать от чего зависит необходимое количество эпох обучения.
- Для построения графиков я использовала EXCEL, куда и вводила данные после каждой итерации.
- На скриншоте приведены графики для всех логических операций:
![Скриншот 25-11-2022 163624](https://user-images.githubusercontent.com/113704972/203977440-bde6d517-a5e1-48f1-8f70-5f313aa68289.jpg)


## Задание 3
### Построить визуальную модель работы перцептрона на сцене Unity.

К сожалению, не справилась :(


## Выводы
- При выполнении лабораторной работы я разобралась, как работает прецептрон, как можно проверять его работу и сделала выводы о корректной работе некоторых логических операций. Более того, могу отметтть, что сделала для себя вывод, что в среднем прецептрону нужно минимум 3-4 эпохи для обучения без ошибок. Всё зависит от количества входных данных, где их здесь всего 2, что довольно мало. Поэтому необходимо всего 3-4 эпохи для обучения.
