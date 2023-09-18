# Замеры метрик производительности исходной модели

## Предварительная подготовка

Датасет был скачан со страницы: https://www.crowdhuman.org/. Данные были сконвертированы в yolo-формат с помощью скрипта crowdhuman_to_yolo.py: https://gist.github.com/adujardin/62653118466962264aa0c6339c3e9cf5 (команда для запуска: ```"python3 crowdhuman_to_yolo.py --dataset_path {FOLDER_WITH_ZIPS_AND_ANNOTATIONS}"```).

Веса модели были скачаны со страницы репозитория yolov5-crowdhuman: https://github.com/deepakcrk/yolov5-crowdhuman/tree/master.

Затем внутри склонированного репозитория yolov5-crowdhuman в конфигурационном файле с описанием датасета (```./data/crowdhuman.yaml```) пути до файлов ```train.txt```, ```val.txt``` и ```test.txt``` были изменены на актуальные.

## Запуск замера метрик производительности

Внутри склонированного репозитория yolov5-crowdhuman была запущена следующая команда:

```python3 test.py --weights {MODEL_WEIGHTS_PATH} --data ./data/crowdhuman.yaml```

В результате запуска были замерены метрики качества на валидационной части датасета: precision, recall, mAP общие и для каждого из классов в отдельности, а также замеры скорости работы модели на инференсе. Скриншот с полученными результатами (на cpu) сохранён в этой папке: ```hw1_screen.png```.

Также данные результаты будут добавлены в общую таблицу.