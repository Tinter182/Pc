# OsintVisualizer - Project Structure

/osint_visualizer
├── main.py                 # Точка входа в приложение
├── requirements.txt        # Зависимости
├── config.py             # Конфигурация и настройки
├── core
│   ├── __init__.py
│   ├── window.py         # Основное окно приложения (GUI)
│   ├── graph_widget.py   # Виджет графа (Vis.js через QWebEngine)
│   ├── plugin_manager.py # Менеджер загрузки плагинов
│   └── translator.py     # Система локализации (RU/EN)
├── plugins
│   ├── __init__.py
│   └── base_plugin.py    # Базовый плагин (поиск по API, никнеймам)
├── exports
│   ├── __init__.py
│   └── telegram_export.py # Экспорт в TXT со спойлерами
├── assets
│   ├── styles.qss        # Стили CSS для PyQt
│   └── translations.json # Словарь переводов
└── utils
    ├── __init__.py
    └── key_checker.py    # Проверка ключа через GitHub Raw

## Описание компонентов:
1. **main.py**: Инициализация приложения, проверка ключа, запуск окна.
2. **core/window.py**: Верстка интерфейса (Sidebar, Search, Grid, Graph).
3. **core/graph_widget.py**: Обертка над HTML/JS с библиотекой Vis.js для отрисовки графа.
4. **core/plugin_manager.py**: Сканирование папки plugins, динамический импорт классов.
5. **plugins/base_plugin.py**: Пример плагина, реализующего поиск по BreachDirectory, VirusTotal (заглушки), Sherlock.
6. **exports/telegram_export.py**: Форматирование вывода, замена телефонов на спойлеры `||+7...||`.
7. **utils/key_checker.py**: Логика запроса к raw.githubusercontent.com.
