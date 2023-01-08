# Нейронные сети для прогнозирования временных рядов

**Нейросеть в машинном обучении** — это математическая модель, которая работает по принципу нейронной сети живого организма. В отличие от нейросети животного, которая передаёт сигнал от мозга к другим органам и полностью регулирует жизнедеятельность организма, компьютерная нейросеть учится решать только ту задачу, которую ей ставит человек.

Суть работы нейронных сетей — смоделировать способ решения задачи, присущий людям. Чтобы определить пол человека, изображённого на фотографии, нейросеть будет использовать те же принципы, по которым работает человеческое зрение.
Использование нейронных сетей опирается на накопленный опыт в виде данных и подходит для решения задач, с которыми человечество уже знакомо. Например, нейросети могут помочь организовать полёт внутри Солнечной системы, а для планирования полёта за её пределы лучше опираться на физическую теорию.

## Виды нейронных сетей

Классификация нейронных сетей основана на задачах, с которыми они работают:
* многослойные нейронные сети, или перцептроны, обрабатывают числовые данные;
* свёрточные нейронные сети работают с изображениями;
* рекуррентные нейронные сети собирают и обрабатывают информацию, которая меняется с течением времени;
* генеративные нейронные сети создают контент — тексты, изображения.

## Понятие временных рядов

>Методические указания к лабораторным занятиям по дисциплине "Машинное обучение на больших данных в информационно-аналитических системах" [Электронный ресурс] - сост. Т. А. Васяева. – Донецк: ДОННТУ, 2020.

**Временной ряд** представляет собой последовательность наблюдений за 
изменениями во времени значений параметров некоторого объекта или 
процесса. Строго говоря, каждый процесс непрерывен во времени, то есть 
некоторые значения параметров этого процесса существуют в любой момент 
времени. Но для задач анализа не нужно знать значения параметров объектов в 
любой момент времени. Интерес представляют временные отсчеты – значения 
зафиксированные в некоторые, обычно равноотстоящие моменты времени. 
Отсчеты могут браться через различные промежутки: через минуту, час, день, 
неделю, месяц или год – в зависимости от того, насколько детально должен 
быть проанализирован процесс. В задачах анализа временных рядов мы имеем 
дело с дискретным временем, когда каждое наблюдение за параметром 
образуют временной отсчет.

Временные ряды могут быть одномерными и многомерные. Одномерные 
ряды содержат наблюдения за изменением только одного параметра 
исследуемого процесса или объекта, а многомерные − за двумя параметрами 
или более.

Цель анализа временного ряда – построение его математической модели, 
с помощью которой можно обнаружить закономерности поведения ряда, а 
также построить прогноз его дальнейшего развития.

Проблемы прогнозирования временных рядов являются сложным типом задачи прогнозного моделирования.

В отличие от прогнозного регрессионного моделирования, временной ряд также добавляет сложность зависимости последовательности между входными переменными.

## Анализ фондового рынка

**Котировка** — цена (курс, процентная ставка) товара, которую объявляет 
продавец или покупатель и по которой они готовы совершить покупку или 
продажу (предлагается оферта). Обычно подразумевается относительно быстро 
меняющаяся цена, например биржевая. 
На биржах цены регистрирует специальная котировальная комиссия 
(комитет). Обычно публикуются цены открытия и закрытия биржевой сессии, 
максимальная и минимальная цена дня. Такие публикации называют 
«официальная котировка». 
Котировки отражают складывающуюся на торгах конъюнктуру рынка, 
соотношение спроса и предложения. 

OHLC – это сокращенное обозначение котировок, которые указываются 
для элементарной диаграммы какого-либо ценового графика. К примеру, им 
может быть бар или японская свеча. А этой аббревиатуре О обозначает Open – 
цену открытия интервала, H означает High — максимум цены интервала, L 
означает Low – минимум цены интервала и C означает Close – цену закрытия 
интервала. Каждый график типа OHLC представляет собой классический 
столбиковый график, бар. В нем каждый интервал времени (например, 5 минут) 
представлен OHLC ценами прямо внутри этого интервала.

Цена открытия — Open, говорит трейдеру о том, что находилась эта цена 
в момент самого начала данного бара, то есть в самый начальный момент 
времени определенного временного отрезка, описанного в баре. Благодаря этому параметру трейдеру всегда известно с какой цены начался определенный 
временной отрезок на рынке FOREX. Цена закрытия — Close, является 
значением, которое приобретает цена за определенный промежуток времени, 
содержащийся в конкретном баре. Нужно сказать, что цена закрытия может не 
совпадать с ценой открытия следующего бара, особенно тогда, когда цены 
меняются очень быстро. Между ценой закрытия старого бара и открытия 
нового проходит достаточно много времени, которого хватает для изменения 
цены. Максимальное и минимальное значение цены — High и Low, говорят о 
наибольшем или наименьшем значении, которое приобреталось ценой за время 
формирования одного конкретного бара. Каждый опытный трейдер по 
информации, которая содержится в баре, сможет сделать анализ и предоставить 
качественный вывод о том, что делается на рынке в данный момент, каково его 
поведение, какие тенденции можно наблюдать. 

## Пример

Для примера выберем данные для анализа на сайте: https://www.finam.ru/quotes - Сбербанка.

*Задание:*
разработать рекуррентную нейросеть для прогнозирования котировок (цена открытия и / или закрытия), обязателен слой LSTM.
Предусмотреть: 
* нормирование / денормирование данных; ‒ обязательное сохранение / считывание обученной НС; 
* отдельный этап тестирования для указанного интервала в будущем; 
* вывод и расчет ошибки на обучающих, тестовых (валидационных) данных; 
* вывод результатов в файл (дата, спрогнозированное значение, реальное значение (если такое имеется для текущего прогноза), ошибка); 
* вывод результатов на графиках (отдельно обучающая выборка, отдельно тестовая и обе на одном графике).

