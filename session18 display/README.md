# Session 18 — Display, Visibility & Opacity

در این جلسه می‌بینیم عنصر چطور در صفحه **نمایش** داده می‌شود و تفاوت سه راه «مخفی کردن» چیست.

هر بخش یک باکس سیاه دارد و روی لینک داخلش حالت‌های مختلف را تست می‌کنیم.

---

## 1. `display: inline`
عنصر در همان خط متن می‌ماند؛ مثل رفتار پیش‌فرض `<a>` و `<span>`.

```css
.linkInline {
  display: inline;
}
```

ویژگی‌ها:
- کنار متن/عناصر دیگر در یک خط می‌نشیند
- `width` و `height` معمولاً اثر کامل ندارند
- `margin-top` / `margin-bottom` معمولاً اعمال نمی‌شود

---

## 2. `display: block`
عنصر کل عرض خط را می‌گیرد و به خط خودش می‌رود؛ مثل `<div>` و `<p>`.

```css
.linkBlock {
  display: block;
  text-align: center;
}
```

ویژگی‌ها:
- از خط جدید شروع می‌شود
- می‌توان `width`، `height`، و margin عمودی داد
- در این مثال لینک وسط‌چین شده است

---

## 3. `display: inline-block`
ترکیب هر دو: در خط می‌ماند، ولی مثل block اندازه‌پذیر است.

```css
.linkInlineBlock {
  display: inline-block;
  margin-top: 10px;
}
```

ویژگی‌ها:
- کنار عناصر دیگر می‌نشیند
- `width` / `height` و margin عمودی کار می‌کند
- برای دکمه‌ها و باکس‌های کنار هم خیلی رایج است

---

## 4. سه روش مخفی کردن

### `display: none`
عنصر از صفحه **کاملاً حذف** می‌شود؛ جا هم اشغال نمی‌کند.

```css
.linkNone {
  display: none;
}
```

لینک دیده نمی‌شود و جای خالی هم نمی‌گذارد.

### `visibility: hidden`
عنصر **نامرئی** است، ولی جایش در layout حفظ می‌شود.

```css
.linkInvisible {
  visibility: hidden;
}
```

جای لینک خالی می‌ماند؛ انگار هنوز آنجاست ولی دیده نمی‌شود.

### `opacity: 0`
عنصر کاملاً شفاف است (شفافیت صفر)، ولی هنوز در صفحه هست و جا اشغال می‌کند.

```css
.linkOpacity {
  opacity: 0;
}
```

`opacity` از `0` (نامرئی) تا `1` (کاملاً واضح) است. برخلاف `visibility: hidden`، خود عنصر و فرزندانش شفاف می‌شوند و رویدادهایی مثل کلیک ممکن است هنوز روی آن کار کند (بسته به شرایط).

---

## مقایسه مخفی‌سازی

| خاصیت | دیده می‌شود؟ | جا اشغال می‌کند؟ | کاربرد رایج |
| --- | --- | --- | --- |
| `display: none` | خیر | خیر | حذف کامل از چیدمان |
| `visibility: hidden` | خیر | بله | مخفی موقت بدون به‌هم‌ریختن layout |
| `opacity: 0` | خیر | بله | انیمیشن محو شدن، افکت fade |

---

## مقایسه `display`

| مقدار | در خط می‌ماند؟ | width/height | مثال این جلسه |
| --- | --- | --- | --- |
| `inline` | بله | محدود | `.linkInline` |
| `block` | خیر (خط جدا) | بله | `.linkBlock` |
| `inline-block` | بله | بله | `.linkInlineBlock` |
| `none` | — | — | `.linkNone` |

---

## خلاصه مثال‌ها

| کلاس | خاصیت | نتیجه |
| --- | --- | --- |
| `.linkInline` | `display: inline` | لینک در جریان متن |
| `.linkBlock` | `display: block` | لینک تمام‌عرض و وسط‌چین |
| `.linkInlineBlock` | `display: inline-block` | لینک با `margin-top` |
| `.linkNone` | `display: none` | حذف کامل |
| `.linkInvisible` | `visibility: hidden` | نامرئی با حفظ فضا |
| `.linkOpacity` | `opacity: 0` | شفاف کامل با حفظ فضا |
