# Прогнозирование биологического ответа

Данные представлены в формате CSV.  Каждая строка представляет молекулу. 

    - Первый столбец Activity содержит экспериментальные данные, описывающие фактический биологический ответ [0, 1]; 
    - Остальные столбцы D1-D1776 представляют собой молекулярные дескрипторы — это вычисляемые свойства, которые могут фиксировать некоторые характеристики молекулы, например размер, форму или состав элементов.

![](https://raw.githubusercontent.com/IgorAbalakin/Biological_Response_task/main/dst-3-ml-7-10.png)

**Задача:** необходимо обучить две модели: логистическую регрессию и случайный лес. Далее сделать подбор гиперпараметров с помощью четырех методов оптимизации(GridSeachCV, RandomizedSearchCV, Hyperopt, Optuna). В качестве метрики использовать F1-score.


**Результаты**

1. Наилучший f1_score: 0.83 (RandomForest, гиперпараметры {'criterion': 0, 'max_depth': 24.0, 'min_samples_leaf': 2.0, 'n_estimators': 210.0}, подобраны с помощью Hyperopt).

2. Подбор параметров и обучение модели случайного леса проходит стабильно быстрее по сравнению с логистической регрессией.

3. Кросс-валидация существенно увеличивает время подбора параметров и обучения, и лишь в одном случае из четырех для данной задаче позволила улучшить значение метрики.