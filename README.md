# قالب سایت فروشگاهی برازنده (نسخه استاتیک برای GitHub Pages)

نسخه‌ی **استاتیک** و **بدون بک‌اند** از سایت واقعی فروشگاه «برازنده» — همان تمپلیت‌ها، همان CSS/JS اصلی، همان هدر/فوتر/منوی پایین، فقط با داده‌های نمونه (فیک) به‌جای دیتابیس واقعی و بدون پنل ادمین.

> 🔗 نسخه‌ی واقعی و فعال سایت (با بک‌اند کامل جنگو) در حال حاضر لایو است.
> این ریپازیتوری فقط برای نمایش UI/UX و کدهای فرانت‌اند ساخته شده.

## 🖥️ دمو
[لینک GitHub Pages را اینجا اضافه کن — بعد از فعال‌سازی Pages]

## ✨ ویژگی‌ها
- ۳۲ صفحه‌ی HTML رندرشده از تمپلیت‌های واقعی جنگوی سایت
- ۱۲ محصول نمونه در دسته‌بندی‌های مختلف (شومیز، تیشرت زنانه، پیراهن زنانه، دامن)
- مقالات کامل در بخش مجله (راهنمای سایز، نگهداری پارچه)
- پروفایل کامل کاربر نمونه: سفارش‌ها، آدرس‌ها، تیکت‌های پشتیبانی، اعلان‌ها
- صفحات کامل فروشگاهی: سبد خرید، ورود/ثبت‌نام، سوالات متداول، تماس با ما، قوانین
- طراحی کاملاً واکنش‌گرا (ریسپانسیو) و راست‌به‌چپ (RTL)
- عکس‌های واقعی محصولات، بنرها، کاور مقالات و آواتار پروفایل

## 🛠️ ساختار فنی
```
├── index.html, products.html, product-1..12.html   → صفحات محصولات و فروشگاه
├── cart.html, login.html, profile.html              → سبد خرید و حساب کاربری
├── blog.html, blog-*.html                           → مجله و مقالات
├── about.html, contact.html, faq.html, terms.html   → صفحات اطلاعاتی
├── assets/
│   ├── css/main.css      → استایل اصلی سایت
│   ├── js/main.js        → منطق فرانت‌اند (تعامل‌ها، منوها و...)
│   ├── data/             → داده‌های JSON نمونه (بنرها و...)
│   ├── products/, banner/, logo/, fonts/
```

## ⚙️ نحوه ساخت این نسخه
تمپلیت‌های اصلی Django (`base.html`, `core/home.html`, `products/list.html` و `detail.html`, `accounts/profile.html`, `blog/list.html` و `detail.html` و غیره) با موتور Jinja2 و داده‌های نمونه رندر شدند تا خروجی HTML نهایی، دقیقاً همان مارک‌آپ و استایل سایت واقعی را داشته باشد.

## ⚠️ نکات مهم
- چون این نسخه بک‌اند واقعی ندارد، اکشن‌هایی مثل «افزودن به سبد خرید»، «ثبت نظر»، «پرداخت» و... درخواست شبکه می‌فرستند ولی چون سرور واقعی پشت‌شان نیست، پاسخ موفق نمی‌گیرند.
- عکس محصولات، بنرها، کاور مقالات و آواتار پروفایل از Unsplash (رایگان و بدون کپی‌رایت) و به‌صورت hotlink بارگذاری می‌شوند.
- داده‌های نمونه در `build/dataset.py` تعریف شده‌اند (جدا از خروجی نهایی)؛ خودِ فایل‌های HTML، ایستا و نهایی هستند.

## 🚀 آپلود روی GitHub Pages
```bash
git init
git add .
git commit -m "Static UI showcase"
git branch -M main
git remote add origin https://github.com/USERNAME/barazandeh-tan.git
git push -u origin main
```
سپس در گیت‌هاب: `Settings > Pages > Source: Deploy from a branch > Branch: main > Folder: / (root)` را انتخاب کن.

آدرس نهایی: `https://USERNAME.github.io/barazandeh-tan/`

---

## English

Static, backend-free UI showcase of the **Barazandeh** online fashion store. The real production site runs on Django with a full backend and admin panel — this repo renders the same templates, CSS, and JS with sample data, for a clean front-end demo on GitHub Pages.

**Includes:** 32 rendered HTML pages, 12 sample products across categories (blouses, women's t-shirts, dresses, skirts), a full blog section, a sample user profile (orders, addresses, support tickets, notifications), cart/login/FAQ/contact/terms pages — fully responsive, RTL layout.

Since there's no real backend, actions like "add to cart" or "submit review" fire network requests that won't succeed (same as the live site with no server connection). Product/banner/avatar images are hotlinked from Unsplash.
