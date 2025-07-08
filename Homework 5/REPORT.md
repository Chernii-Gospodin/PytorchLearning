---
## Задание 1: Стандартные аугментации torchvision (15 баллов)

1) Создайте пайплайн стандартных аугментаций torchvision (например, RandomHorizontalFlip, RandomCrop, ColorJitter, RandomRotation, RandomGrayscale).
2) Примените аугментации к 5 изображениям из разных классов (папка train).
3) Визуализируйте 
- Оригинал
- Результат применения каждой аугментации отдельно
- Результат применения всех аугментаций вместе
   ![alt text](https://github.com/Chernii-Gospodin/PytorchLearning/blob/main/Homework%205/plots/Fubuki_all.png)
   ![alt text](https://github.com/Chernii-Gospodin/PytorchLearning/blob/main/Homework%205/plots/Fubuki_each.png)
   ![alt text](https://github.com/Chernii-Gospodin/PytorchLearning/blob/main/Homework%205/plots/Garo_all.png)
   ![alt text](https://github.com/Chernii-Gospodin/PytorchLearning/blob/main/Homework%205/plots/Garo_each.png)
   ![alt text](https://github.com/Chernii-Gospodin/PytorchLearning/blob/main/Homework%205/plots/Sonik_all.png)
   ![alt text](https://github.com/Chernii-Gospodin/PytorchLearning/blob/main/Homework%205/plots/Sonik_each.png)
   ![alt text](https://github.com/Chernii-Gospodin/PytorchLearning/blob/main/Homework%205/plots/Genos_all.png)
   ![alt text](https://github.com/Chernii-Gospodin/PytorchLearning/blob/main/Homework%205/plots/Genos_each.png)
   ![alt text](https://github.com/Chernii-Gospodin/PytorchLearning/blob/main/Homework%205/plots/Saitama_all.png)
   ![alt text](https://github.com/Chernii-Gospodin/PytorchLearning/blob/main/Homework%205/plots/Saitama_each.png)
   ![alt text](https://github.com/Chernii-Gospodin/PytorchLearning/blob/main/Homework%205/plots/Tatsumaki_all.png)
   ![alt text](https://github.com/Chernii-Gospodin/PytorchLearning/blob/main/Homework%205/plots/Tatsumaki_each.png)

Здесь представлены визуализации
---

## Задание 2: Кастомные аугментации (20 баллов)

1. Реализуйте минимум 3 кастомные аугментации (например, случайное размытие, случайная перспектива, случайная яркость/контрастность).
2. Примените их к изображениям из train.
3. Сравните визуально с готовыми аугментациями из extra_augs.py.

---

## Задание 3: Анализ датасета (10 баллов)

1. Подсчитайте количество изображений в каждом классе.
> 30*6 = 180 В TRAIN
>
> 100*6 = 100 В TEST

3. Найдите минимальный, максимальный и средний размеры изображений.
>
>**Тестовый датасет**
>Статистика размеров изображений:\
>Ширина: min=220, max=736, mean=547.7\
>Высота: min=220, max=1308, mean=631.0

>Количество изображений по классам:\
>Гароу: 100\
>Ширина: min=225, max=736, mean=533.1

>Генос: 100\
>Ширина: min=236, max=736, mean=546.3

>Сайтама: 100\
>Ширина: min=300, max=736, mean=549.3

>Соник: 100\
>Ширина: min=225, max=735, mean=531.8

>Татсумаки: 100\
>Ширина: min=250, max=736, mean=560.8

>Фубуки: 100\
>Ширина: min=220, max=736, mean=564.7
______________________________________
>
>Тренировочный датасет\
>Статистика размеров изображений:\
>Ширина: min=210, max=736, mean=538.9\
>Высота: min=240, max=1308, mean=623.6

>Количество изображений по классам:\
>Гароу: 30\
>Ширина: min=246, max=735, mean=538.4

>Генос: 30\
>Ширина: min=270, max=720, mean=550.2

>Сайтама: 30\
>Ширина: min=375, max=736, mean=559.3

>Соник: 30\
>Ширина: min=210, max=604, mean=525.9

>Татсумаки: 30\
>Ширина: min=267, max=736, mean=527.2

>Фубуки: 30\
>Ширина: min=286, max=736, mean=532.4

3. Визуализируйте распределение размеров и гистограмму по классам.

## Анализ тренировочного датасета

![alt text](https://github.com/Chernii-Gospodin/PytorchLearning/blob/main/Homework%205/plots/train_analisyz.png)

## Анализ тестового датасета

![alt text](https://github.com/Chernii-Gospodin/PytorchLearning/blob/main/Homework%205/plots/test_analisyz.png)
---

## Задание 4: Pipeline аугментаций (20 баллов)

1. Реализуйте класс AugmentationPipeline с методами:
   - add_augmentation(name, aug)
   - remove_augmentation(name)
   - apply(image)
   - get_augmentations()
2. Создайте несколько конфигураций (light, medium, heavy).
 > Все реализовал и создал
> 
4. Примените каждую конфигурацию к train и сохраните результаты.

## Примеры для некотрых изображений

![alt text](https://github.com/Chernii-Gospodin/PytorchLearning/blob/main/Homework%205/plots/Sonik_light1.png)
![alt text](https://github.com/Chernii-Gospodin/PytorchLearning/blob/main/Homework%205/plots/Sonik_light2.png)
![alt text](https://github.com/Chernii-Gospodin/PytorchLearning/blob/main/Homework%205/plots/Sonik_medium1.png)
![alt text](https://github.com/Chernii-Gospodin/PytorchLearning/blob/main/Homework%205/plots/Sonik_medium2.png)
![alt text](https://github.com/Chernii-Gospodin/PytorchLearning/blob/main/Homework%205/plots/Sonik_heavy2.png)
![alt text](https://github.com/Chernii-Gospodin/PytorchLearning/blob/main/Homework%205/plots/Saitama_heavy.png)
---

## Задание 5: Эксперимент с размерами (10 баллов)

1. Проведите эксперимент с разными размерами изображений (например, 64x64, 128x128, 224x224, 512x512).
2. Для каждого размера измерьте время загрузки и применения аугментаций к 100 изображениям, а также потребление памяти.
3. Постройте графики зависимости времени и памяти от размера.

У меня получились интересные результаты :
```
Size: (64, 64)
Time: 0.08 sec
Memory used: 0.13 MB
---
Size: (128, 128)
Time: 0.16 sec
Memory used: -0.73 MB
---
Size: (224, 224)
Time: 0.32 sec
Memory used: -1.42 MB
---
Size: (512, 512)
Time: 1.41 sec
Memory used: 3.51 MB
```
Очень серьезно будут нагружать мой компьютер большие изображения (примерно 800x800)  
с batch_size > 16

---

## Задание 6: Дообучение предобученных моделей (25 баллов)
*** У меня не грузились веса с из-за того, что я сижу на мобильных данных и VPN не работает, поэтому  обучал без предобученных данных)
1. Возьмите одну из предобученных  моделей torchvision (например, resnet18, efficientnet_b0, mobilenet_v3_small).
2. Замените последний слой на количество классов вашего датасета.
3. Дообучите модель на train, проверьте качество на val.
4. Визуализируйте процесс обучения (loss/accuracy).

### Получил не самые лучшие метрики

Первые 10 эпох
![IMAGE](https://github.com/Chernii-Gospodin/PytorchLearning/blob/main/Homework%205/plots/metrics_10_epoches.png)

Дообучение С 10 эпохи до 20 
![IMAGE](https://github.com/Chernii-Gospodin/PytorchLearning/blob/main/Homework%205/plots/metrics_from10to20_epoches.png)


Также из-за повышения кол-ва изображений на batche (в 3 раза благодаря аугментации) моя видеокарта не выдеражала (не хватило памяти в 4гб). Из-за этого скорость обучения за 10 эрох составляла [08:28<00:00, 50.81s/it].

При понижении batch_size=16 (то есть 48 изображений в итоговом batche) Скорость обучения увеличилась и составила на 30 эпох 100%[08:53<00:00, 17.77s/it]. Но это не помогло спасти от **Королевских** лоссов:

![IMAGE](https://github.com/Chernii-Gospodin/PytorchLearning/blob/main/Homework%205/plots/%D0%9A%D0%BE%D1%80%D0%BE%D0%BB%D0%B5%D0%B2%D1%81%D0%BA%D0%B8%D0%B5%20%D0%BB%D0%BE%D1%81%D1%81%D1%8B.png)


#  В целом, мне понравилась это тема. С помощью аугментаций можно разнообразить датасет, увеличив стойкость модели к немного аномальным данным, а также качетсво обучения (из-за большего размера итогового датасета)
---
