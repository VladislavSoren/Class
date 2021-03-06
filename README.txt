Название проекта: 
Классификация физических упражнений по видео.

Новые возможности: 
Проект доработан и теперь помимо классификации возможен подсчет количества повторений на видео.

Нейронные сети входящие в проект:
- Предобученная Yolo3 (Object Detection Net) - получение координат Bounding box
- Предобученная ResNet (Post Estimation Net) - получение координат суставных узлов человека
- Классификатор (Обучался на данных после предикта Yolo3 и ResNet) - классификация по полученным координатам

Циклограмма работы проекта:
- В выпадющем окне пользователь выбирает файл классификатора
- В выпадющем окне пользователь выбирает директорию с видео упражнений
- Видео нарезаются на кадры и кадры сохраняются в автоматически созданную директорию
- Выбирается режим (при вводе "1" выбирается "классификация + подсчет", в других случаях "классификация")
- Yolo3 и ResNet формируют массивы координат
- По массивам координат классификатор делает предсказания
- Появляется таблица, где указан порядковые номера видео и соответствующие им распознанные типы упражнений
- Теперь данная таблица так же содержит количество повторений на видео
*- Всего возможны два режима работы (классификация) / (классификация + подсчет)

PipeLine:
1. сбор базы (210 видео) + написание ТЗ
2. аугментация базы
3. парсинг базы в DataSet с помощью предобученных НС
4. предобработка данных (нормализация)
5. создание прототипа классификатора (НС)
6. создание финального классификатора с высокой точностью распознавания (более 95%)
7. проверка работы классификатора в тандеме с предобученными НС
8. разворачивание проекта в PyCharm (все предыдущие этапы производились в Colab)
9. создание графического интерфейса с помощью Tkinter.
10. Добавление режима подсчета количества повторений упражнения на видео
