# Session 13 — Text Decoration & Transformation

در این جلسه دو گروه خاصیت را می‌بینیم:

- `text-decoration` — تزئین متن (خط زیر، خط روی متن و ...)
- `text-transform` — تبدیل حروف (بزرگ/کوچک و ...)

---

## 1. `text-decoration`
خطوط تزئینی روی متن اضافه یا حذف می‌کند.

| مقدار | معنی |
| --- | --- |
| `none` | بدون تزئین |
| `underline` | خط زیر متن |
| `line-through` | خط روی متن (مثل متن خط‌خورده) |
| `overline` | خط بالای متن |

### مثال‌های این جلسه

```css
.box h1 {
  text-decoration: underline; /* خط زیر عنوان */
}

.box h2 {
  text-decoration: line-through; /* خط روی نام */
}
```

---

## 2. چرا روی لینک‌ها معمولاً `text-decoration: none` می‌گذاریم؟
مرورگر به‌صورت پیش‌فرض برای تگ `<a>` خط زیر (`underline`) می‌گذارد تا لینک بودن مشخص باشد. در طراحی‌های مدرن اغلب این خط را نمی‌خواهند و می‌نویسند:

```css
.box a {
  text-decoration: none;
}
```

یا کلی‌تر در کل پروژه:

```css
a {
  text-decoration: none;
}
```

### نکته UX
اگر خط زیر را حذف کردید، لینک را از متن عادی جدا کنید؛ مثلاً با رنگ متفاوت، `font-weight`، یا underline فقط در hover:

```css
a {
  text-decoration: none;
  color: #ffe600;
}

a:hover {
  text-decoration: underline;
}
```

---

## 3. `text-transform`
حروف متن را تبدیل می‌کند؛ محتوای HTML عوض نمی‌شود، فقط نمایش عوض می‌شود.

| مقدار | معنی |
| --- | --- |
| `none` | بدون تغییر (پیش‌فرض) |
| `uppercase` | همه حروف بزرگ |
| `lowercase` | همه حروف کوچک |
| `capitalize` | حرف اول هر کلمه بزرگ |

```css
.box p {
  text-transform: uppercase;
}
```

متن `my name is Kian Kooshki` به صورت `MY NAME IS KIAN KOOSHKI` دیده می‌شود.

---

## خلاصه مثال‌های این جلسه

| عنصر | خاصیت | نتیجه |
| --- | --- | --- |
| `h1` | `text-decoration: underline` | خط زیر |
| `h2` | `text-decoration: line-through` | خط روی متن |
| `a` | `text-decoration: none` | حذف خط زیر پیش‌فرض لینک |
| `p` | `text-transform: uppercase` | نمایش با حروف بزرگ |
