# Ketchunez health watchdog

Внешний мониторинг сайта https://ketchunez.ru.

Каждые 5 минут запускается GitHub Actions cron. Если сайт отдаёт не 200 либо БД не отвечает — после 2 фейлов подряд (≈10 мин downtime) шлёт алерт в Telegram-группу «КЕТЧУНЕЗ» → topic «Состояние сайта». При восстановлении — сообщение «Сайт восстановлен».

Репозиторий **публичный** специально — GitHub Actions для public repos неограничены, scheduled cron работает гарантированно (private free tier — 2000 минут/мес, что приводит к throttling).

Внутри кода нет секретов — токен бота и chat ID хранятся в GitHub Actions Secrets.
