# Проект классификации изображений фруктов и овощей

Этот проект посвящен классификации изображений различных фруктов и овощей с использованием машинного обучения без применения TensorFlow. Датасет содержит 36 классов фруктов, каждая категория представлена отдельной папкой с изображениями.

## Обзор проекта

- **Алгоритм:** RandomForestClassifier
- **Извлечение признаков:** HOG (Гистограммы направленных градиентов)
- **Оценка модели:** Точность классификации и матрица ошибок
- **Датасет:** Датасет состоит из изображений, разделенных на 36 классов, метки которых соответствуют названиям папок.

## Визуализация датасета

### Количество изображений для каждой метки

![Количество меток](https://github.com/user-attachments/assets/a0e4611a-5ccb-481b-9a5b-42005882c699)


Этот график показывает количество изображений для каждого класса фруктов в датасете.

### Пример изображений для каждого класса

![Пример изображений](https://github.com/user-attachments/assets/7fe2dd41-0567-4fec-98c3-6455e98a8566)


На изображении выше представлены примеры по одному изображению для каждого класса фруктов.

## Оценка модели

После обучения модели Random Forest, её производительность была оценена с помощью матрицы ошибок. Она позволяет визуализировать, как модель справляется с классификацией каждого класса.

### Матрица ошибок

![Матрица ошибок](https://github.com/user-attachments/assets/c0d65179-fa10-408d-8cde-33a28b847415)


Матрица ошибок демонстрирует, насколько точно модель предсказывает каждый класс фруктов.

## Пример использования

```python
# Загрузка модели из файла
loaded_model = joblib.load(model_filename)

# Использование загруженной модели для предсказания
new_img_path = 'fruits\\validation\\onion\\Image_3.JPG'
predicted_fruit = predict_image(loaded_model, new_img_path)
print(f'Predicted fruit: {predicted_fruit}')
```

## Обучение и оценка модели

Процесс обучения включает следующие этапы:

1. Извлечение признаков HOG для каждого изображения в датасете.
2. Разделение данных на тренировочный, тестовый и валидационный наборы.
3. Обучение модели Random Forest с последующей проверкой её качества на тестовом и валидационном наборах.
4. Визуализация матрицы ошибок для оценки результатов.

## Результаты

Модель продемонстрировала высокую точность на тестовом наборе, что подтверждается матрицей ошибок, показанной выше. Применение HOG-признаков позволило эффективно различать изображения фруктов разных классов.
