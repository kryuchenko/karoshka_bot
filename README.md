# Karoshka Bot (Бот-Картошка) 🥔

## О боте

Karoshka Bot — это дружелюбный Telegram-бот для модерации и публикации мемов в вашем чате. Он создан, чтобы сделать процесс публикации мемов простым, безопасным и веселым!

## Основные возможности

- 📝 Возможность публикации как текстовых, так и фото-мемов
- 🎭 Два режима публикации:
  - От своего имени (с указанием автора)
  - От имени "Анонимной Аллюминиевой Картошки" (для тех, кто хочет остаться инкогнито)
- 👥 Система модерации контента через доверенных редакторов
- ✨ Автоматическое уведомление авторов о статусе их публикаций

## Как использовать

1. Начните диалог с ботом командой `/start`
2. Выберите режим публикации:
   - Напишите `user` для публикации от своего имени
   - Напишите `potato` для анонимной публикации
3. Отправьте свой мем (текст или фото)
4. Дождитесь модерации — бот сообщит вам о решении редакторов

## Установка и настройка

### 1. Установка зависимостей

Установите необходимые библиотеки с помощью pip:

```bash
pip install -r requirements.txt
```

### 2. Настройка переменных окружения

1. Создайте файл `.env` в корневой директории проекта
2. Добавьте в него следующие переменные:

```env
BOT_TOKEN=1234567890:ABCdefGHIjklMNOpqrsTUVwxyz # Пример формата
EDITOR_IDS=123456789 # Один ID или несколько через запятую
PUBLISH_CHAT_ID=-100123456789 # ID должен начинаться с -100 для публичных групп
BOT_NAME=MyMemeBot # Любое имя для вашего бота
```

Как получить значения:

1. `BOT_TOKEN`: 
   - Напишите [@BotFather](https://t.me/BotFather) в Telegram
   - Используйте команду /newbot
   - Следуйте инструкциям и получите токен бота

2. `EDITOR_IDS` и `PUBLISH_CHAT_ID`:
   Самый простой способ получить оба ID:
   - Напишите [@getidsbot](https://t.me/getidsbot)
   - Перешлите (форвардните) боту любое сообщение из нужного канала/чата
   - Бот покажет:
     * Ваш ID (для EDITOR_IDS)
     * ID канала/чата (для PUBLISH_CHAT_ID)
   - Если модераторов несколько, каждому нужно переслать сообщение боту и получить свой ID
   - Укажите ID модераторов через запятую без пробелов
   
Важно: Не забудьте добавить вашего бота в канал/чат как администратора с правами на публикацию сообщений!

4. `BOT_NAME`:
   - Укажите имя, которое вы дали боту при создании
   - Может быть любым удобным для вас названием

## Преимущества использования

- 🛡️ Защита чата от нежелательного контента
- 🎯 Централизованная модерация материалов
- 💫 Возможность анонимной публикации
- 📨 Автоматические уведомления
- 🤝 Удобный интерфейс для модераторов

## Философия проекта

Наш бот создан с любовью к мемам и заботой о комфорте пользователей. Мы верим, что юмор должен быть доступным и безопасным для всех участников сообщества. Бот помогает создать уютную атмосферу, где каждый может поделиться своим творчеством, сохраняя при этом порядок и дружелюбную обстановку в чате.

---

С любовью к мемам и картошке! 🥔✨
