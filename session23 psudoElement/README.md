# Session 23 — Pseudo-elements

Pseudo-element با `::` نوشته می‌شود و یک **عنصر مجازی** یا بخش خاصی از محتوا را هدف می‌گیرد؛ بدون اینکه تگ جدیدی در HTML اضافه کنید.

در این جلسه سه مورد را می‌بینیم: **`::before`**، **`::after`**، **`::selection`**

---

## 1. `::before` و `::after`

| Pseudo-element | کجا ساخته می‌شود؟ |
| --- | --- |
| `::before` | قبل از محتوای عنصر |
| `::after` | بعد از محتوای عنصر |

```css
selector::before {
  content: '';
}

selector::after {
  content: '';
}
```

### شرط اجباری: `content`
بدون `content` معمولاً چیزی دیده نمی‌شود.

```css
content: '';           /* خالی — برای شکل‌های تزئینی */
content: 'متن';       /* متن مجازی */
content: url('...');   /* تصویر */
```

### با آن‌ها چه کارهایی می‌شود کرد؟
تقریباً مثل یک عنصر واقعی استایل می‌گیرند:

- متن یا آیکون کنار محتوا
- خط روی قیمت (مثل این جلسه)
- badge، فلش، کادر تزئینی
- افکت hover و دکور UI
- ترکیب با `position` برای جایگذاری دقیق

---

## 2. `::selection`
استایل بخشی از متن که کاربر با ماوس **انتخاب (Select)** می‌کند را عوض می‌کند.

```css
::selection {
  background-color: #ff0000;
  color: #fff;
}
```

در این جلسه وقتی هر متنی در صفحه را سلکت کنید، پس‌زمینه قرمز و متن سفید می‌شود.

معمولاً فقط چند خاصیت محدود مثل `color` و `background-color` روی `::selection` کار می‌کنند.

می‌توانید آن را محدود به یک عنصر هم بنویسید:

```css
p::selection {
  background-color: #ff0000;
  color: #fff;
}
```

---

## تفاوت با Pseudo-class

| | Pseudo-class | Pseudo-element |
| --- | --- | --- |
| علامت | `:` مثل `:hover` | `::` مثل `::before` |
| معنی | حالت عنصر | بخش مجازی / بخش خاصی از محتوا |
| مثال | `:focus`، `:checked` | `::before`، `::after`، `::selection` |

---

## مثال خط روی قیمت (`::before`)

```html
<h1 class="price">189$</h1>
```

```css
.price {
  position: relative; /* مرجع برای absolute */
}

.price::before {
  content: '';
  display: inline-block;
  position: absolute;
  height: 2px;
  width: 73px;
  background-color: #ff0000;
  top: 0;
  bottom: 0;
  margin: auto; /* وسط‌چین عمودی خط */
}
```

چطور کار می‌کند:
1. `::before` یک عنصر مجازی خالی می‌سازد
2. با `height` و `background` تبدیل به خط قرمز می‌شود
3. با `position: absolute` روی متن قیمت می‌نشیند
4. خود `.price` با `relative` مرجع مختصات است

همین کار را می‌توان با `::after` هم کرد؛ فقط عنصر مجازی **بعد** از محتوا ساخته می‌شود.

---

## الگوی رایج برای before/after

```css
.element {
  position: relative;
}

.element::before,
.element::after {
  content: '';
  position: absolute;
  /* اندازه، رنگ، جایگذاری */
}
```

---

## خلاصه مثال‌های این جلسه

| مورد | کاربرد در این جلسه |
| --- | --- |
| `::before` | خط قرمز روی قیمت `.price` |
| `::after` | همان قابلیت؛ اینجا استفاده نشده |
| `::selection` | رنگ قرمز هنگام انتخاب متن |

> نکته: برای هر عنصر معمولاً فقط یک `::before` و یک `::after` دارید. `::selection` جداست و به انتخاب متن کاربر مربوط می‌شود.
