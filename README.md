# Engineer-Technologist-Projects
# 1. Создание БД (SQLite) параметров литейного производства за 2016-2025 гг.
## СТРУКТУРА БАЗЫ ДАННЫХ
================================================================================

📊 ТАБЛИЦА: batch_matching
--------------------------------------------------

Столбцы:
  - Дата: TIMESTAMP NULL 
  - Отливка: TEXT NULL 
  - Номер_партии: REAL NULL 
  - Номер_разливки: REAL NULL 

📊 ТАБЛИЦА: batch_report
--------------------------------------------------

Столбцы:
  - Отливка: TEXT NULL 
  - Номенклатура: TEXT NULL 
  - Номер_партии: REAL NULL 
  - Количество_обрубка: REAL NULL 
  - Количество_дробеочистка: REAL NULL 
  - Количество_зачистка: REAL NULL 
  - Количество_упаковка: REAL NULL 

📊 ТАБЛИЦА: casting_calculation
--------------------------------------------------

Столбцы:
  - Дата: TIMESTAMP NULL 
  - Номер_расчета: REAL NULL 
  - Статус_в_работе: TEXT NULL 
  - Заказчик: TEXT NULL 
  - Отливка: TEXT NULL 
  - Масса_отливки: REAL NULL 
  - Марка_чугуна: TEXT NULL 
  - Толщина_стенки: REAL NULL 
  - Количество_отливок_в_форме: REAL NULL 
  - Металлоемкость_формы: REAL NULL 
  - Номер_модели: REAL NULL 
  - Время_заливки: REAL NULL 
  - Температура_заливки_мин: REAL NULL 
  - Температура_заливки_макс: REAL NULL 
  - Кол-во_модификатора_1: REAL NULL 
  - Кол-во_модификатора_2: REAL NULL 
  - Коэффициент_использования_формы: REAL NULL 

📊 ТАБЛИЦА: casting_processing
--------------------------------------------------

Столбцы:
  - Дата: TIMESTAMP NULL 
  - Номер_обработки: REAL NULL 
  - Отливка: TEXT NULL 
  - Номенклатура: TEXT NULL 
  - Номер_партии: REAL NULL 

📊 ТАБЛИЦА: castings_list
--------------------------------------------------

Столбцы:
  - Отливка: TEXT NULL 
  - Код_отливки: REAL NULL 
  - Марка_чугуна: TEXT NULL 
  - Номенклатура: TEXT NULL 

📊 ТАБЛИЦА: charge_materials
--------------------------------------------------
Первичный ключ: Номер_плавки

Столбцы:
  - Дата: TIMESTAMP NULL 
  - Номер_плавки: REAL NULL PRIMARY KEY
  - Отливка: TEXT NULL 
  - Возврат_собственного_производства_ВЧ: REAL NULL 
  - Возврат_собственного_производства_СЧ: REAL NULL 
  - Графит_измельченный: REAL NULL 
  - Графит_измельченный_А99: REAL NULL 
  - Графит_измельченный_Б97: REAL NULL 
  - Медь_М1: REAL NULL 
  - Стальной_лом_1А: REAL NULL 
  - УККС_19: REAL NULL 
  - Ферромарганец_ФМн78: REAL NULL 
  - Ферросилиций_ФС45: REAL NULL 
  - Ферросилиций_ФС75: REAL NULL 
  - Чугун_литейный_Л6: REAL NULL 
  - Чугун_передельный_ПА1: REAL NULL 
  - Чугун_передельный_ПЛ1: REAL NULL 
  - Чугунный_лом_17А: REAL NULL 

📊 ТАБЛИЦА: chemical_analysis
--------------------------------------------------
Первичный ключ: Номер_плавки

Столбцы:
  - Дата: TIMESTAMP NULL 
  - Номер_плавки: REAL NULL PRIMARY KEY
  - C: REAL NULL 
  - Cr: REAL NULL 
  - Mg: REAL NULL 
  - Mn: REAL NULL 
  - P: REAL NULL 
  - S: REAL NULL 
  - Si: REAL NULL 

📊 ТАБЛИЦА: finished_products
--------------------------------------------------

Столбцы:
  - Дата: TIMESTAMP NULL 
  - Номер_строки: REAL NULL 
  - Отливка: TEXT NULL 
  - Номенклатура: TEXT NULL 
  - Номер_партии: REAL NULL 
  - Номер_упаковки: REAL NULL 
  - Ответственный: TEXT NULL 
  - Количество_готовых_отливок: REAL NULL 

📊 ТАБЛИЦА: good_castings
--------------------------------------------------

Столбцы:
  - Номер_партии: REAL NULL 
  - Отливка: TEXT NULL 
  - Номенклатура: TEXT NULL 
  - Количество_годных_отливок: REAL NULL 

📊 ТАБЛИЦА: liquid_metal
--------------------------------------------------
Первичный ключ: Номер_плавки

