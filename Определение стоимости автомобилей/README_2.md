# Определение стоимости автомобилей

Сервис по продаже автомобилей с пробегом «Не бит, не крашен» разрабатывает приложение для привлечения новых клиентов. В нём можно быстро узнать рыночную стоимость своего автомобиля. В вашем распоряжении исторические данные: технические характеристики, комплектации и цены автомобилей. Вам нужно построить модель для определения стоимости.

Заказчику важны:
- качество предсказания;
- скорость предсказания;
- время обучения.

## Описание проекта.
## Цель - 
разработать модель для определения рыночной стоимости автомобиля, отвечающую критериям заказчика.

## Задачи:
1. Загрузить данные.
2. Изучить, заполнить пропущенные значения, обработать аномалии в столбцах. оставить только информативные признаки.
3. Подготовить выборки для обучения моделей.
4. Обучить модели: LightGBM, LinearRegression, - с разными гиперпараметрами.
5. Проанализировать время обучения, время предсказания и качество моделей.
6. Выбрать лучшую модель, проверить её качество на тестовой выборке.

## Описание данных:

Признаки:

- DateCrawled — дата скачивания анкеты из базы
- VehicleType — тип автомобильного кузова
- RegistrationYear — год регистрации автомобиля
- Gearbox — тип коробки передач
- Power — мощность (л. с.)
- Model — модель автомобиля
- Kilometer — пробег (км)
- RegistrationMonth — месяц регистрации автомобиля
- FuelType — тип топлива
- Brand — марка автомобиля
- Repaired — была машина в ремонте или нет
- DateCreated — дата создания анкеты
- NumberOfPictures — количество фотографий автомобиля
- PostalCode — почтовый индекс владельца анкеты (пользователя)
- LastSeen — дата последней активности пользователя.

Целевой признак:

- Price — цена (евро)
- Учебные проекты

## Используемые библиотеки
- import pandas as pd
- import re
- import matplotlib.pyplot as plt
- from sklearn.linear_model import LinearRegression, Ridge
- from sklearn.preprocessing import StandardScaler
- from sklearn.model_selection import GridSearchCV
- from sklearn.model_selection import train_test_split
- import time
- from sklearn.model_selection import KFold
- from category_encoders import TargetEncoder
- from sklearn.pipeline import Pipeline
- from sklearn.compose import ColumnTransformer
- from sklearn.preprocessing import OneHotEncoder, OrdinalEncoder, StandardScaler, MinMaxScaler
- from sklearn.impute import SimpleImputer
- import numpy as np
- import pandas as pd
- from sklearn.tree import DecisionTreeRegressor
- from sklearn.metrics import root_mean_squared_error
- import lightgbm as lgb
- from sklearn.model_selection import cross_val_score

## ВЫВОД:
Найдена качественная модель предсказания рыночной стоимости автомобиля. Это LightGBM ("learning_rate":0.1, "num_leaves":40). Она обучается за 6 с, предсказывает за 3 с. RMSE модели 1831.
