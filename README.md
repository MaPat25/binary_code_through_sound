Идея проекта: Мы кодируем информацию в виде нулей-единиц, кодируем ноль и единицу разными частотами (пока что это 1, 1.5 кц). После чего преобразуем этот массив в звуковой файл, содержащий синусоиды, проигрываем его, а другим устройством записываем и декодируем. Для отображение зависимости амплитуды от частоты используем преобразование Фурье.
Пояснение, как проходит декодирование с помощью традиционных методов: делим на три класса: модулятор - создает массив (который синусоидальный звук), wav - отвечает за создания файла wav из массива и вообще для работы с wav, decoder - сам дешифровщик, как он работает:
1) Мы получаем на вход массив данных, который является звуковым файлом в котором кроме нужных синусоид содержится тишина (скорее всего шумы), поэтому мы выделяем оттуда сами синусоиды следующим образом:
1.1) "Грубое определение синусоид": смотрим, где на нужных частотах находится какая-то амплитуда (больше, чем рандомный шум) с помощью нормализации. 
1.2)Потом, максимизируя нужную функцию (с помощью деления "координатной оси" на части, см код для подробностей), находим уже точно.
1.x?)Сделать тоже самое, только с помощью машинного обучения?
2) Здесь все должно быть просто: если мы нормально определили, то только на одной из частот должен быть сигнал.
3) profit??
Добавлено предсказывание двух параметров с помощью нейросети, работает. Добавлено предсказывание места самого сигнала, работает не очень. Нужно собрать больше данных.
