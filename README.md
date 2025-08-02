
# 📦 amin-backup

ابزاری حرفه‌ای برای بکاپ‌گیری از Marzban و ارسال خودکار به تلگرام — توسعه داده شده توسط **محمدامین (aminborna)**

---

## 🚀 ویژگی‌ها

- بکاپ‌گیری کامل از پنل Marzban
- پشتیبانی از MariaDB، MySQL و SQLite
- ارسال خودکار بکاپ‌ها به تلگرام
- کرون‌جاب اتوماتیک (نصب آسان زمان‌بندی‌شده)
- پیام کاملاً شخصی‌سازی‌شده در تلگرام
- نصب آسان تنها با یک خط کد

---

## ⚙️ نصب سریع

```bash
bash <(curl -sL https://raw.githubusercontent.com/aminborna/amin-backup/main/marzban.sh)
```

---

## 🧩 پیش‌نیازها

- فعال بودن `curl` و `bash`
- داشتن ربات تلگرام و گرفتن:
  - `TELEGRAM_BOT_TOKEN`
  - `TELEGRAM_CHAT_ID`

---

## 🔧 تنظیمات فایل `config.json`

در مسیر `/opt/amin-backup/config.json`:

```json
{
  "telegram_bot_token": "توکن_ربات_شما",
  "telegram_chat_id": "آیدی_عدد_یا_کانال",
  "databases": [
    {
      "type": "mariadb",
      "env_path": "/opt/marzban/.env",
      "docker_path": "/opt/marzban/docker-compose.yml",
      "container_name": "mariadb",
      "url_format": "sqlalchemy",
      "external": ["/var/lib/marzban/certs"]
    },
    {
      "type": "sqlite",
      "db_name": "test",
      "env_path": "/opt/marzban/.env",
      "docker_path": "/opt/marzban/docker-compose.yml",
      "external": ["/var/lib/marzban/templates"]
    }
  ]
}
```

---

## 📥 پیام دریافتی در تلگرام

```
📦 بکاپ با موفقیت انجام شد  
👨‍💻 ارسال‌شده توسط: محمدامین (aminborna)  
✅ مخصوص پنل Marzban  
🛡 پشتیبان‌گیری اختصاصی توسط اسکریپت شخصی‌سازی‌شده  
📁 GitHub: https://github.com/aminborna/marzban-backup
```

---

## ⏰ افزودن به کرون‌جاب

برای اجرای خودکار هر ۱ ساعت:

```bash
(crontab -l 2>/dev/null; echo "0 * * * * bash /opt/amin-backup/marzban.sh") | crontab -
```

---

## 📚 منابع

- [Marzban Documentation (Gozargah)](https://github.com/Gozargah/Marzban)
- [Telegram Bot API](https://core.telegram.org/bots/api)

---

## 🛡 مجوز

MIT License — استفاده آزاد با حفظ نام نویسنده (aminborna)

---

## 🙋‍♂️ پشتیبانی

در صورت نیاز به پشتیبانی یا همکاری:
- GitHub: [aminborna](https://github.com/aminborna)
- Telegram: [@aminborna](https://t.me/aminborna)

