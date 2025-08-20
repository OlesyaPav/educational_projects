# Компьютерное зрение
Учебный проект

## Цель проекта:
Построить модель, которая по фотографии определит приблизительный возраст человека.

## Описание данных:
Данные взяты с сайта ChaLearn Looking at People.
Данные представляют собой набор: одна папка со всеми изображениями и CSV-файл двумя колонками: file_name и real_age.

## Использовала библиотеки:
 - import matplotlib.pyplot as plt
 - import pandas as pd
 - import numpy as np
 - import tensorflow as tf
 - from tensorflow.keras.optimizers import Adam
 - from tensorflow.keras.preprocessing.image import ImageDataGenerator
 - from tensorflow.keras.layers import Dense, Flatten, Conv2D, GlobalAveragePooling2D
 - from tensorflow.keras.models import Sequential
 - from tensorflow.keras.layers import BatchNormalization
 - from tensorflow.keras.layers import Dropout
 - from tensorflow.keras.applications.resnet import ResNet50
 - from tensorflow.keras.preprocessing.image import ImageDataGenerator
 - from sklearn.metrics import mean_absolute_error

## Общий вывод:
Найдена модель, сверточная нейросеть, которая определяет возраст человека по фотографии с точностью до 6,9836 лет.

Модель оценивалась на метрике MAE, т.к. данные содержат выбросы. Модель достаточно качественная. По сравнению с простой моделью предсказания медианы, где MAE 12,91 лет, она хорошо определяет возраст.

Модель немного переобучилась: MAE train (7,4717) > MAE test (6,9836).

В возрасте 25 лет и более ошибка 6,9836 некритична, потому что если модель и ошибется в меньшую сторону, и определит 18 и более лет, то алкоголь покупателю уже можно продать. А в более старшем возрасте люди с разницей в почти 7 лет во многом похожи. Критично продать алкоголь покупателю которому 11 лет, а модель определит его как совершеннолетнего. Покупателям до 25 лет, по-прежнему обязателньо предъявлять паспорт.



