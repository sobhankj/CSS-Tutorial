# Session 5 — Background

در این جلسه خاصیت‌های مربوط به **پس‌زمینه تصویر** را روی یک باکس می‌بینیم. عنصر `.box` ابعاد دارد و با تصویر کوه تزئین می‌شود.

```css
.box {
  width: 1000px;
  height: 500px;
}
```

---

## 1. `background-image`
آدرس تصویر پس‌زمینه را مشخص می‌کند.

```css
background-image: url('https://www.w3schools.com/css/mountain.jpg');
```

---

## 2. `background-size`
اندازه تصویر روی عنصر را کنترل می‌کند.

| مقدار | معنی |
| --- | --- |
| `cover` | تصویر کل باکس را می‌پوشاند (ممکن است بخشی از تصویر بریده شود) |
| `contain` | کل تصویر داخل باکس جا می‌شود (ممکن است فضای خالی بماند) |
| `100%` | عرض تصویر برابر عرض باکس می‌شود |

```css
background-size: cover;
background-size: contain;
background-size: 100%;
```

> اگر چند بار پشت سر هم نوشته شود، فقط **آخرین مقدار** اعمال می‌شود.

---

## 3. `background-repeat`
تکرار شدن تصویر را مشخص می‌کند.

| مقدار | معنی |
| --- | --- |
| `repeat` | تصویر در هر دو جهت تکرار می‌شود (پیش‌فرض) |
| `no-repeat` | تصویر فقط یک بار نشان داده می‌شود |

```css
background-repeat: repeat;
background-repeat: no-repeat;
```

---

## 4. `background-attachment`
رفتار تصویر هنگام اسکرول صفحه را مشخص می‌کند.

| مقدار | معنی |
| --- | --- |
| `scroll` | تصویر همراه محتوا اسکرول می‌شود (پیش‌فرض) |
| `fixed` | تصویر ثابت می‌ماند و محتوا روی آن حرکت می‌کند |

```css
background-attachment: fixed;
background-attachment: scroll;
```

در `index.html` چند `<br>` گذاشته شده تا بتوان اثر `fixed` را با اسکرول تست کرد.

---

## 5. `background-position`
جای تصویر داخل عنصر را مشخص می‌کند.

```css
background-position: center; /* وسط */
background-position: top;    /* بالا */
```

مقادیر رایج دیگر: `left`، `right`، `bottom`، یا ترکیب مثل `top left` و حتی درصد مثل `50% 50%`.

---

## 6. Shorthand: `background`
همه خاصیت‌های بالا را می‌توان در یک خط نوشت:

```css
background: url('...') no-repeat fixed center;
```

ترتیب رایج:

```text
background: [image] [repeat] [attachment] [position];
```

مثال این جلسه:

```css
background: url('https://www.w3schools.com/css/mountain.jpg') no-repeat fixed center;
```

یعنی:
- تصویر کوه
- بدون تکرار
- ثابت هنگام اسکرول
- قرارگیری در مرکز

---

## نکته مهم
در فایل `style.css` چند مقدار برای یک خاصیت نوشته شده (مثلاً چند `background-size`). در CSS همیشه **آخرین تعریف** برنده است. این کار برای تمرین و مقایسه مقادیر مختلف است؛ در پروژه واقعی معمولاً فقط یک مقدار نهایی نگه داشته می‌شود.
