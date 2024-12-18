# Отчет

## Итоговый отчет о проделанной работе

## Разработка Telegram-бота для обнаружения и блокировки нежелательного контента

# ChatWhispG
# Команда:
**Крамарев Игорь Юрьевич МКИС33**
**Кублицкий Данил Дмитриевич МКИС33**
**Беликов Илья Денисович МКИС33**

ChatWhispG — это Telegram-бот, созданный для обнаружения и блокировки нежелательного контента, включая нецензурную лексику, рекламу и предложения о нелегальной продукции. Проект использует технологии машинного обучения для классификации текстовых сообщений и предоставляет инструменты для управления системой через панель администратора.

## Основные возможности

1. **Анализ текстового контента:**
   - Автоматическое обнаружение нецензурной лексики, рекламы и других типов нежелательного контента в сообщениях.
3. **Настраиваемые фильтры:**
   - Возможность включения/отключения фильтров для различных типов контента (например, нецензурной лексики или рекламы).
4. **Панель администратора:**
   - Удобный интерфейс для управления фильтрацией и просмотра статистики обработки сообщений.
5. **Отслеживание статистики:**
   - Запись данных о работе фильтров и обработке сообщений для последующего анализа и оптимизации.

## Мои обязанности

- **Выбор архитектуры модели машинного обучения:**
  - Анализ существующих решений (BERT, RoBERTa, XLNet, RNN) и выбор наиболее подходящей модели для задачи.
- **Сбор и обработка данных:**
  - Подготовка наборов данных для обучения модели, включая нейтральные тексты, тексты с нецензурной лексикой и рекламные тексты.
- **Обучение модели:**
  - Настройка гиперпараметров, таких как скорость обучения, размер мини-выборки и количество эпох.
  - Запуск процесса обучения с помощью скрипта `train.py`.
- **Тестирование модели:**
  - Проведение анализа эффективности модели на основе метрик точности, полноты и F1.
- **Создание документации:**
  - Разработка инструкций для других разработчиков, включая описание структуры проекта, используемых библиотек и настроек модели.
- **Оптимизация системы:**
  - Усовершенствование модели и фильтров на основе результатов тестирования.

# Этапы работы

## Сбор данных
- **Данные были собраны из различных открытых источников, включая форумы, социальные сети и базы данных текстов.**
- **Для повышения качества модели использовались тексты с нейтральным содержанием, ненормативной лексикой и рекламой.**

## Очистка данных
- **Удаление лишних символов: Ликвидация пробелов, HTML-тегов и других артефактов.**
- **Использование инструментов: Регулярные выражения и библиотека BeautifulSoup для парсинга текста.**

## Структурирование данных
- **Формат данных в датасетах:**
  - neutral.json — тексты с нейтральным содержанием.
  - profanity.json — тексты с ненормативной лексикой.
  - ads.json — рекламные тексты.
- **Формат строки в файлах: ID ::: Категория ::: Текст.**

## Установка и настройка

1. **Клонирование репозитория:**

   ```bash
   git clone https://github.com/yourusername/ChatWhispG.git
   cd ChatWhispG
   ```

2. **Настройка виртуального окружения:**

   ```bash
   python3 -m venv venv
   source venv/bin/activate   # Для Windows: venv\Scripts\activate
   ```

3. **Установка зависимостей:**

   ```bash
   pip install -r requirements.txt
   ```

4. **Настройка конфигурации:**

   - Переименуйте файл `config.example.py` в `config.py`.
   - Внесите изменения в `config.py`, указав:
     - `BOT_TOKEN`: токен вашего Telegram-бота.
     - `ADMINS`: список ID пользователей с правами администратора.
     - `ALLOWED_CHATS`: список ID чатов, которым разрешено взаимодействие с ботом.
     - `FILTER_PROFANITY`, `FILTER_ADVERTISING`: логические флаги для активации фильтров.

5. **Подготовка данных для обучения:**

   - Разместите файлы данных в папке `dataset/ru/`:
     - `neutral.json`: нейтральные тексты.
     - `profanity.json`: тексты с нецензурной лексикой.
     - `ads.json`: рекламные тексты.

6. **Обучение модели:**

   ```bash
   python train.py
   ```

7. **Запуск бота:**

   ```bash
   python main.py
   ```
## Тестирование бота
![photo_2024-12-17_20-23-22](https://github.com/user-attachments/assets/0e5ef5e4-3aeb-46eb-b3b0-eaff975c3671)
![Screenshot_6](https://github.com/user-attachments/assets/daedd068-f25f-404e-be10-203b898af9f6)

## Структура проекта

```
ChatWhispG/
├── main.py            # Основной скрипт для запуска бота
├── admin.py           # Логика панели администратора
├── train.py           # Скрипт для обучения модели
├── config.py          # Файл конфигурации
├── requirements.txt   # Зависимости Python
├── dataset/           # Папка с наборами данных
│   ├── ru/            # Наборы данных на русском языке
│       ├── neutral.json
│       ├── profanity.json
│       ├── ads.json
├── models/            # Папка для хранения обученных моделей
└── README.md          # Документация
```

## Зависимости

- **aiogram:** Фреймворк для работы с Telegram API.
- **tensorflow:** Библиотека для реализации машинного обучения.
- **numpy:** Для работы с многомерными массивами данных.
- **pandas:** Для обработки и анализа данных.
- **matplotlib:** Для визуализации данных.
- **sqlite3:** Для управления базой данных.
