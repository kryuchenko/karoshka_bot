# Kartoshka Bot (Бот-Картошка) 🥔

## О боте

Kartoshka Bot — это дружелюбный Telegram-бот для модерации и публикации мемов в вашем чате. Он создан, чтобы сделать процесс публикации мемов простым, безопасным и веселым!

Бот поддерживает два режима работы:

- **Обычный режим (Единоличный Узурпатор)**: решения о публикации мемов принимает единоличный модератор.
- **Криптоселектархическая олигархия**: решения принимаются коллективно группой тайных модераторов (криптоселектархов), и для публикации или отклонения мема требуется определённое количество голосов.

## Основные возможности

- 📝 Возможность публикации текстовых, фото, видео и GIF-мемов
- 🎭 Два режима публикации через удобные кнопки:
  - 👤 От своего имени (с указанием автора)
  - 🥔 Анонимно (от имени "Картошки")
- 👥 Система модерации контента:
  - **Обычный режим**: модерация осуществляется единоличным модератором
  - **Криптоселектархическая олигархия**: решения принимаются коллективно группой криптоселектархов, и для одобрения или отклонения мема требуется набрать определённое количество голосов
- ✅ Кнопки модерации для редакторов: Одобрить / Отклонить
- ✨ Автоматическое уведомление авторов о статусе их публикаций
- 📢 Динамическое приветственное сообщение, которое меняется в зависимости от текущего режима бота

## Как использовать

1. Начните диалог с ботом командой `/start`
2. Выберите режим публикации, нажав одну из кнопок:
   - 👤 "От своего имени (ваше имя будет указано)."
   - 🥔 "Анонимно (от имени «Картошки»)."
3. Отправьте свой мем (текст, фото, видео или GIF)
4. Дождитесь модерации — бот сообщит вам о решении редакторов

## Установка и настройка

### 1. Установка зависимостей

Установите необходимые библиотеки с помощью `pip`:
```bash
pip install -r requirements.txt
```

### 2. Настройка переменных окружения

1. Создайте файл `.env` в корневой директории проекта
2. Добавьте в него следующие переменные:

```env
BOT_TOKEN=1234567890:ABCdefGHIjklMNOpqrsTUVwxyz  # Пример формата
EDITOR_IDS=123456789  # Один ID или несколько через запятую
PUBLISH_CHAT_ID=-100123456789  # ID должен начинаться с -100 для каналов
BOT_NAME=MyMemeBot  # Любое имя для вашего бота
CRYPTOSELECTARCHY=true  # Установите "true" для включения режима криптоселектархии
```

**Как получить значения:**

1. `BOT_TOKEN`: 
   - Напишите [@BotFather](https://t.me/BotFather) в Telegram
   - Используйте команду `/newbot`
   - Следуйте инструкциям и получите токен бота

2. `EDITOR_IDS` и `PUBLISH_CHAT_ID`:
   - Самый простой способ получить оба ID:
     - Напишите [@getidsbot](https://t.me/getidsbot)
     - Перешлите (форвардните) боту любое сообщение из нужного канала/чата
     - Бот покажет:
       * **Ваш ID** (для `EDITOR_IDS`)
       * **ID канала/чата** (для `PUBLISH_CHAT_ID`)
     - Если модераторов несколько, каждому нужно переслать сообщение боту и получить свой ID
     - Укажите ID модераторов через запятую без пробелов
     
   **Важно**: Не забудьте добавить вашего бота в канал/чат как администратора с правами на публикацию сообщений!

3. `BOT_NAME`:
   - Укажите имя, которое вы дали боту при создании
   - Может быть любым удобным для вас названием

4. `CRYPTOSELECTARCHY`:
   - Установите значение `true`, чтобы включить режим Криптоселектархической олигархии
   - При значении `false` или отсутствии этой переменной бот будет работать в обычном режиме

### 3. Развёртывание на сервере

1. Клонируйте репозиторий:
```bash
git clone git@github.com:kryuchenko/kartoshka_bot.git
cd kartoshka_bot
```

2. Установите необходимые пакеты и создайте виртуальное окружение:
```bash
# Установите python3.10-venv, если его нет
sudo apt install python3.10-venv

# Создайте и активируйте виртуальное окружение
python3 -m venv venv
source venv/bin/activate  # Для Linux/macOS
```

3. Установите зависимости:
```bash
pip install -r requirements.txt
```

4. Создайте и настройте файл `.env` (как описано выше)

5. Запустите бота в фоновом режиме с помощью `tmux`:
```bash
# Установите tmux, если его нет
sudo apt install tmux  # Для Ubuntu/Debian

# Создайте новую сессию
tmux new -s kartoshka_bot

# Убедитесь, что вы находитесь в нужной директории и файл бота существует
pwd  # должно показать путь до /kartoshka_bot
ls   # проверьте наличие файла kartoshka_bot.py

# Внутри сессии запустите бота
python3 kartoshka_bot.py

# Отключитесь от сессии (бот продолжит работать)
# Нажмите Ctrl+B, затем D
```

Чтобы обновить код и перезапустить бота одной командой:
```bash
git pull && tmux kill-session -t kartoshka_bot && tmux new-session -d -s kartoshka_bot "python3 kartoshka_bot.py"
```

Чтобы вернуться к сессии бота:
```bash
tmux attach -t kartoshka_bot
```

Чтобы остановить бота:
```bash
# Подключитесь к сессии и нажмите Ctrl+C
# Или завершите сессию командой
tmux kill-session -t kartoshka_bot
```

## Преимущества использования

- 🛡️ Защита чата от нежелательного контента
- 🎯 Централизованная модерация материалов
- 💫 Возможность анонимной публикации
- 👥 Выбор между единоличной и коллективной модерацией
- 📨 Автоматические уведомления
- 🤝 Удобный интерфейс для модераторов с кнопками для голосования
- 🗳️ Возможность настроить количество голосов для принятия решения в режиме криптоселектархии

## Режимы работы бота

### Обычный режим (Единоличный Узурпатор)

- Решения о публикации или отклонении мемов принимает единоличный модератор.
- Автор мема уведомляется о решении сразу после модерации.

### Криптоселектархическая олигархия

- Режим коллективного принятия решений.
- Криптоселектархи (т.е. модераторы) голосуют за одобрение или отклонение мема.
- Для публикации необходимо набрать 3 голоса "за".
- Для отклонения необходимо набрать 3 голоса "против".
- Автор мема уведомляется при каждом новом голосе и о конечном решении.
- Приветственное сообщение бота меняется, отражая текущий режим работы.

## Философия проекта

Наш бот создан с любовью к мемам и заботой о комфорте пользователей. Мы верим, что юмор должен быть доступным и безопасным для всех участников сообщества. Режим **Криптоселектархической олигархии** позволяет обеспечить более справедливый процесс модерации за счёт коллективного принятия решений. Бот помогает создать уютную атмосферу, где каждый может поделиться своим творчеством, сохраняя при этом порядок и дружелюбную обстановку в чате.

---

С любовью к мемам и картошке! 🥔✨
