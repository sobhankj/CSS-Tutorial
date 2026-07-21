# Session 32 — Media Queries

`@media` به CSS اجازه می‌دهد استایل‌ها را **فقط وقتی شرطی برقرار است** اعمال کند؛ مثلاً وقتی عرض صفحه از یک مقدار کمتر یا بیشتر شود.

این پایهٔ طراحی **ریسپانسیو** است: یک صفحه روی دسکتاپ و موبایل ظاهر متفاوت داشته باشد.

در این جلسه وقتی عرض viewport به ۶۰۰px یا کمتر برسد، اندازه و رنگ `h1` و `p` عوض می‌شوند.

---

## 1. بدون Media Query

```css
h1 {
  font-size: 40px;
  color: red;
}

p {
  font-size: 20px;
  color: blue;
}
```

این استایل‌ها روی **همه اندازه‌های صفحه** یکسان‌اند. روی موبایل ممکن است عنوان خیلی بزرگ به نظر برسد.

---

## 2. ساختار `@media`

شکل کلی:

```css
@media media-type and (شرط) {
  /* استایل‌های شرطی */
}
```

| بخش | معنی |
| --- | --- |
| `@media` | شروع یک Media Query |
| `screen` | فقط برای صفحه‌نمایش (نه چاپ) |
| `and` | ترکیب شرط‌ها |
| `(max-width: 600px)` | وقتی عرض viewport حداکثر ۶۰۰px باشد |

---

## 3. مثال این جلسه

```css
.container {
  max-width: 800px;
  margin: 50px auto;
  text-align: center;
}

h1 {
  font-size: 40px;
  color: red;
}

p {
  font-size: 20px;
  color: blue;
}

@media screen and (max-width: 600px) {
  h1 {
    font-size: 20px;
    color: green;
  }
  p {
    font-size: 10px;
    color: yellow;
  }
}
```

| حالت | `h1` | `p` |
| --- | --- | --- |
| عرض بیشتر از ۶۰۰px | ۴۰px، قرمز | ۲۰px، آبی |
| عرض ۶۰۰px یا کمتر | ۲۰px، سبز | ۱۰px، زرد |

برای تست: پنجره مرورگر را کوچک کنید یا DevTools را روی موبایل بگذارید؛ وقتی عرض به ۶۰۰px برسد، رنگ و فونت عوض می‌شود.

---

## 4. `max-width` vs `min-width`

```css
@media (max-width: 600px) { /* عرض ≤ 600px */ }
@media (min-width: 601px) { /* عرض ≥ 601px */ }
```

| رویکرد | معنی | کاربرد رایج |
| --- | --- | --- |
| `max-width` | تا این عرض | استایل موبایل روی دسکتاپ پایه |
| `min-width` | از این عرض به بالا | موبایل‌اول؛ استایل بزرگ‌تر برای تبلت/دسکتاپ |

این جلسه از `max-width: 600px` استفاده می‌کند: استایل پایه برای دسکتاپ، و استایل کوچک‌تر برای صفحه‌های باریک.

---

## 5. نقش `viewport` در HTML

در `index.html` این خط مهم است:

```html
<meta name="viewport" content="width=device-width, initial-scale=1.0">
```

بدون این meta، موبایل‌ها صفحه را مثل دسکتاپ کوچک‌شده نشان می‌دهند و Media Query درست کار نمی‌کند. `width=device-width` عرض واقعی دستگاه را به CSS می‌دهد.

---

## 6. انواع رایج Media Type و شرط

```css
@media screen and (max-width: 600px) { }
@media print { /* فقط هنگام چاپ */ }
@media (orientation: landscape) { /* افقی */ }
@media (min-width: 768px) and (max-width: 1024px) { /* بازه */ }
```

| شرط | معنی تقریبی |
| --- | --- |
| `screen` | صفحه‌نمایش |
| `print` | حالت چاپ |
| `max-width` / `min-width` | عرض viewport |
| `orientation` | عمودی یا افقی |

---

## خلاصه مثال این جلسه

| بخش | مقدار | نتیجه |
| --- | --- | --- |
| استایل پایه | `h1` قرمز ۴۰px، `p` آبی ۲۰px | ظاهر دسکتاپ |
| `@media ... (max-width: 600px)` | `h1` سبز ۲۰px، `p` زرد ۱۰px | ظاهر موبایل/عرض کم |
| `meta viewport` | در HTML | فعال شدن درست Media Query روی موبایل |

صفحه با عنوان و پاراگراف؛ با کوچک کردن عرض تا ۶۰۰px، اندازه و رنگ متن‌ها تغییر می‌کند.
