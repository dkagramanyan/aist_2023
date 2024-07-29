# aist_2023
 
## Содержание репозитория

| Файл | Содержание |
|------|------------|
| [chars_crop.ipynb](notebooks/characters/chars_crop.ipynb) | выделение области с текстом с бланка (обрезание шапки бланка) |
| | обрезанные бланки сохраняются в отдельную папку |
| | .csv с метаданными о бланках объединяются в один |
| [chars_ocr.ipynb](notebooks/characters/chars_ocr.ipynb) | OCR - optical character recognition |
| | применение библиотеки *pytesseract* |
| | ??? |
| [digits_classication.ipynb](notebooks/grades/digits_classication.ipynb) | MNIST + CNN (keras) |
| | mnist.h5 -- веса модели |
| | ?? (предобработка изображений) |
| | с помощью модели обученной на MNIST распознавание оценок за работу |
| [docs_stats.ipynb](notebooks/grades/docs_stats.ipynb) | ?? (автоматизированное выставление оценки по количеству орфографических/пунктуационных ошибок) |
| [document_alignment.ipynb](notebooks/document_alignment.ipynb) | Выправление бланков |
| | |
| [fractal dimention.ipynb](notebooks/fractal%20dimention.ipynb) | Расчет фрактальных размеров |
| | |
| [grades.csv](data/grades.csv) | метаинформация (msk22+msk23+nov22?) о бланках |
| [grades_nn.ipynb](notebooks/grades/grades_nn.ipynb) | работа с оценками (кластеризация) |
| | UMAP, XGBoost, RandomForest |
| [mnist.h5](data/mnist.h5) | веса сверточной сети, обученной на мнисте |
| | см. *digit_classification.ipynb* |
| [space between words.ipynb](notebooks/space%20between%20words.ipynb) | бинарное изображение превращается во временной ряд |
| | расстояния между словами определяются как <br>расстояния между границами групп объектов (?) |
| [words detection.ipynb](notebooks/words%20detection.ipynb) | *rgb2smyk* -- перевод изображения из стандартной <br>кодировки RGB в CMYK (Cyan-Magenta-Yellow-Black) |
| | фильтр оцу (threshold_otsu) - рассчитывает "оптимальный" порог, максимизируя дисперсию между двумя классами пикселей, которые разделены порогом. Эквивалентно, этот порог минимизирует внутриклассовую дисперсию. |
| | ?? попытка выделить линии (или сам текст) |
| [words segmentation.ipynb](notebooks/words%20segmentation.ipynb) | получается три изображения с выделенным текстом (сегментация) |
| | binary_image -- серые пиксели в зависимости от порога (0) либо заменяются на черный, либо на белый (0 - 255); получаем белый текст + черный фон |
| | dilated_image -- "свертка" проходится по изображению (фильтр - прямоугольник) и расширяет границы текста (см ниже) |
| | colored_img -- значение каждого пикселя заменяется на цвет (трехмерное равномерное распределение) если метка связности ненулевая (Two pixels are connected when they are neighbors and have the same value. In 2D, they can be neighbors either in a 1- or 2-connected sense.<br>The value refers to the maximum number of orthogonal hops to consider a pixel/voxel a neighbor) |
| [words slant.ipynb](notebooks/words%20slant.ipynb) | words detection - выделение границ текста, цветные границы текста |
| | (in progress) - наклон текста по 8 направлениям |