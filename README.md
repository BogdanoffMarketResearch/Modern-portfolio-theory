# Портфельная теория Марковица

### Задача
Построить портфель минимального риска, задача отличается от классической тем, что мы берем не только актив, но и опцион пут на него. 

### Библиотеки
- numpy, scipy, matplotlib
- [gurobipy](https://www.gurobi.com/): для оптимизации модели (платная, но есть бесплатная подписка для студентов)
- [Alpha Vantage](https://www.alphavantage.co/documentation/): API для данных
- [requests](https://requests.readthedocs.io/en/master/): запросы к Alpha Vantage
- [Prophet](https://facebook.github.io/prophet/docs/quick_start.html#python-api): для прогнозирования временного ряда

### Система файлов
- [reader.py](https://github.com/armeni/portfolio/blob/main/reader.py): чтение и предобработка даных. 
    * Класс GettingData с помощью requests обращается к сайту по тикеру компании и скачивает исторические данные (за 20+ лет) в формате csv. 
    * Класс Reader считывает csv-файл и обрабатывает его, оставляя только данные по дневным ценам закрытия торгов за определенный промежуток времени (с 03.01.2017 по 01.12.2020).

- [calculator.py](https://github.com/armeni/portfolio/blob/main/calculator.py): расчет необходимых значений для оптимизации (ожидаемая доходность портфеля, волатильность, риск порфтеля, стоимость опциона пут, ковариационная матрица).

- [forecast.ipynb](https://github.com/armeni/portfolio/blob/main/forecast.ipynb): прогнозирование цены акций компаний на месяц.

- [optimization.ipynb](https://github.com/armeni/portfolio/blob/main/optimization.ipynb): создание оптимизионной модели, вывод результатов.

- [results.csv](https://github.com/armeni/portfolio/blob/main/results.csv): все данные, включая прогноз. С этими данными происходит работа в optimization.ipynb