Прежде чем мы начнем, сначала импортируем все функции и классы, которые собираемся использовать. Это предполагает рабочую среду SciPy с установленной библиотекой глубокого обучения Keras.

LSTM чувствительны к масштабу входных данных, особенно когда используются функции активации сигмоида (по умолчанию) или tanh. Хорошей практикой может быть изменение масштаба данных до диапазона от 0 до 1, также называемого нормализацией. Мы можем легко нормализовать набор данных, используя MinMaxScaler класс предварительной обработки из библиотеки scikit-learn:
```python
scaler = MinMaxScaler(feature_range=(0, 1))
dataset = scaler.fit_transform(dataset)
dataset
```
После того, как мы смоделируем наши данные и оценим навыки нашей модели на обучающем наборе данных, нам нужно получить представление о навыках модели на новых невидимых данных.

Для данных временных рядов важна последовательность значений. Поэтому мы вычисляем индекс точки разделения и делим данные на обучающие наборы данных с 67% наблюдений, которые мы можем использовать для обучения нашей модели, оставляя 33% для тестирования модели:
```python
train_size = int(len(dataset) * 0.67)
test_size = len(dataset) - train_size
train, test = dataset[0:train_size,:], dataset[train_size:len(dataset),:]
print(len(train), len(test))
```
Сеть LSTM ожидает, что входные данные (X) будут снабжены определенной структурой массива в виде:[образцы, временные шаги, особенности].

В настоящее время наши данные находятся в форме: [образцы, особенности] и мы формулируем проблему как один временной шаг для каждого образца. Мы можем преобразовать подготовленный поезд и проверить входные данные в ожидаемую структуру, используя numpy.reshape() следующее:
```python
trainX = numpy.reshape(trainX, (trainX.shape[0], 1, trainX.shape[1]))
testX = numpy.reshape(testX, (testX.shape[0], 1, testX.shape[1]))
```
Теперь проектируем и приспособливаем нашу сеть LSTM.

Сеть имеет видимый слой с 1 входом, скрытый слой с 4 блоками или нейронами LSTM и выходной слой, который делает прогноз одного значения. Функция активации сигмоида по умолчанию используется для блоков LSTM. Сеть обучена для 100 эпох, и используется размер партии 1.
```python
model = Sequential()
model.add(LSTM(4, input_shape=(1, look_back)))
model.add(Dense(1))
model.compile(loss='mean_squared_error', optimizer='adam')
model.fit(trainX, trainY, epochs=100, batch_size=1, verbose=2)
```
После того, как модель подобрана, мы можем оценить производительность модели в тестовых наборах данных. Это даст нам точку сравнения для новых моделей:
```python
trainPredict = model.predict(trainX)
testPredict = model.predict(testX)
# invert predictions
trainPredict = scaler.inverse_transform(trainPredict)
trainY = scaler.inverse_transform([trainY])
testPredict = scaler.inverse_transform(testPredict)
testY = scaler.inverse_transform([testY])
#расчет ошибки на обучающих, тестовых (валидационных) данных
trainScore = math.sqrt(mean_squared_error(trainY[0], trainPredict[:,0]))
print('Train Score: %.2f RMSE' % (trainScore))
testScore = math.sqrt(mean_squared_error(testY[0], testPredict[:,0]))
print('Test Score: %.2f RMSE' % (testScore))
```

**Для обучающей выборки график:**
```python
labels = ['History', 'True Future', 'Model Prediction']
trainPredictPlot = numpy.empty_like(dataset)
trainPredictPlot[:, :] = numpy.nan
trainPredictPlot[look_back:len(trainPredict)+look_back, :] = trainPredict
plt.title("Обучающая выборка")
plt.plot(trainPredictPlot)
plt.show()
```
**Результат:**<br>
![2023-01-08 (1)](https://user-images.githubusercontent.com/79097818/211195142-5e5c5027-3afb-4fbb-87e3-5422945e41dc.png)

**Тестовая выборка:**
```python
testPredictPlot = numpy.empty_like(dataset)
testPredictPlot[:, :] = numpy.nan
testPredictPlot[len(trainPredict)+(look_back*2)+1:len(dataset)-1, :] = testPredict
plt.plot(testPredictPlot)
plt.title("Тестовая выборка")
plt.show()
```
**Результат:**<br>
![2023-01-08 (2)](https://user-images.githubusercontent.com/79097818/211195149-b157c8d0-febc-452f-9e11-1b7188d99c07.png)

После подготовки данные выводятся на график, который показывает исходный набор данных синим цветом, прогнозы для набора обучающих данных зеленым цветом и прогнозы для набора невидимых тестовых данных красным цветом.
```python
labels = ['History', 'True Future', 'Model Prediction']
trainPredictPlot = numpy.empty_like(dataset)
trainPredictPlot[:, :] = numpy.nan
trainPredictPlot[look_back:len(trainPredict)+look_back, :] = trainPredict
# shift test predictions for plotting
testPredictPlot = numpy.empty_like(dataset)
testPredictPlot[:, :] = numpy.nan
testPredictPlot[len(trainPredict)+(look_back*2)+1:len(dataset)-1, :] = testPredict
# plot baseline and predictions
plt.plot(scaler.inverse_transform(dataset))
plt.plot(trainPredictPlot)
plt.plot(testPredictPlot)
plt.show()
```
**Результат:**<br>
![2023-01-08 (3)](https://user-images.githubusercontent.com/79097818/211195159-0f3423b6-55c9-435e-982f-4ff5b5889b03.png)
