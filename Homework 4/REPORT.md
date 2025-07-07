# Задание 1: Сравнение CNN и полносвязных сетей (40 баллов)
## 1.1 Сравнение на MNIST (20 баллов)

---
Сравните производительность на MNIST:
>
- Полносвязная сеть (3-4 слоя)
- Простая CNN (2-3 conv слоя)
- CNN с Residual Block


Для начала я скопировал с гитхаба код на обучение моделей *(run_epoch, train_model, Dataset|Dataloader)*, и взял основы классов простых нейронных сетей (после чуть видоизменил и добавил свой класс Linear), а после обучил модели

Для каждого варианта:

- Обучите модель с одинаковыми гиперпараметрами
>Обучил

- Сравните точность на train и test множествах
>Скопировал функции plot_training_history, визуализировал метрики, самой точной оказалась CNN ~0.993+ test accr, далее ResNet, а FCN начала переобучаться после 7 итерации (видно, что tesst accr начал падать)
>![alt text](https://github.com/Chernii-Gospodin/PytorchLearning/blob/main/Homework%204/images/ResNet%20metrics.png)
>![alt text](https://github.com/Chernii-Gospodin/PytorchLearning/blob/main/Homework%204/images/FCN%20metrics.png)
>![alt text](https://github.com/Chernii-Gospodin/PytorchLearning/blob/main/Homework%204/images/CNN%20metrics.png)
>
- Измерьте время обучения и инференса
> Вывел время инференс - самая быстрой оказалась CNN модель, после FCN, и самая медленная ResNet
- Визуализируйте кривые обучения
> Визуализировал с помощью AUC-ROC и везде мне показывались метрики   > 0.99+, что удивило меня
> ![alt text](https://github.com/Chernii-Gospodin/PytorchLearning/blob/main/Homework%204/images/CNN%20AUC-ROC.png)
- Проанализируйте количество параметров
> Получил интересные данные: самая лучшая модель - CNN, и там 50186 параметров. Дальше идет ResNet - 163466, после FC - 70090. То есть CNN оказалась легче и гибче


---

## 1.2 Сравнение на CIFAR-10 (MNIST) (20 баллов)
 Сравните производительность на CIFAR-10 *(к сожалению, **без Cifar10**, так как у меня не грузит ни putorch, ни файл с сайта. Даже с VPN)*:
 
 >
- Полносвязная сеть (глубокая)
>> Создал с 5-ю Linear(out => 1024, 512, 512, 256, num_classes).
>> Структура: Linear -> ReLU -> Dropout(0.5/0.3/0/25), *3* раза подряд
>
- CNN с Residual блоками
>> Создал с 3-мя блоками
>
- CNN с регуляризацией и Residual блоками
 
 Для каждого варианта:
 
 - Обучите модель с одинаковыми гиперпараметрами
>Обучил

 - Сравните точность и время обучения
 > Сохранил и визуализировал метрики. У DeepFCN график потерь и accuracy гладкий, но вот что удивило - Test accr (~0.98+)  больше Train accr. У ResNetCNN график получился очень ломанный (скорее всего из-за отсутствия + обучался *ОЧЕНЬ* долго (37 минут 10 эпох), но результыт вполне сносный - в пике test accr 0.99+, что очень радует.
> 
> ResNetCNN
 > ![alt text](https://github.com/Chernii-Gospodin/PytorchLearning/blob/main/Homework%204/images/ResNetCNN%20losses-accr.png)
> DeepFCN
 > ![alt text](https://github.com/Chernii-Gospodin/PytorchLearning/blob/main/Homework%204/images/DeepFCN%20losses-accr.png)
 
 - Проанализируйте переобучение
 > Переобучения не заметил (скорее всего из-за недостатка эпох), но   до него будет тяжело дойти из-за огромного кол-ва параметров
 
 - Визуализируйте confusion matrix
>![alt text](https://github.com/Chernii-Gospodin/PytorchLearning/blob/main/Homework%204/images/DeepFCN%20matrix.png)
> ![alt text](https://github.com/Chernii-Gospodin/PytorchLearning/blob/main/Homework%204/images/ResNetCNN%20matrix.png)

 - Исследуйте градиенты (gradient flow)
> ![alt text](https://github.com/Chernii-Gospodin/PytorchLearning/blob/main/Homework%204/images/grad_flow_deepfcn.png)
> ![alt text](https://github.com/Chernii-Gospodin/PytorchLearning/blob/main/Homework%204/images/grad_flow_resnetcnn.png)


## В этой части работе я понял, что CNN - универсальный элемент нейронной сети, обладает гибкостью, мощностью и легкостью. Мега машина в мире нейронных сетей, применяется практически везде (Faster R-CNN, ResNet50 + R-CNN). Также отточил навык считывания и понимания метрик и их графиков. Повторил, как создавать каркас для NN-сетей 

---

# Задание 2: Анализ архитектур CNN (30 баллов)
## 2.1 Влияние размера ядра свертки (15 баллов)


 Исследуйте влияние размера ядра свертки:
- 3x3 ядра
 - 5x5 ядра
 - 7x7 ядра
 - Комбинация разных размеров (1x1 + 3x3)
 
Для каждого варианта:
- Поддерживайте одинаковое количество параметров
- Сравните точность и время обучения
> Модели обучались примерно одинаково (по 3 минуты каждая, 10 эпох). У всех test_accr больше, чем train_accr + метрики у них одинаковые, хоть и разные графики
> 
## ***UPD: Увидел, что именно эти модели я не правильно спроектировал из-за  опечатки (невнимательность), вывод не действителен.***
> 
> ![alt text](https://github.com/Chernii-Gospodin/PytorchLearning/blob/main/Homework%204/images/fatal_error1.jpg)
> ![alt text](https://github.com/Chernii-Gospodin/PytorchLearning/blob/main/Homework%204/images/fatal_error2.jpg)
> ![alt text](https://github.com/Chernii-Gospodin/PytorchLearning/blob/main/Homework%204/images/fatal_error3.jpg)

 - Проанализируйте рецептивные поля
 > При одинаковых размерах ядер у слоев размер рецептивного слоя увеличивается на 2 в каждом измерении (высота * ширина)
>  То есть первый слой считывает 3x3 область пикселей, второй слой смотрит своим ядром (3X3) на карту первого слоя -> отсюда смотрит на область 5x5 изображения
>Я создал в каждом по 3 слоя.
>> Ядро\
>>  3х3| 1 → 3 → 5 → 6 → 10	_10x10_\
    5x5|	1 → 5 → 9 → 10 → 18	_18x18_\
    7x7|	1 → 7 → 13 → 14 → 26	_26x26_\
    combine (1+3+5)|	1 → 1 → 3 → 4 → 12	_12x12_\
>
>Имеем, что при kernel_size = 7x7 каждый пикслель в feature map на 3 слое обладает информации о 26x26 пикселей (при 28x28 MNIST - считай все изображение)
> 
 - Визуализируйте активации первого слоя
> Вот пример для цифры 7 (первый слой Deep CNN, генерируется 32 feature maps; показано 16)
>
> ![alt text](https://github.com/Chernii-Gospodin/PytorchLearning/blob/main/Homework%204/images/layer0.png)


## В этой части я убедился, что чем глубже сеть, тем лучше ее результаты (но также возрастает время на ее обучение). Полностью разобрался, как работают рецептивные слои и визуализируются карты признаков
---
# Задание 3: Кастомные слои и эксперименты (30 баллов)
##3.1 Реализация кастомных слоев (15 баллов)





