# AI: Классификация и сегментация изображений графиков и чертежей

## Описание проекта

Данный проект предназначен для автоматической классификации изображений (график, чертёж, другое), определения типа графика, а также сегментации изображений с использованием современных методов машинного обучения и компьютерного зрения.

Проект включает:
- Генерацию и обработку синтетических и реальных данных
- Сегментацию изображений (выделение объектов)
- Обучение и тестирование различных моделей (CNN, ViT, SVM, Naive Bayes, LSTM)
- Оценку качества моделей
- Использование обученных моделей для предсказания классов новых изображений

## Структура проекта

- `dataset_create.py` — генерация синтетических графиков различных типов
- `desmos_create_dataset.py` — генерация графиков с помощью Desmos
- `dataset_new/` — исходные изображения для сегментации (по классам)
- `processed_dataset/` — сегментированные изображения для обучения моделей
- `test/` — тестовые изображения по классам
- `processed_test/` — сегментированные тестовые изображения
- `testing_validation_dataset/` — изображения для финального тестирования (подпапки: `chertezh`, `graphiks`, `other`)
- `model/` — обученные модели (CNN, ViT и др.)
- `CNN_model.py`, `VIT_model.py`, `defining_image_model.py` — обучение и тестирование моделей
- `opencv_processing.py`, `skimage_segmentation.py`, `watershed.py` — различные методы сегментации
- `check_model.py`, `test_model.py` — тестирование и валидация моделей
- `код препрода/` — альтернативные и вспомогательные скрипты (SVM, Naive Bayes, LSTM, метрики, преобразования)

## Используемые датасеты

- [Датасет для определения типа графика (обучение нейросети)](https://disk.yandex.ru/d/ZbxfknsLxiIabw)
- [Датасет для сегментации изображений](https://disk.yandex.ru/d/1x9NszKY3BQ18A)
- [Датасет для определения вида изображения (график, чертёж, другое)](https://disk.yandex.ru/d/LmFx0h4kp5nVfg)

## Требования

- Python 3.8+
- tensorflow, keras, scikit-learn, numpy, matplotlib, opencv-python, tqdm, Pillow, PyDesmos, pyautogui и др.

Установить зависимости:
```bash
pip install tensorflow keras scikit-learn numpy matplotlib opencv-python tqdm Pillow PyDesmos pyautogui
```

## Основные этапы работы

1. **Генерация данных**
   - `dataset_create.py`, `desmos_create_dataset.py` — создание синтетических графиков
2. **Сегментация изображений**
   - `opencv_processing.py`, `skimage_segmentation.py`, `watershed.py` — выделение объектов на изображениях
3. **Обработка и подготовка данных**
   - Преобразование изображений к нужному формату, размеру, каналам (`Validaz3RGB.py`, `valid.py`)
4. **Обучение моделей**
   - `CNN_model.py`, `VIT_model.py`, `LSTM_model.py`, `defining_image_model.py` — обучение моделей на подготовленных данных
5. **Тестирование и оценка**
   - `test_model.py`, `check_model.py` — тестирование, расчет метрик (accuracy, precision, recall, F1, ROC AUC)


## Примеры запуска

### Обучение модели
```bash
python CNN_model.py
python VIT_model.py
python LSTM_model.py
```

### Сегментация изображений
```bash
python opencv_processing.py
```

### Тестирование модели
```bash
python test_model.py
```



## Документация и описание файлов

- `CNN_model.py`, `VIT_model.py`, `defining_image_model.py` — обучение моделей (описание архитектуры внутри файлов)
- `test_model.py`, `check_model.py` — тестирование и расчет метрик
- `opencv_processing.py`, `skimage_segmentation.py`, `watershed.py` — методы сегментации
- `код препрода/` — альтернативные модели (SVM, Naive Bayes, LSTM), расчет метрик, преобразование изображений
- `dataset_create.py`, `desmos_create_dataset.py` — генерация синтетических данных

### Описание моделей
- **CNN** — сверточная нейросеть для классификации изображений по типу графика
- **ViT/MobileNetV2** — transfer learning для классификации изображений
- **LSTM** —   разновидность архитектуры рекуррентных нейронных сетей (RNN). Работает по принципу долгая краткосрочная память

