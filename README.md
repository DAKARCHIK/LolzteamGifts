# Lolz Deals Bot

> Telegram-бот для безопасных P2P-сделок с поддержкой криптовалют и фиата

[![Python](https://img.shields.io/badge/Python-3.11+-3776AB?style=flat&logo=python&logoColor=white)](https://python.org)
[![python-telegram-bot](https://img.shields.io/badge/python--telegram--bot-22.0+-2CA5E0?style=flat&logo=telegram&logoColor=white)](https://python-telegram-bot.org)
[![License](https://img.shields.io/badge/License-MIT-green?style=flat)](LICENSE)

---

## О проекте

**Lolz Deals Bot** — Telegram-бот-гарант для проведения безопасных сделок между двумя сторонами. Бот выступает посредником: покупатель переводит средства боту, продавец передаёт товар/услугу, после чего бот завершает сделку и выплачивает продавцу.

Канал с ботом: [@skladmaterialov](https://t.me/skladmaterialov)

---

## Возможности

| Функция | Описание |
|---|---|
| 🤝 **P2P-сделки** | Создание сделок между покупателем и продавцом с пошаговым подтверждением |
| 💱 **Мультивалютность** | RUB, USDT, BTC, UAH, KZT, BYN, Telegram Stars |
| 💰 **Баланс и депозит** | Пополнение через Crypto Pay (CryptoBot) |
| 🔗 **Invite-ссылки** | Уникальная ссылка для второго участника сделки |
| 👥 **Реферальная система** | 50% от комиссии с каждой сделки реферала |
| 🌍 **Мультиязычность** | Русский и английский интерфейс |
| 👑 **Админ-панель** | Управление пользователями, банлист |
| 💎 **Premium emoji** | Кастомные Telegram Premium-эмодзи в кнопках и сообщениях |
| 📊 **История сделок** | Просмотр всех активных и завершённых сделок |
| 🛡 **Безопасность** | Атомарная запись JSON, защита от дублирования |

---

## Стек технологий

- **Python 3.11+**
- **python-telegram-bot 22.0+** — асинхронный фреймворк для Telegram Bot API
- **httpx** — HTTP-клиент для интеграции с внешними API
- **Crypto Pay API** (CryptoBot) — приём платежей в крипте
- **CoinGecko API** — курсы криптовалют
- **open.er-api.com** — курсы фиатных валют

---

## Установка

```bash
# 1. Клонируйте репозиторий
git clone https://github.com/your-username/LolzteamGifts.git
cd LolzteamGifts

# 2. Создайте виртуальное окружение
python -m venv .venv

# Windows
.venv\Scripts\activate

# Linux / macOS
source .venv/bin/activate

# 3. Установите зависимости
pip install -r requirements.txt
```

---

## Настройка

Токен бота передаётся через переменную окружения или аргумент запуска. Ничего не хранится в конфигурационных файлах.

| Переменная | Описание |
|---|---|
| `BOT_TOKEN` | Токен Telegram-бота (от [@BotFather](https://t.me/BotFather)) |
| `CRYPTO_PAY_TOKEN` | API-токен Crypto Pay для приёма платежей |

---

## Запуск

**Через переменную окружения (рекомендуется):**

```bash
# Linux / macOS
export BOT_TOKEN="ваш_токен"
export CRYPTO_PAY_TOKEN="ваш_cryptopay_токен"
python main.py

# Windows (PowerShell)
$env:BOT_TOKEN="ваш_токен"
$env:CRYPTO_PAY_TOKEN="ваш_cryptopay_токен"
python main.py
```

**Через аргумент командной строки:**

```bash
python main.py <BOT_TOKEN>
```

---

## Структура проекта

```
LolzteamGifts/
├── main.py                      # Основной файл бота
├── requirements.txt             # Зависимости
├── forbot.jpg                   # Приветственное изображение
├── deals.json                   # База активных сделок
├── balances.json                # Балансы пользователей
├── reqs.json                    # Реквизиты пользователей
├── langs.json                   # Настройки языка
└── completed_deals_boost.json   # Статистика завершённых сделок
```

---

## Сценарий работы сделки

```
Создатель                    Бот                      Второй участник
    │                         │                              │
    │──── /start ────────────►│                              │
    │◄─── Меню ───────────────│                              │
    │                         │                              │
    │── Создать сделку ───────►│                              │
    │◄─ Ссылка на сделку ─────│                              │
    │                         │◄────── Переход по ссылке ────│
    │                         │──────► Подтверждение ────────►│
    │                         │                              │
    │── Подтвердить оплату ───►│                              │
    │                         │──────► Уведомление ──────────►│
    │                         │◄────── Товар передан ─────────│
    │◄─ Уведомление ──────────│                              │
    │── Получил товар ────────►│                              │
    │                         │──────► Сделка завершена ──────►│
```

---

## Поддерживаемые валюты

| Валюта | Символ | Источник курса |
|---|---|---|
| Российский рубль | RUB | Базовая |
| USDT (Tether) | USDT | CoinGecko / CryptoBot |
| Bitcoin | BTC | CoinGecko / CryptoBot |
| Украинская гривна | UAH | open.er-api.com |
| Казахстанский тенге | KZT | open.er-api.com |
| Белорусский рубль | BYN | open.er-api.com |
| Telegram Stars | ⭐ | Встроенная |

---

## Лицензия

Этот проект распространяется под лицензией MIT. Подробнее в файле [LICENSE](LICENSE).
