# Определение стоимости автомобилей
## Задача:
<details><summary></summary>
  
В нашем распоряжении исторические данные: технические характеристики, комплектации и цены автомобилей.<br/>
Необходимо построить модель для определения стоимости.


### Заказчику важны:

* качество предсказания;
* скорость предсказания;
* время обучения.
</details>

## Описание данных:
<details><summary>В предоставленной выборке:</summary>

| Признаки |    Интерпретация |
| :--- | :----------- |
| DateCrawled | - дата скачивания анкеты из базы |
| VehicleType | - тип автомобильного кузова |
| RegistrationYear | - год регистрации автомобиля |
| Gearbox     | - тип коробки передач |
| Power     | - мощность (л.с.) |
| Model | - модель автомобиля |
|Kilometer|- пробег (км)|
| RegistrationMonth     | - месяц регистрации автомобиля |
|FuelType|- тип топлива|
|Brand|- марка автомобиля|
|NotRepaired|- была машина в ремонте или нет|
| DateCreated | - дата создания анкеты |
|NumberOfPictures|- количество фотографий автомобиля|
|PostalCode|- почтовый индекс владельца анкеты (пользователя)|
|LastSeen|- дата последней активности пользователя|

| Целевой признак |    Интерпретация |
| :--- | :----------- |
| Price | - цена (евро) |
</details>

## Используемые библиотеки:
* pandas
* numpy
* sklearn
* matplotlib
* seaborn
* IPython
* catboost 
* lightgbm

## Отработанные методы и навыки:
* Предобработка данных, 
* Техника прямого кодирования,
* Техника порядкового кодирования,
* Кросс-валидация, 
* Обучение моделей бустинга, 
* Анализ качества
* Анализ времени работы модели.
<details><summary>В данном исследовании получены ответы на поставленные задачи Заказчика, а именно:</summary>

|Вопросы|Выводы|
|:--- |:----------- |
|Построить модель для определения стоимости.<br/>Заказчику важны:<ul><li>качество предсказания;</li><li>скорость предсказания;</li><li>время обучения.|В ходе проделанной работы были проанализированы данные сервиса по продаже автомобилей.<ul><li>По подготовленным данным были обучены следующие модели:<ul><li>Модель `LinearRegression`</li><li>Модель `DecisionTreeRegressor`</li><li>Модель `LGBMRegressor`</li><li>Модель `CatBoostRegressor`.</li></ul>Для оценки качества моделей использовалась метрика RMSE</li><li>Учитывая значимые, для заказчика критерии:<ul><li>На основании полученных данных выбрана самая точная модель<br/>`LGBMRegressor` (t_обучения = 273с, RMSE = 1683.758)</li><li>Самая быстрая и точная модель<br/>`DecisionTreeRegressor` (t_обучения = 3.22с, RMSE = 2300.157)</li></ul></li></ul>В целом, модели Бустинга более точны в своих оценках, нежели простые регрессоры, но подбор их параметров и обучение занимают гораздо большее время. Если опираться на качество предсказания модели, то первое место за:<ul><li>`LGBMRegressor`(на тестовой выборке: t_предсказания = 5.01с, RMSE = 1691.239)|
