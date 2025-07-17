Add New Features

Support for merged cells in HTML visualization.
Option to export the visualization as a PDF.
Interactive cell tooltips with full formatting info.
Toggle to show/hide comments, headers, or tables.
Optimize

Speed up border analysis for large sheets.
Reduce memory usage by streaming HTML output.
Cache border styles for repeated use.
Refactor

Split large methods into smaller, testable functions.
Move CSS generation to a separate module.
Add type hints and docstrings for all methods.
Switch to Another Module

Review and improve clustering logic.
Audit and refactor exporters or detectors for code quality.
Enhance CLI usability and error handling.

---
Перехожу к задачам по другим модулям: кластеризация, экспортеры, CLI.

**1. Кластеризация**
- Основная логика кластеризации реализована в:
  - clustering_analyzer.py
  - table_analyzer.py
  - cluster_detector.py
  - final_correct_detector.py (старый детектор, используется для сравнения)
- Класс `ClusteringExcelProcessor` (в clustering_processor.py) — точка входа для кластеризации через CLI.
- Для тестов и отладки: `tests/integration/test_clustering_app.py`, `debug_clustering_params.py`, test_hybrid_algorithm.py.

**2. Экспортеры**
- Экспорт данных реализован в:
  - enhanced_exporter.py
  - exporters.py
  - Форматы: json_exporter.py, `markdown_exporter.py`, `full_cell_exporter.py`, `method_comparison_exporter.py`
- Для восстановления экспорта в markdown/html/отчёты — используйте старую архитектуру из main_clustering.py или доработайте `ClusteringExcelProcessor`.

**3. CLI**
- Основной интерфейс: main.py (точка входа), использует `ClusteringExcelProcessor`.
- Для расширения CLI:
  - excel_analyzer.py
  - file_selector.py
  - clustering_processor.py
- Валидация и обработка ошибок: error_handling.py, validation.py
- Для запуска и проверки окружения: environment_guardian.py

**Рекомендации по дальнейшей работе:**
- Проверьте корректность импортов и совместимость между модулями.
- Для расширения экспорта восстановите старую логику из main_clustering.py или добавьте новые форматы в `ClusteringExcelProcessor`.
- Для CLI убедитесь, что все команды и обработка ошибок работают через декораторы и контекстные менеджеры из error_handling.py.
- Запустите интеграционные тесты для проверки кластеризации и экспорта.

Если нужна конкретная инструкция или правка — уточните, какой модуль или функцию доработать.

---

Для проверки абсолютных импортов и совместимости между модулями в вашем проекте нужно выполнить следующие шаги:

1. **Проверить все импорты**  
   - Убедиться, что все импорты в файлах используют абсолютные пути, например:  
     ```python
     from src.excel_converter.cli.clustering_processor import ClusteringExcelProcessor
     ```
     вместо относительных (`from .utils import ...`).

2. **Проверить корректность импортов после реорганизации**  
   - Если структура проекта изменилась, обновить все импорты, чтобы они соответствовали новым путям.
   - Особое внимание уделить импортам из src, например:  
     - `from src.utils import ...`
     - `from src.markdown_exporter import ...`
     - `from src.excel_converter.cli import ...`

3. **Проверить совместимость между модулями**  
   - Убедиться, что все зависимости между модулями корректны и нет циклических импортов.
   - Запустить интеграционные тесты (`tests/integration/test_clustering_app.py`) для проверки работоспособности связки кластеризации и экспорта.

4. **Проверить корректность импортов в точках входа**  
   - В файле main.py и других CLI-скриптах убедиться, что все импорты абсолютные и соответствуют структуре проекта.

5. **Проверить импорты в экспортерах и анализаторах**  
   - В файлах `enhanced_exporter.py`, `exporters.py`, `json_exporter.py`, `markdown_exporter.py`, `full_cell_exporter.py`, `method_comparison_exporter.py` убедиться, что импорты абсолютные.

6. **Проверить импорты в тестах**  
   - В тестах использовать абсолютные импорты, чтобы избежать ошибок при запуске из разных директорий.

### Пример корректного абсолютного импорта:
```python
from src.excel_converter.cli.clustering_processor import ClusteringExcelProcessor
```

### Дальнейшие действия
- Если найдены относительные импорты — заменить их на абсолютные.
- Если есть ошибки импорта — исправить пути.
- После правок запустить тесты для проверки совместимости.

Если требуется автоматизированная проверка или конкретные примеры исправления импортов — уточните, и я предложу скрипт или список изменений.