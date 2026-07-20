# Session 17 — List Style

با خاصیت‌های `list-style` ظاهر نشانه‌های لیست (`ul` / `ol` و آیتم‌های `li`) را کنترل می‌کنیم.

در این جلسه روی یک `ul` کار می‌کنیم:

```html
<ul class="list">
  <li>item 1</li>
  ...
</ul>
```

---

## 1. `list-style-type`
نوع نشانه‌ی پیش‌فرض لیست را مشخص می‌کند (وقتی از تصویر استفاده نکنید).

| مقدار | معنی |
| --- | --- |
| `disc` | دایره توپر (پیش‌فرض `ul`) |
| `circle` | دایره توخالی |
| `square` | مربع |
| `decimal` | ۱، ۲، ۳... (معمول `ol`) |
| `none` | بدون نشانه |

```css
ul {
  list-style-type: square;
}
```

---

## 2. `list-style-image`
به‌جای دایره/عدد، یک **تصویر** به‌عنوان نشانه لیست می‌گذارد.

```css
ul {
  list-style-image: url("../images/icon.svg");
}
```

مسیر نسبت به فایل CSS است؛ اینجا آیکون از پوشه `images` خوانده می‌شود.

اگر تصویر لود نشود، مرورگر معمولاً به `list-style-type` برمی‌گردد.

---

## 3. `list-style-position`
جای نشانه را نسبت به متن مشخص می‌کند.

| مقدار | معنی |
| --- | --- |
| `outside` | نشانه بیرون باکس محتوا (پیش‌فرض) |
| `inside` | نشانه داخل جریان متن/باکس آیتم |

```css
ul {
  list-style-position: inside;
}
```

با `inside`، نشانه همراه متن داخل آیتم قرار می‌گیرد و در layout مرتب‌تر دیده می‌شود؛ مخصوصاً وقتی `padding` لیست را صفر کرده باشید.

---

## 4. Shorthand: `list-style`
هر سه را می‌توان در یک خط نوشت:

```css
ul {
  list-style: disc inside url("../images/icon.svg");
  /* type | position | image */
}
```

یا برای حذف کامل نشانه‌ها (رایج در منوها):

```css
ul {
  list-style: none;
}
```

وقتی `list-style: none` می‌گذارید، معمولاً `padding`/`margin` پیش‌فرض لیست را هم صفر می‌کنند تا فاصله اضافه نماند.

---

## مثال این جلسه

```css
ul {
  list-style-image: url("../images/icon.svg");
  list-style-position: inside;
}
```

| خاصیت | مقدار | اثر |
| --- | --- | --- |
| `list-style-image` | `icon.svg` | به‌جای bullet، آیکون سفارشی |
| `list-style-position` | `inside` | نشانه داخل آیتم |

> نکته: در ابتدای فایل `margin` و `padding` همه عناصر صفر شده؛ با `inside` نشانه‌ها بهتر دیده می‌شوند چون تورفتگی پیش‌فرض `ul` حذف شده است.
