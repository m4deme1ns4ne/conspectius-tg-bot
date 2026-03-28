# Conspectius Telegram Bot (conspectius-tg-bot)

**conspectius-tg-bot** — это клиентский Telegram-интерфейс для системы Conspectius.

Проект реализует концепцию «легкого клиента»: бот отвечает исключительно за удобное взаимодействие с пользователем (прием аудиофайлов и выдачу готового результата), делегируя тяжелую ML-обработку (транскрибацию и генерацию академических конспектов) ядру системы. Бот помогает студентам и исследователям превращать многочасовые аудиолекции в подробные, структурированные конспекты прямо в мессенджере.

## Функционал

  * Прием аудиолекций в форматах аудиофайлов.
  * Обработка пользовательских настроек.
  * Отправка пользователю итогового академического конспекта.

## Установка

Для локальной разработки инструмента используется [Poetry](https://python-poetry.org/). Убедитесь, что у вас установлен Python версии 3.12 или выше.

Клонируйте репозиторий бота:

```bash
git clone https://github.com/m4deme1ns4ne/conspectius-tg-bot.git
cd conspectius-tg-bot
```

*(Примечание: Исходный код веб-интерфейса находится в отдельном репозитории `conspectius-site`, а ядро обработки выделяется в `conspectius-engine`)*.

## Конфигурация

Создайте файл `.env` в корневой директории проекта и добавьте необходимые переменные окружения для подключения API и базы данных:

```env
# Настройки Telegram
TELEGRAM_BOT_TOKEN="your_telegram_bot_token"

# Настройки внешних API (для текущей интеграции)
OPENAI_API_KEY="your_openai_api_key"
ASSEMBLY_AI_API="your_assembly_ai_token"

# Сетевые настройки
PROXY="your_proxy_url" # (опционально)
URL="your_URL"         # (для сервера загрузчика, опционально)

# База данных (MySQL)
MYSQL_ROOT_PASSWORD="your_MYSQL_ROOT_PASSWORD"
MYSQL_DATABASE="your_MYSQL_DATABASE"
MYSQL_USER="your_MYSQL_USER"
MYSQL_PASSWORD="your_MYSQL_PASSWORD"
MYSQL_PORT="your_MYSQL_PORT"
MYSQL_HOST="your_MYSQL_HOST"
```

## Запуск

Выполните следующую команду в корне проекта:

```bash
docker compose up --build -d
```

После успешного запуска контейнера бот готов к работе. Отправьте ему аудиосообщение в Telegram, и он автоматически инициирует процесс создания конспекта.

## Технологии

Стек технологий клиентской части (Telegram Bot):

  - **Python 3.12**
  - **Aiogram**
  - **Poetry**
  - **Docker & Docker Compose**
