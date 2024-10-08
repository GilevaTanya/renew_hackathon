# Хакатон компании Ренью
♻️ Заказчик: Компания Ренью.

📑 Цель проекта: разработать модель для трекинга объектов на конвейерной ленте мусороперерабатывающего завода. 
   - Задача проекта:  Обучить трекер для отслеживания движущихся объектов (пластиковые бутылки разных типов) на ленте конвейера мусороперерабатывающего завода. 

📌 Сроки проекта: 19/08/24 - 09/09/24.

💻 Стек технологий: cv2, ultralytics, motmetrics, YOLO8, BoT-SORT, ByteTrack, SORT, DeepSORT.

## 📝 Описание проекта:
На мусороперерабатывающем заводе над конвейерной лентой установлена камера, которая фиксирует движение пластикового мусора. Данные в потоке передаются детектору и трекеру, которые определяют тип мусора и координаты bounding box.

Необходимо улучшить работу трекера:
- получить более точных координат bounding box;
- обеспечить устойчивость прослеживания объекта без смены ID;

📌 Требования заказчика:
* в течении 2х недель разработать решение для отслеживания объектов на ленте конвейера
* скорость обработки должна быть не более 100мс на кадр
* добиться наилучшего значения метрики MOTA
* подготовить отчет о работе.

⚒️ Работа велась в команде DS:
- [Альбина](https://t.me/AlbinaUsaeva) 
- [Татьяна](https://t.me/Tanya_GileT) 
- [Павел](https://t.me/keyboardnorth) 

## ✅ Результаты
Было протестировано 4 трекера. На 9000 фреймах лучшая метрика MOTA оказалась у DeepSORT:

|  Трекер   | MOTA  |
|:---------|:------|
|  DeepSORT | 0.955 |
| BoTSORT   | 0.924 |
| SORT      | 0.874 |
| ByteTrack | 0.519 |


Пример работы трекера DeepSORT:
![](https://github.com/usaeva-a/renew_hackathon/blob/0245a033d1c6dbdf7176b266f00f1dc69487c217/pics/example.gif)

## Структура репозитория
- В папке [test_of_trackers](test_of_trackers) собраны результаты тестирования всех использованных трекеров.
- В папке [app/deepsort](app/deepsort) представлен скрипт для трекера deepsort, показавшего наилучшую метрику.
