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
2. Найдите минимальный, максимальный и средний размеры изображений.
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

---

## Задание 4: Pipeline аугментаций (20 баллов)

1. Реализуйте класс AugmentationPipeline с методами:
   - add_augmentation(name, aug)
   - remove_augmentation(name)
   - apply(image)
   - get_augmentations()
2. Создайте несколько конфигураций (light, medium, heavy).
3. Примените каждую конфигурацию к train и сохраните результаты.

---

## Задание 5: Эксперимент с размерами (10 баллов)

1. Проведите эксперимент с разными размерами изображений (например, 64x64, 128x128, 224x224, 512x512).
2. Для каждого размера измерьте время загрузки и применения аугментаций к 100 изображениям, а также потребление памяти.
3. Постройте графики зависимости времени и памяти от размера.

---

## Задание 6: Дообучение предобученных моделей (25 баллов)

1. Возьмите одну из предобученных моделей torchvision (например, resnet18, efficientnet_b0, mobilenet_v3_small).
2. Замените последний слой на количество классов вашего датасета.
3. Дообучите модель на train, проверьте качество на val.
4. Визуализируйте процесс обучения (loss/accuracy).


---
