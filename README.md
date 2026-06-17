# 🃏 Moharez NFC — راهنمای نصب و راه‌اندازی

## ساختار فایل‌ها

```
repo/
├── index.html     ← کارت NFC مشتری (public)
├── panel.html     ← پنل مدیریت (password protected)
├── data.json      ← داده‌ها (GitHub API آپدیت می‌کنه)
└── README.md
```

---

## مرحله ۱ — آپلود روی GitHub Pages

1. یه repo جدید بساز (مثلاً `moharez-ali`)
2. هر سه فایل رو آپلود کن: `index.html` ، `panel.html` ، `data.json`
3. برو **Settings → Pages → Branch: main → Save**
4. سایت روی `https://username.github.io/moharez-ali` آنلاین میشه

---

## مرحله ۲ — GitHub Token بگیر

1. برو [github.com/settings/tokens](https://github.com/settings/tokens)
2. روی **Generate new token (classic)** کلیک کن
3. یه اسم بده (مثلاً `moharez-nfc`)
4. تیک **repo** رو بزن
5. روی **Generate token** کلیک کن
6. توکن رو کپی کن ← **فقط یه بار نشون داده میشه!**

---

## مرحله ۳ — تنظیم پنل

1. برو به `https://username.github.io/moharez-ali/panel.html`
2. رمز ورود: **`moharez2025`** (در فایل panel.html قابل تغییره)
3. بالای صفحه **"تنظیم اتصال"** رو بزن
4. اطلاعات رو پر کن:
   - **Token:** توکن GitHub
   - **Username:** نام کاربری GitHub
   - **Repo:** نام repository
   - **Path:** `data.json`
   - **Branch:** `main`
5. ذخیره کن

---

## مرحله ۴ — تغییر رمز پنل

داخل `panel.html` خط زیر رو پیدا کن و رمز رو عوض کن:

```javascript
const PANEL_PASSWORD = 'moharez2025';
```

---

## امکانات پنل

| امکان | توضیح |
|-------|-------|
| 📷 عکس پروفایل | آپلود از دستگاه، base64 ذخیره میشه |
| 🎵 موزیک | فایل MP3 آپلود، پلیر کامل |
| 🏷️ تگ‌ها | حداکثر ۵ تگ |
| 🔗 شبکه‌های اجتماعی | تلگرام، اینستاگرام، واتساپ، گیتهاب، لینکدین |
| 📞 تماس | تلفن، ایمیل، آدرس |
| 👁️ پیش‌نمایش | قبل از ذخیره ببین |
| ✅ ثبت روی سایت | GitHub API — سایت فوری آپدیت |
| 🔒 لاگین | رمز ساده، session-based |

---

## نکته مهم درباره موزیک و عکس

عکس و موزیک به صورت **base64** داخل `data.json` ذخیره میشن.
- عکس: حداکثر 2MB توصیه میشه
- موزیک: حداکثر 5MB توصیه میشه (بیشتر از این ممکنه GitHub رد کنه)

اگه فایل‌ها بزرگن، بهتره از لینک مستقیم (CDN/hosting) استفاده کنی.

---

## عیب‌یابی

| مشکل | راه‌حل |
|------|---------|
| ثبت نمیشه | Token رو چک کن — دسترسی `repo` لازمه |
| سایت آپدیت نمیشه | GitHub Pages یه دقیقه تأخیر داره |
| عکس نمیاد | سایز عکس رو کم کن |
| رمز فراموش شدم | داخل `panel.html` پیدا کن و عوض کن |

---

**ساخته شده توسط Moharez NFC** 🚀