Столбцы:
  - Дата: TIMESTAMP NULL 
  - Номер_плавки: REAL NULL PRIMARY KEY
  - Количество_жидкого_металла: REAL NULL 

📊 ТАБЛИЦА: melts_list
--------------------------------------------------
Первичный ключ: Номер_плавки

Столбцы:
  - Дата: TIMESTAMP NULL 
  - Номер_плавки: REAL NULL PRIMARY KEY
  - Марка_чугуна: TEXT NULL 
  - Ответственный: TEXT NULL 
  - Смена: TEXT NULL 
  - Отливка: TEXT NULL 
  - Номер_печи: REAL NULL 
  - Номер_расчета: REAL NULL 
  - Жидкий_металл_кг: REAL NULL 

📊 ТАБЛИЦА: mixer_materials
--------------------------------------------------
Первичный ключ: Номер_разливки

Столбцы:
  - Дата: TIMESTAMP NULL 
  - Номер_разливки: REAL NULL PRIMARY KEY
  - Время_замеса: REAL NULL 
  - Вода: REAL NULL 
  - Оборотная_смесь: REAL NULL 
  - Песок: REAL NULL 
  - Бентонит: REAL NULL 
  - Блескол: REAL NULL 
  - Количество_замесов: REAL NULL 

📊 ТАБЛИЦА: model_operations
--------------------------------------------------
Столбцы:
  - Номер_модели: INTEGER NULL
  - Дата: TIMESTAMP NULL
  - Заказчик: TEXT NULL
  - Отливка: TEXT NULL
  - Номер_расчета: INTEGER NULL
  - Вид_работ: TEXT NULL
  - Комментарий: TEXT NULL

📊 ТАБЛИЦА: pouring_list
--------------------------------------------------
Первичный ключ: Номер_разливки

Столбцы:
  - Дата: TIMESTAMP NULL 
  - Номер_разливки: REAL NULL PRIMARY KEY
  - Марка_чугуна: TEXT NULL 
  - Ответственный: TEXT NULL 
  - Номер_плавки: REAL NULL 

📊 ТАБЛИЦА: pouring_results
--------------------------------------------------

Столбцы:
  - Дата: TIMESTAMP NULL 
  - Номер_разливки: REAL NULL 
  - Номер_строки: REAL NULL 
  - Отливка: TEXT NULL 
  - Номер_расчета: REAL NULL 
  - Количество_форм: REAL NULL 
  - Количество_отливок: REAL NULL 

📊 ТАБЛИЦА: production_defects
--------------------------------------------------

Столбцы:
  - Номер_партии: REAL NULL 
  - Отливка: TEXT NULL 
  - Раковины: REAL NULL 
  - Зарез: REAL NULL 
  - Глухой_звук: REAL NULL 
  - Перекос: REAL NULL 
  - Нарост: REAL NULL 
  - Коробление: REAL NULL 
  - Вылом: REAL NULL 
  - Пригар: REAL NULL 
  - Спай: REAL NULL 
  - Утяжина: REAL NULL 
  - Недолив: REAL NULL 
  - Стержневой_залив: REAL NULL 
  - Обжим: REAL NULL 
  - Другое: REAL NULL 
  - Итог: REAL NULL 
  - Дата: TIMESTAMP NULL 

📊 ТАБЛИЦА: trimming_list
--------------------------------------------------

Столбцы:
  - Дата: TIMESTAMP NULL 
  - Номер_обработки: REAL NULL 
  - Отливка: TEXT NULL 

================================================================================
ИНДЕКСЫ
================================================================================
📈 idx_finished_products_batch (таблица: finished_products)
📈 idx_finished_products_package (таблица: finished_products)
📈 idx_pouring_results_pouring (таблица: pouring_results)
📈 idx_good_castings_batch (таблица: good_castings)
📈 idx_batch_report_batch (таблица: batch_report)
📈 idx_batch_matching_batch (таблица: batch_matching)
📈 idx_batch_matching_pouring (таблица: batch_matching)
📈 idx_casting_processing_batch (таблица: casting_processing)
📈 idx_production_defects_batch (таблица: production_defects)
📈 idx_casting_calculation_number (таблица: casting_calculation)

# 2. Проект A/B тестирования эффективности ремонта модельной оснастки в сторонней организации
## План

1. Подготовка данных при помощи SQL-запросов, очистка, проверка целостности

2. Исследовательский анализ (EDA)

3. Формулировка гипотез

- H0: Процент брака после ремонта ≥ процента брака до ремонта

- H1: Процент брака после ремонта < процента брака до ремонта (с порогом 5%)

4. Статистический анализ, тест Шапиро-Уилка, t-тест Уэлча, расчет p-value

5. Анализ практической значимости, интерпретация результатов

6. Формирование отчета, выводы и рекомендации

