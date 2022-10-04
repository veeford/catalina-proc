# Архитектура приложения
- Клиент (экзаменатор, экзаменуемый)
- Сервер (хранение данных в БД)
<!-- Вставить картинку со схемой архитектуры клиент-сервер-клиент -->
# Функционал приложения клиента
## Со стороны экзаменуемого
- Подключение к компьютеру экзаменатора по цифро-буквенному коду
- Показать/скрыть изображение с веб-камеры (заглушка при отсутствии камеры)
- Периодическая верификация человека по фотографии из БД (через промежутки времени случайной длины от 15 секунд до 5 минут)
- Показать/скрыть логирование нарушений
- Захват изображения с веб-камеры
  - Определение лица в видеопотоке (face detection)
  - Определение направления взгляда
  - Определение открытия/закрытия рта
- Логирование нарушений в реальном времени
- Запись сессий проведения экзамена (видеопоток, лог нарушений записываются в отдельные файлы)
- Отправка видеопотока и потока логирования на сервер (если вычислительных мощностей клиента не хватит)
## Со стороны экзаменатора
- Генерация цифро-буквенного кода для подключения экзаменуемого
# Функционал сервера
- Только если не будет хватать мощности клиента экзаменуемого:
  - Определение лица в видеопотоке (face detection)
  - Определение направления взгляда
  - Определение открытия/закрытия рта
- Хостинг базы данных
## Данные, хранящиеся в БД
- Зарегистрированные пользователи, данные о них
- Видеозаписи и логи сессий экзаменов
- Результаты (точность) текущей и предыдущих итераций обучения модели