# 🛍️ Divine Beauty Shop

A Django-based Persian/English bilingual e-commerce web application with user authentication, product management, cart, order, and email verification functionality. Built using Django 5.2.4, Python 3.13.2, PostgreSQL, and Tailwind CSS.

---

## 🇮🇷 فروشگاه آنلاین Divine Beauty

این پروژه یک **وب‌اپلیکیشن فروشگاه آنلاین** است که با استفاده از Django توسعه داده شده و امکاناتی مثل مدیریت کاربران، محصولات، سبد خرید، سفارش، تأیید ایمیل، محافظت رباتی و رابط کاربری مدرن را فراهم می‌کند.

---

## ✨ Features / ویژگی‌ها

### 👤 User Authentication / احراز هویت

- ثبت‌نام با نام، نام خانوادگی، ایمیل و رمز عبور
- تأیید ایمیل قبل از ورود
- ورود/خروج امن با reCAPTCHA v2 و honeypot
- مدل کاربر سفارشی (CustomUser) با ایمیل به‌عنوان فیلد یکتا
- پیام‌رسانی بر اساس Session (با PostgreSQL)

### 🛒 فروشگاه

- مدیریت محصولات با پشتیبانی از اسلاگ فارسی
- سبد خرید پویا با افزودن، حذف، به‌روزرسانی
- ثبت سفارش با اطلاعات ارسال و روش پرداخت
- پروفایل کاربر شامل سبد و تاریخچه سفارش
- رابط کاربری واکنش‌گرا با Tailwind CSS، Remixicon، Swiper

---

## 🛠 Technologies / تکنولوژی‌ها

- Python 3.13.2  
- Django 5.2.4  
- PostgreSQL  
- Tailwind CSS  
- Font: Zain, Jost  
- JavaScript, Remixicon, Swiper

---

## 🔑 Key Dependencies / وابستگی‌ها

- `django-recaptcha==4.0.0` – محافظت با reCAPTCHA  
- `psycopg2-binary` – اتصال PostgreSQL  
- `requests` – برای reCAPTCHA API  
- `django.contrib.auth` – مدیریت کاربران و نشست‌ها  

> ✅ Optional: نصب django-ratelimit برای محدودسازی درخواست‌ها  
```bash
pip install django-ratelimit
```

---

## 📦 Requirements / پیش‌نیازها

- Python 3.13.2  
- Django 5.2.4  
- PostgreSQL  
- virtualenv (اختیاری)

---

## ⚙️ Setup / نصب و اجرا

```bash
# Clone the repository
git clone <repository-url>
cd DivineBeautyShop

# Create virtual environment
python -m venv venv
source venv/bin/activate  # Windows: venv\Scripts\activate

# Install dependencies
pip install -r requirements.txt
```

### 🔧 Configure Environment

Create a `.env` or edit `settings.py`:
```python
RECAPTCHA_PUBLIC_KEY = 'your-site-key'
RECAPTCHA_PRIVATE_KEY = 'your-secret-key'

EMAIL_HOST = 'smtp.gmail.com'
EMAIL_PORT = 587
EMAIL_USE_TLS = True
EMAIL_HOST_USER = 'your-email@gmail.com'
EMAIL_HOST_PASSWORD = 'your-app-password'
DEFAULT_FROM_EMAIL = 'your-email@gmail.com'

DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.postgresql',
        'NAME': 'myproject',
        'USER': 'myuser',
        'PASSWORD': 'mypassword',
        'HOST': 'localhost',
        'PORT': '5432',
    }
}
```

### 📂 Migrations & Run

```bash
python manage.py makemigrations
python manage.py migrate
python manage.py collectstatic
python manage.py createsuperuser  # optional
python manage.py runserver
```

> Project runs at: `http://127.0.0.1:8000`

---

## 🔗 URLs / مسیرهای مهم

- `/accounts/register/` : ثبت‌نام  
- `/accounts/login/` : ورود  
- `/accounts/logout/` : خروج  
- `/accounts/profile/` : پروفایل  
- `/cart/` : سبد خرید  
- `/order/create/` : ثبت سفارش  
- `/products/<id>/` : جزئیات محصول  
- `/` : صفحه اصلی  

---

## 🗂 Project Structure

```
DivineBeautyShop/
├── accounts/
│   ├── models.py ← CustomUser
│   ├── views.py ← Register, Login, Logout, Verify
│   └── urls.py
├── orders/ ← Cart, Orders
├── products/ ← Product model & views
├── templates/accounts/html/ ← HTML Templates
├── static/ ← css/, js/, img/
```

---

## 🧪 Testing

- ثبت‌نام با داده صحیح/نادرست و تأیید ایمیل  
- ورود با حساب تأیید شده/نشده  
- خروج از حساب  
- بررسی لاگ‌ها در فایل `debug.log`

---

## 🚀 Future Improvements / توسعه‌های آینده

- بازیابی رمز عبور (Password Reset)  
- افزودن سیستم کد تخفیف و فیلتر پیشرفته  
- بهبود فرم‌ها و انیمیشن رابط کاربری  
- اتصال درگاه پرداخت آنلاین  
- پیاده‌سازی کامل بخش محصولات و سبد خرید


